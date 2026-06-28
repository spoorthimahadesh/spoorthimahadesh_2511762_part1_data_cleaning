# Cleaning Log

## 1. List of Issues Found

* Missing values were found in `region`, `ship_mode`, and `discount` columns.
* Duplicate `order_id` values were identified.
* Some discount values were invalid (negative values and values greater than 0.50).
* Inconsistent values were found in categorical columns such as `customer_segment` (case and spacing differences).
* Some records had ship dates occurring before order dates.
* Sales and profit mismatches were identified by comparing existing values with recalculated values.

---

## 2. Cleaning Actions Performed

* Filled missing `region` values with `"Unknown"`.
* Filled missing `ship_mode` values with `"Unknown"`.
* Replaced missing discount values with `0` after validating related sales fields.
* Standardized categorical values by correcting case differences and extra spaces.
* Created `cleaned_discount` column to flag invalid discount values.
* Calculated `calculated_sales` using quantity, unit price, and cleaned discount.
* Calculated `calculated_profit` using calculated sales and cost.
* Extracted `order_month` and `order_year` from order dates.
* Calculated shipping delay in days.
* Created `data_quality_flag` column to classify records as Clean, Warning, or Invalid.

---

## 3. Business Rules Applied

* Missing `region` and `ship_mode` values were filled with `"Unknown"`.
* Missing discount values were treated as `0` only when other sales fields were valid.
* Negative discounts and discounts above `0.50` were flagged as invalid.
* Cancelled orders and failed payments were excluded from completed sales analysis.
* Refunded orders were summarized separately.
* Records with ship dates earlier than order dates were flagged as invalid.

---

## 4. Assumptions Made

* Missing discounts indicate that no discount was applied and were replaced with `0`.
* Missing categorical values were assigned `"Unknown"` to preserve records.
* Duplicate order IDs were assumed to require manual review rather than automatic deletion.
* Sales calculations were assumed to follow the formula:
  `Quantity × Unit Price × (1 - Discount)`.

---

## 5. Records Removed

* Exact duplicate rows were removed from the dataset.
* Total records removed: **[32]**.

---

## 6. Records Flagged

* Records with duplicate `order_id`s were flagged for manual review.
* Records with invalid discounts were flagged as `"Invalid"`.
* Records with invalid shipping dates were flagged for review.
* Total flagged records: **[162]**.

---

## 7. Limitations of the Cleaning Process

* Conflicting duplicate records were not automatically resolved and require manual verification.
* Missing values filled with `"Unknown"` may affect future analysis.
* Business rules were applied based on the available dataset and assumptions provided.
* External validation was not performed to verify the accuracy of source data.
