# sales_analysis

Cleaning and analysing a messy e-commerce sales dataset using **Power Query** and **DAX** (Power BI).

## Dataset Overview

The raw dataset contains order-level sales records with the following columns:

| Column | Description |
|---|---|
| ID | Record identifier |
| Customer_Name | Name of the customer |
| Order_ID | Order identifier |
| Order_Date | Date the order was placed |
| Product | Product name |
| Category | Product category |
| Quantity | Number of units ordered |
| Price | Price per unit |
| Payment_Method | How the customer paid |
| Status | Order status |
| Total | Order total (as recorded in the raw data) |


## Initial Observation

The dataset is **messy** and needs cleaning before any analysis can be done. The issues found and the fixes applied are documented step by step below.

![Raw data loaded in Power Query](01-raw-data.png)
*Raw data as loaded into Power Query, before any cleaning.*

## Data Cleaning Log

### Step 1: Understanding the data
Reviewed every column to understand what kind of data it holds and what type it should be (for example, IDs and Quantity as whole numbers, Price as currency, Order_Date as a date).

### Step 2: Checking for duplicate IDs
1. Used **Group By** on `ID` with a **Count Rows** operation to see how many times each ID appears.
2. Filtered the Count column to show only values greater than 1.

![Group By on ID with row count](images/02-group-by-id.png)
*Grouping rows by ID to count occurrences.*

![IDs appearing more than once](images/03-duplicate-ids.png)
*Filtering the count column reveals the duplicate IDs.*

**Finding:** X IDs appear more than once.
