# spoorthimahadesh_2511762_part1_data_cleaning
# Sales Orders Data Cleaning and Quality Assessment

## 1. Problem Summary

The objective of this project was to clean, validate, and prepare a sales orders dataset for business analysis. The dataset contained missing values, duplicate records, invalid discounts, inconsistent categorical values, and date-related issues. The goal was to improve data quality by applying business rules, validating calculations, and generating summary reports and pivot-based insights.

---

## 2. Dataset Description

The dataset contains transactional sales order information with details related to:

* Order ID
* Order Date
* Ship Date
* Customer Segment
* Region
* Ship Mode
* Quantity
* Unit Price
* Discount
* Sales
* Cost
* Profit
* Payment Status
* Order Status

The dataset consisted of approximately **900+ records** and included both numerical and categorical variables.

---

## 3. Tools Used

* **Microsoft Excel**

  * Data Cleaning
  * Formula Creation
  * Conditional Formatting
  * Pivot Tables
  * Pivot Charts
* **Markdown (.md)**

  * Documentation

---

## 4. Cleaning Steps Performed

The following data cleaning steps were performed:

1. Identified and handled missing values.
2. Identified duplicate records and duplicate order IDs.
3. Standardized categorical values.
4. Created a cleaned discount column.
5. Validated sales and profit calculations.
6. Extracted month and year from order dates.
7. Calculated shipping delay in days.
8. Created data quality flags.
9. Generated pivot reports and visualizations.

---

## 5. Business Rules Applied

| Rule Area              | Action Taken                                     |
| ---------------------- | ------------------------------------------------ |
| Missing Region         | Filled with "Unknown"                            |
| Missing Ship Mode      | Filled with "Unknown"                            |
| Missing Discount       | Replaced with 0 if other sales fields were valid |
| Negative Discount      | Flagged as Invalid                               |
| Discount > 0.50        | Flagged as Invalid                               |
| Cancelled Orders       | Excluded from completed sales analysis           |
| Failed Payments        | Excluded from completed sales analysis           |
| Refunded Orders        | Reported separately                              |
| Ship Date < Order Date | Flagged as Invalid                               |

---

## 6. Summary of Data Quality Issues Found

The following issues were identified:

* Missing values in region, ship mode, and discount columns.
* Duplicate order IDs.
* Invalid discount values.
* Inconsistent categorical values.
* Invalid shipping records.
* Sales and profit mismatches.
* Records with failed payments and cancelled orders.

A detailed summary was provided in **data_quality_report.xlsx**.

---

## 7. Summary of Final Pivot Reports

The following pivot reports and charts were created:

1. Sales by Region
2. Sales by Customer Segment
3. Monthly Sales Trend
4. Profit by Region
5. Refunded/Cancelled/Failed Orders by Region
6. Order Status Distribution
7. Payment Status Summary

These reports provided insights into sales performance, profitability, and operational issues.

---

## 8. Key Business Insights

* Certain regions contributed significantly more revenue than others.
* A small number of invalid discounts affected sales calculations.
* Cancelled and failed orders impacted overall revenue performance.
* Refunded orders required separate analysis to understand revenue leakage.
* Data standardization improved the reliability of reporting and analysis.

---

## 9. Assumptions and Limitations

### Assumptions

* Missing discounts imply no discount and were replaced with 0.
* Missing categorical values were assigned "Unknown".
* Duplicate order IDs require manual review before deletion.

### Limitations

* Conflicting duplicate records were not automatically resolved.
* Source data could not be externally validated.
* Filled missing values may influence future analysis.

---

## 10. Screenshots Included

The repository includes screenshots of:

* Cleaned dataset
* Data quality report
* Pivot tables
* Pivot charts
<img width="1867" height="675" alt="image" src="https://github.com/user-attachments/assets/9756e974-713d-4743-bccf-0fb6cc77feca" />
<img width="1532" height="666" alt="image" src="https://github.com/user-attachments/assets/fae1d87f-d23d-4e1a-bd45-2f70963140a1" />

<img width="780" height="496" alt="image" src="https://github.com/user-attachments/assets/8582549f-23d5-4033-843a-f8be709e2fc9" />

<img width="658" height="367" alt="image" src="https://github.com/user-attachments/assets/5a1fd378-3471-4ed2-93e6-9a3966101194" />

---

## Project Deliverables

* `cleaned_orders.xlsx`
* `data_quality_report.xlsx`
* `cleaning_log.md`
* `README.md`

---

**Prepared using Microsoft Excel for data cleaning, validation, and business analysis.**
