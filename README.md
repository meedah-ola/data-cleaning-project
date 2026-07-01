# data-cleaning-project
# E-Commerce Orders — Data Cleaning

## Project Overview
This project demonstrates a structured data cleaning process applied to a 1,200-row e-commerce orders dataset. The goal was to identify and handle missing values, check for duplicates, and validate data formats before analysis.

## Tools Used
- Microsoft Excel (live formulas, COUNTBLANK, COUNTIF, SUMPRODUCT)

## Dataset
- **Source:** E-Commerce Orders Dataset
- **Rows:** 1,200 orders
- **Columns:** 14 (OrderID, Date, CustomerID, Product, Quantity, UnitPrice, ShippingAddress, PaymentMethod, OrderStatus, TrackingNumber, ItemsInCart, CouponCode, ReferralSource, TotalPrice)
- **Date range:** January 2023 – June 2025

## Cleaning Steps Performed

### 1. Missing Values
- Scanned all 14 columns using `COUNTBLANK` formulas
- **Finding:** Only `CouponCode` had missing values — 309 out of 1,200 rows (25.75%)
- **Action:** Replaced nulls with `"No Coupon"` using an `IF` formula so the column remains fully analyzable

### 2. Duplicate Check
- Checked for fully duplicate rows and duplicate `OrderID` and `TrackingNumber` values using `SUMPRODUCT` + `COUNTIF`
- **Finding:** Zero duplicates found across all three checks

### 3. Data Format & Value Validation
- Confirmed `Date` column is stored as a true date type (not text)
- Confirmed `Quantity`, `UnitPrice`, and `TotalPrice` are numeric with no negatives or zeroes
- Cross-validated `TotalPrice = Quantity × UnitPrice` across all 1,200 rows — zero mismatches found
- Confirmed date range falls within expected 2023–2025 window
- Confirmed all categorical text fields (Product, PaymentMethod, OrderStatus, ReferralSource) have consistent capitalization and no stray whitespace

## Workbook Structure

| Sheet | Purpose |
|---|---|
| README | Summary of findings and methodology |
| RawData | Original, unmodified dataset |
| Cleaning_Audit | Live formulas for all cleaning checks |
| CleanedData | Final cleaned dataset ready for analysis |

## Key Finding
The dataset was largely clean with one actionable issue: 309 missing `CouponCode` values. These were not errors but expected blanks (orders placed without a coupon), so rows were retained and the field was filled with `"No Coupon"` rather than deleted.

## Files in This Repository
- `Ecommerce_Data_Cleaning.xlsx` — Full cleaning workbook with live formulas
- `README.md` — This file

## Skills Demonstrated
Data cleaning · Missing value treatment · Duplicate detection · Format validation · Excel formulas · Data preparation
