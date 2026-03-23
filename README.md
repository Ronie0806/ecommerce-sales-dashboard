# E-Commerce Sales Performance Dashboard 📊

## Project Overview
This end-to-end data analytics project demonstrates the ability to process raw, unstructured retail data, perform exploratory data analysis (EDA), and build an interactive Business Intelligence dashboard. The goal of this project is to provide actionable insights into revenue trends, product performance, and customer purchasing behavior for an online retail company.

## Tech Stack Used
* **Data Processing & Cleaning:** Python (Jupyter Notebook, `pandas`)
* **Data Visualization & BI:** Microsoft Power BI
* **Calculations:** DAX (Data Analysis Expressions)

## Phase 1: Data Engineering (Python)
The original dataset contained over 500,000 rows of transactional data. To optimize for dashboard performance and demonstrate data manipulation skills, I used Python to extract a representative sample and clean the data.

**Key Data Cleaning Steps:**
* **Encoding Resolution:** Resolved `UnicodeDecodeError` by applying `unicode_escape` to handle European characters and currency symbols.
* **Handling Nulls:** Removed transactions lacking a valid `CustomerID` to ensure accurate user-tracking metrics.
* **Anomaly Removal:** Filtered out negative quantities and zero-dollar unit prices (representing returns and entry errors) to focus on successful sales.
* **Feature Engineering:** Programmatically generated a `TotalSales` column (`Quantity` * `UnitPrice`) and extracted specific time-series features (`Month`, `DayOfWeek`, `Hour`) from the raw `InvoiceDate` string.

## Phase 2: Business Intelligence (Power BI)
The cleaned, 10,000-row dataset was imported into Power BI to construct an interactive executive dashboard. 

**Dashboard Features:**
* **Executive KPIs:** Created dynamic scorecard visuals for Total Revenue, Total Orders, and Unique Customers.
* **Custom DAX Measures:** Engineered an `Average Order Value (AOV)` metric using the `DIVIDE`, `SUM`, and `DISTINCTCOUNT` DAX functions to prevent incorrect mathematical averaging.
* **Trend Analysis:** Developed a smoothed line chart plotting Revenue against Time to identify seasonal sales spikes.
* **Dynamic Filtering:** Implemented a Top N filter on a clustered bar chart to isolate and display only the Top 5 Best-Selling Products by Revenue.
* **Interactive Slicers:** Added a tile-formatted Slicer visual allowing stakeholders to filter the entire dashboard by specific months.

## Key Business Insights Discovered

* **Strong Q4 Seasonality:** Revenue trends show a massive, exponential spike beginning in September and peaking heavily in November. This indicates strong holiday-driven purchasing behavior, suggesting the business should allocate the majority of its marketing budget to Q3/Q4 campaigns.
* **Top Performing Products:** The "Gin + Tonic Diet Metal Sign" is the highest-grossing individual item ($3.6K), closely followed by the "Jumbo Bag Red Retrospot" ($2.9K). The business should ensure high inventory levels for these items, especially leading into the November peak season.
* **Baseline Customer Value:** The Average Order Value (AOV) sits at $29.32. To increase overall revenue without acquiring new customers, the business could implement a strategy like "Free Shipping on orders over $35" or bundle the top-selling Jumbo Bags together to push the average cart size higher.

## How to Run This Project
1. Clone this repository.
2. Run the `ECommerce_Data_Cleaning.ipynb` file in Jupyter to see the data transformation steps (requires `data_small.csv`).
3. Open the `ECommerce_Dashboard.pbix` file in Power BI Desktop to interact with the visualizations.