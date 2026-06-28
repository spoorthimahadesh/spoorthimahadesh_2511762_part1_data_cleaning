# Cleaning Log

## Task 5: Business Rules Applied

### 1. Missing Region

* **Rule:** Missing values in the `region` column should be filled with `"Unknown"`.
* **Action Taken:** All missing region values were replaced with `"Unknown"`.
* **Reason:** To ensure no records are lost due to missing geographical information.
* **Quality Report:** Records with missing regions were flagged in the data quality report.

### 2. Missing Ship Mode

* **Rule:** Missing values in the `ship_mode` column should be filled with `"Unknown"`.
* **Action Taken:** All missing ship mode values were replaced with `"Unknown"`.
* **Reason:** To maintain consistency and avoid null values in shipping analysis.
* **Quality Report:** Affected records were flagged in the data quality report.

### 3. Missing Discount

* **Rule:** Missing discount values should be treated as `0` only when other sales-related fields are valid.
* **Action Taken:** Missing discount values were replaced with `0` after validating quantity and unit price fields.
* **Reason:** Missing discounts are assumed to indicate no discount was applied.

### 4. Invalid Discounts

* **Rule:** Negative discounts and discounts greater than `0.50` are invalid.
* **Action Taken:** Discounts less than `0` or greater than `0.50` were flagged as `"Invalid"` in the `cleaned_discount` column.
* **Reason:** Discounts outside the acceptable range violate business rules.

### 5. Cancelled Orders

* **Rule:** Cancelled orders should not contribute to the final completed sales summary.
* **Action Taken:** Records with `order_status = "Cancelled"` were excluded from completed sales calculations.
* **Reason:** Cancelled orders do not generate realized revenue.

### 6. Failed Payments

* **Rule:** Orders with failed payments should not contribute to the final completed sales summary.
* **Action Taken:** Records with `payment_status = "Failed"` were excluded from completed sales calculations.
* **Reason:** Failed payments do not represent successful transactions.

### 7. Refunded Orders

* **Rule:** Refunded orders must be summarized separately.
* **Action Taken:** Orders with refund status were retained and reported separately from completed sales.
* **Reason:** Refunded transactions affect revenue differently and require separate analysis.

### 8. Shipping Date Validation

* **Rule:** Ship dates occurring before order dates are invalid.
* **Action Taken:** Records where `ship_date < order_date` were flagged as invalid shipping records.
* **Reason:** Orders cannot be shipped before they are placed.

## Summary

All business rules were successfully applied, and affected records were either corrected, excluded from analysis, or flagged for review based on the defined business requirements.
