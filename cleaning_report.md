# Cleaning Report

Dataset: `dirty_cafe_sales.csv`, 10,000 rows, 8 columns. Script: [`src/clean_cafe_sales.py`](../src/clean_cafe_sales.py). Counts from the last run are in [`cleaning_log.json`](cleaning_log.json).

## 1. What was wrong

There are no duplicate rows and no duplicate Transaction IDs. All IDs follow the pattern `TXN_` plus 7 digits. The dirt is one thing: placeholder values (blank, `ERROR`, `UNKNOWN`) in every column except Transaction ID. 6,911 of 10,000 rows (69.1%) have at least one.

| Column | Blank | ERROR | UNKNOWN | Total | Share of rows |
|---|---|---|---|---|---|
| Transaction ID | 0 | 0 | 0 | 0 | 0% |
| Item | 333 | 292 | 344 | 969 | 9.7% |
| Quantity | 138 | 170 | 171 | 479 | 4.8% |
| Price Per Unit | 179 | 190 | 164 | 533 | 5.3% |
| Total Spent | 173 | 164 | 165 | 502 | 5.0% |
| Payment Method | 2,579 | 306 | 293 | 3,178 | 31.8% |
| Location | 3,265 | 358 | 338 | 3,961 | 39.6% |
| Transaction Date | 159 | 142 | 159 | 460 | 4.6% |

Two side effects of the placeholders: the three labels split what is really one category ("missing"), and Quantity, Price Per Unit and Total Spent couldn't be read as numbers.

## 2. The price list

I could not read the Kaggle page (it renders with JavaScript), so I derived the price list from the data. Across the 8,552 rows where both Item and Price Per Unit are valid, every item has exactly one price and there are no conflicts.

| Item | Price |
|---|---|
| Cookie | 1.0 |
| Tea | 1.5 |
| Coffee | 2.0 |
| Cake | 3.0 |
| Juice | 3.0 |
| Sandwich | 4.0 |
| Smoothie | 4.0 |
| Salad | 5.0 |

This is the one assumption the recovery rules depend on. The data supports it, but it should be confirmed against the dataset description.

## 3. Decisions

### 3.1 Standardise placeholders
**Decision:** convert blank, `ERROR` and `UNKNOWN` to a true null.
**Why:** the three labels mean the same thing. Keeping them separate would split counts and block numeric parsing. This changes no real data.

### 3.2 Fix data types
**Decision:** Quantity to whole number, Price and Total to decimal, Transaction Date parsed as `YYYY-MM-DD`.
**Result:** every remaining date parsed cleanly and falls between 2023-01-01 and 2023-12-31. Quantity is always 1 to 5. No zero or negative values.

### 3.3 Recover values using relationships in the data
Before applying any rule, I tested the core one. In the 8,544 rows where Quantity, Price and Total were all valid, `Quantity × Price = Total` held in every row. That rules out discounts or rounding that would make recovery wrong.

| Rule | Fields recovered | Reason |
|---|---|---|
| Price from Item (price list) | 479 | Each item has one price |
| Price from Total ÷ Quantity | 48 | Used when Item was also missing |
| Item from Price, only for 1.0 Cookie, 1.5 Tea, 2.0 Coffee, 5.0 Salad | 489 | These prices belong to a single item |
| Quantity from Total ÷ Price | 456 | Follows from the verified formula |
| Total from Quantity × Price | 479 | Follows from the verified formula |

A second pass found nothing new. In total, 1,841 rows had at least one field recovered.

### 3.4 Do not guess what can't be derived

| Column | Unresolved | Treatment | Reason |
|---|---|---|---|
| Item | 480 | `Unknown` | 247 have price 3.0 (Cake or Juice), 227 have price 4.0 (Sandwich or Smoothie), 6 have no price. Nothing in the row separates the candidates |
| Quantity | 23 | Left blank | Two of the three linked values are missing, so the third can't be calculated |
| Price Per Unit | 6 | Left blank | Same reason, and the item is also unknown |
| Total Spent | 23 | Left blank | Same reason |
| Payment Method | 3,178 | `Unknown` | No other column relates to it |
| Location | 3,961 | `Unknown` | No other column relates to it |
| Transaction Date | 460 | Left blank | Transaction IDs are random, not sequential, so they carry no date information |

**Why not impute Payment Method and Location with the most common value?** It would invent about 3,000 payment methods and 4,000 locations, then show up in any breakdown as if it were real. An honest `Unknown` group is easier to defend than a smoothed-over one.

### 3.5 Excluded records
**No rows were deleted.** Instead, a flag column marks rows that shouldn't be used for item-level analysis.

- `Analysis Ready = True`: Item, Quantity, Price and Total are all known. 9,500 rows.
- `Analysis Ready = False`: 500 rows, mostly the 480 with an unknown item, plus rows with a missing numeric field.

**Why flag instead of delete:** deleting would discard valid information in the same rows (a known date, payment method or location) and would hide the decision. A flag keeps the rows, makes the exclusion visible, and lets the analyst choose.

## 4. Validation after cleaning

- Duplicate rows: 0. Duplicate Transaction IDs: 0.
- No leading or trailing spaces in any column.
- `Quantity × Price = Total` in all 9,974 rows where all three are present: 0 mismatches.
- No row has an Item whose price disagrees with the price list: 0 conflicts.
- No non-integer quantities.

## 5. Output columns

The cleaned file keeps the original 8 columns and adds:

- `Recovered Fields`: lists which fields in that row were filled in by a rule (1,841 rows have an entry).
- `Analysis Ready`: the flag described in 3.5.

## 6. Limitations

- Everything in 3.3 rests on the derived price list. If a real price differs, the recovered Item, Price and Total values would be wrong for that item.
- Payment Method and Location are about a third and two-fifths unknown. Any conclusion drawn from them is weak.
- Total revenue across rows with a known total is 89,096. Of that, 5,141 sits in rows with an unknown Item, so item-level revenue is slightly understated.
- Recovery was done only where the answer was certain. A model-based imputation could fill more, but I chose not to, to keep every filled value defensible.
