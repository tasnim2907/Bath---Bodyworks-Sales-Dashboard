# Bath & Body Works Canada Sales Dashboard (Excel)
Excel project with Power Query-based data cleaning, Pivot-based analysis, and Dashboard with slicers

## Overview
This project showcases an end-to-end Excel analytics workflow using a Bath & Body Works (Canada) sales dataset. The workbook includes raw data, cleaned and standardized fields, pivot-table analysis, and an interactive dashboard driven by slicers.

## Dashboard Demo (Slicer Interaction)
![Dashboard demo](https://raw.githubusercontent.com/tasnim2907/Bath---Bodyworks-Sales-Dashboard/main/bbw_dashboard.gif)

Static preview:
![Dashboard preview](https://raw.githubusercontent.com/tasnim2907/Bath---Bodyworks-Sales-Dashboard/main/bbw_dashboard_static_preview.JPG)


## Business Questions / Problem Statements
The following questions were defined in the workbook (Pivot Table sheet). Replace the placeholders below with your exact 8 statements from the file:

1. What is total Sales and Profit for 2023 vs 2024?
2. Which province has the highest total Sales and Profit (2023–2024 combined)?
3. Which category contributes the most Sales and Profit in each year (2023, 2024)?
4. Do customers labeled Male vs Female show different average Sales per transaction?
5. What are the top 3 age values by total Sales, and what categories do they buy most?
6. How do Sales trend month-over-month in 2023 vs 2024, and where are the peaks?
7. How does Sales vary by different age group?
8. How is the yearly sales impacted by different channels?

## What’s Inside the Workbook
The Excel file is organized as a full analysis pipeline:

- Raw data sheet: original dataset before standardization
- Cleaned data sheet: cleaned fields created for consistent reporting
- Pivot Table sheet: analysis tables used to power visuals
- Dashboard sheet: interactive visuals with slicers

## Data Cleaning Highlights
Key transformations applied to support reliable analysis:
- Standardized province values into a single `Province_CLEAN` field
- Standardized gender values into `Gender_CLEAN`
- Converted currency/text values into numeric fields (`Sales_CLEAN`, `Profit_CLEAN`)
- Parsed and standardized dates into `Date_CLEAN`
- Created `Age_GROUP` buckets for demographic reporting

## Dashboard Features
- KPI cards for Total Sales and Total Profit
- Sales and profit breakdowns by:
  - Age group
  - Channel (Online vs Store)
  - Category and year trend comparison
- Province slicer to filter the entire dashboard

## How to Interact
1. Download and open: `bbw_canada_sales_SOLUTION.xlsx`
2. Go to the `bbw_Dashboard` sheet
3. Use the Province slicer (and any additional slicers in the file)
4. Watch the KPI cards, pivot tables, and charts update automatically

## Files
- `bbw_canada_sales_SOLUTION.xlsx` — full workbook (raw, cleaned, pivot analysis, dashboard)
- `bbw_dashboard.gif` — slicer interaction demo
- `bbw_dashboard_static_preview.JPG` — static preview image
- `data_dictionary.md` — field definitions and cleaning notes

## Tools Used
- Microsoft Excel (data cleaning, pivot tables, dashboard design)
- Slicers (interactive filtering)
- Charts + formatting (dashboard visualization)

## Notes for Reviewers
This project is designed to demonstrate:
- Practical data cleaning in Excel
- Building analysis-ready fields
- Translating business questions into pivot-table reporting
- Communicating insights through an interactive dashboard
