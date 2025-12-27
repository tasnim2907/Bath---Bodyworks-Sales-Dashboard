# Data Dictionary — Bath & Body Works Canada Sales Dashboard

This data dictionary documents the key fields used in the cleaned dataset, pivot tables, and dashboard. The workbook contains both raw and cleaned versions of the data; the dashboard is driven primarily by the cleaned fields to ensure consistent grouping and correct calculations.

## Dataset Scope
- Currency: CAD (as shown on the dashboard)
- Grain: Transaction-level records (one row per sale/transaction)
- Primary filters used in the dashboard: Province (and any additional slicers included in the workbook)

---

## Raw Fields (as received)
These columns may include inconsistent formatting (casing, spacing, mixed formats) and are not always reliable for direct reporting.

- **Date** (Text/Date)
  - Original transaction date. May appear in multiple formats.

- **Province** (Text)
  - Original province field. May contain inconsistent values (e.g., casing differences or mixed province+city strings in some datasets).

- **City** (Text)
  - Original city field.

- **Gender** (Text)
  - Original gender field with possible inconsistent labels.

- **Age** (Number)
  - Customer age at time of transaction.

- **Category** (Text)
  - Product category (examples: Candles, Body Care, Wallflower & Air Freshener, Hand Soap & Sanitizer, Men’s).

- **Selling Channel** (Text)
  - Sales channel (e.g., Online, Store).

- **Sales** (Text/Number)
  - Sales amount. May be stored as text, sometimes with currency symbols.

- **Profit** (Text/Number)
  - Profit amount. May be stored as text, sometimes with currency symbols.

---

## Cleaned / Standardized Fields (used for reporting)
These are the fields created/standardized to power pivots and visuals reliably.

- **Date_CLEAN** (Date)
  - Standardized date field parsed into a consistent date type.
  - Used for year comparisons and time-based reporting.

- **Year** (Number) *(if present)*
  - Extracted year from `Date_CLEAN` to support year-over-year comparisons.

- **Province_CLEAN** (Text)
  - Standardized province value used for consistent grouping and filtering.
  - Designed to eliminate casing/abbreviation issues and invalid values.

- **Gender_CLEAN** (Text)
  - Standardized gender values for reporting (e.g., Male, Female, Unknown).
  - Ensures pivots do not split the same category into multiple labels.

- **Sales_CLEAN** (Number)
  - Numeric sales value converted from the raw `Sales` field.
  - Currency symbols/text removed and values cast to numeric.
  - Used for all sales totals, pivot aggregations, and dashboard KPI cards.

- **Profit_CLEAN** (Number)
  - Numeric profit value converted from the raw `Profit` field.
  - Currency symbols/text removed and values cast to numeric.
  - Used for all profit totals, pivot aggregations, and dashboard KPI cards.

- **Age_GROUP** (Text)
  - Age bucket derived from `Age` to support demographic reporting.
  - Example buckets used in the workbook/dashboard:
    - Teen (13–17)
    - Young Adult (18–24)
    - Adult (25–34)
    - Mid-Age (35–54)
    - Older Adult (55–75)
    - Unknown (for missing/invalid ages, if applicable)

---

## Pivot Table Outputs (reporting layer)
These are not raw columns, but derived summaries used in the dashboard.

- **Total Sales**
  - Sum of `Sales_CLEAN` under current slicer/filter context.

- **Total Profit**
  - Sum of `Profit_CLEAN` under current slicer/filter context.

- **Sales by Age Group**
  - Aggregation of `Sales_CLEAN` and `Profit_CLEAN` grouped by `Age_GROUP`.

- **Yearly Sales by Channel**
  - Aggregation of `Sales_CLEAN` and `Profit_CLEAN` grouped by `Year` and `Selling Channel`.

- **Yearly Sales and Profit by Category**
  - Aggregation of `Sales_CLEAN` and `Profit_CLEAN` grouped by `Year` and `Category`.

---

## Data Quality Rules and Notes
- **Use cleaned fields for analysis**: Pivot tables and visuals should use `*_CLEAN` fields to avoid inconsistent grouping and incorrect totals.
- **Refreshing**: If you modify or append new rows in the dataset, refresh pivot tables so changes flow into the dashboard visuals.
- **Missing values**:
  - If `Age` is missing or invalid, it should map to `Age_GROUP = Unknown`.
  - If `Gender` is missing or inconsistent, it should map to `Gender_CLEAN = Unknown`.

---

## Suggested Column Mapping (for reviewers)
When reviewing the dataset, prioritize these fields:
- Filtering/grouping: `Province_CLEAN`, `Category`, `Selling Channel`, `Age_GROUP`, `Year`
- Metrics: `Sales_CLEAN`, `Profit_CLEAN`
- Time: `Date_CLEAN`
