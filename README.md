# Global Superstore Sales Analytics Dashboard

An interactive **Power BI sales analytics project** built to explore sales performance, profitability, customer behavior, and product performance using the Global Superstore dataset (2011–2014).

The project transforms transactional sales data into business-focused dashboards and KPIs using **Power BI, Power Query, DAX, and Excel**.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Business Problem](#business-problem)
- [Project Objectives](#project-objectives)
- [Tools and Technologies](#tools-and-technologies)
- [Dataset](#dataset)
- [Data Preparation](#data-preparation)
- [Data Model](#data-model)
- [Key DAX Measures](#key-dax-measures)
- [Dashboard Pages](#dashboard-pages)
- [Key Business Insights](#key-business-insights)
- [Business Recommendations](#business-recommendations)
- [Repository Structure](#repository-structure)
- [How to Use the Project](#how-to-use-the-project)
- [Challenges](#challenges)
- [Future Improvements](#future-improvements)
- [Author](#author)

---

## Project Overview

The **Global Superstore Sales Analytics Dashboard** analyzes historical sales transactions from 2011 to 2014. It provides an interactive view of business performance across markets, regions, product categories, customer segments, and time periods.

The report contains four analytical pages:

1. Sales Performance Dashboard
2. Profit Analytics Dashboard
3. Customer Analytics Dashboard
4. Product Analytics Dashboard

Users can explore the data using report filters and slicers, including year, market, category, customer segment, and other business dimensions.

## Business Problem

The business generates thousands of sales transactions across multiple countries and product categories. Reviewing this data manually makes it difficult to identify trends, understand profitability, compare markets, and recognize valuable customers and products.

This project addresses that challenge by providing an interactive reporting solution to:

- Monitor overall sales and profit.
- Track monthly sales and profit trends.
- Identify high-performing and low-performing categories and products.
- Analyze customer purchasing behavior.
- Compare performance across markets and regions.
- Support faster, data-driven business decisions.

## Project Objectives

- Convert raw transactional data into an analysis-ready dataset.
- Clean and prepare data using Power Query.
- Build a date-based data model.
- Create reusable DAX measures for important business KPIs.
- Design clear and interactive Power BI dashboards.
- Extract actionable insights from sales, profit, customer, and product data.

## Tools and Technologies

| Tool / Technology | Purpose |
|---|---|
| Microsoft Power BI | Data modeling, interactive reports, and visualizations |
| Power Query | Data cleaning and transformation |
| DAX | KPI and analytical measure calculations |
| Microsoft Excel | Source dataset and data inspection |
| GitHub | Project documentation and version control |

## Dataset

- **Dataset:** Global Superstore
- **Period:** 2011–2014
- **Scale:** Approximately 51,000+ transaction rows, as described in the project report.
- **Source file in this repository:** `global-sales.xlsx`
- **Main worksheet:** `superstore`

The workbook includes fields such as:

- Order ID and Order Date
- Customer ID and Customer Name
- Product ID and Product Name
- Category and Sub-Category
- Market, Region, Country, State, and City
- Sales, Profit, Quantity, and Discount
- Shipping Cost and Ship Mode
- Segment and Order Priority

The workbook also contains fields such as `Year`, `Delivery Days`, and `Profit Margin`. The exact fields available for analysis are defined by the supplied Excel workbook.

> **Note:** The dataset is historical and covers 2011–2014. Dashboard values are approximate figures documented in the project report and may vary when filters are applied.

## Data Preparation

Data preparation was performed in **Power Query** before building the report.

The documented preparation steps include:

- Removed unnecessary columns.
- Checked duplicate records.
- Reviewed missing values.
- Changed columns to appropriate data types.
- Formatted date columns.
- Created a Calendar table.
- Renamed columns for clarity.
- Standardized category names.
- Improved overall data quality.
- Loaded the prepared data into Power BI.

## Data Model

The project report describes a **Star Schema** approach with:

- **Fact table:** `Superstore`
- **Date dimension:** `Calendar`

The date relationship is:

`Calendar[Date]` → `Superstore1[Order Date]`

This relationship supports time-based analysis, including monthly and yearly reporting.

## Key DAX Measures

The following measures are documented in the project report. Table and column names should match the names used in the Power BI model.

```dax
Total Sales =
SUM(superstore1[Sales])
```

```dax
Total Profit =
SUM(superstore1[Profit])
```

```dax
Total Orders =
DISTINCTCOUNT(superstore1[Order_ID])
```

```dax
Total Customers =
DISTINCTCOUNT(superstore1[Customer_ID])
```

```dax
Profit Margin % =
DIVIDE([Total Profit], [Total Sales])
```

```dax
Average Sales per Customer =
DIVIDE([Total Sales], [Total Customers])
```

```dax
Average Profit per Customer =
DIVIDE([Total Profit], [Total Customers])
```

```dax
Average Orders per Customer =
DIVIDE([Total Orders], [Total Customers])
```

```dax
Average Sales per Product =
DIVIDE(
    [Total Sales],
    DISTINCTCOUNT(superstore1[Product_Name])
)
```

```dax
Average Profit per Product =
DIVIDE(
    [Total Profit],
    DISTINCTCOUNT(superstore1[Product_Name])
)
```

## Dashboard Pages

### 1. Sales Performance Dashboard

Provides an overview of overall sales performance, including:

- Total Sales
- Total Profit
- Total Orders
- Total Customers
- Monthly Sales Trend
- Sales by Category
- Top Products
- Global Sales Distribution
- Customer Segment Analysis

**Highlights documented in the report:**
- Total sales reached approximately **$13 million**.
- Technology generated the highest sales.
- The Consumer segment contributed the highest revenue.
- Sales increased significantly in the last quarter.

### 2. Profit Analytics Dashboard

Focuses on profitability across products, categories, markets, and time.

**Highlights documented in the report:**
- Total profit exceeded approximately **$1.5 million**.
- Overall profit margin was approximately **11.6%**.
- Technology generated the highest category profit.
- Monthly profit showed an upward trend.
- The Central region contributed the highest profit.

### 3. Customer Analytics Dashboard

Explores customer purchasing behavior and customer-level performance.

**Highlights documented in the report:**
- Approximately **5K customers**.
- Average sales per customer were approximately **$2.59K**.
- Average profit per customer was approximately **$301**.
- The Consumer segment had the highest number of customers.
- APAC recorded the highest customer order volume.

### 4. Product Analytics Dashboard

Evaluates product-level performance, sales contribution, and profitability.

**Highlights documented in the report:**
- Approximately **10K products**.
- Approximately **178K units** sold.
- Office Supplies contained the highest number of products.
- Phones generated the highest sub-category profit.
- Product performance varied across customer segments.

## Key Business Insights

Based on the analysis documented in the project report:

1. Technology is the leading category in both sales and profit.
2. The Consumer segment contributes the most revenue.
3. Office Supplies contains the highest number of products.
4. Sales increase toward the end of the year.
5. Profit follows a positive trend over time.
6. The APAC market has the highest order volume.
7. Phones are the most profitable sub-category.
8. Top products and customers make significant contributions to business performance.
9. Regional performance and profit margins differ across markets and categories.
10. Interactive filters and DAX measures support flexible business analysis.

## Business Recommendations

- Continue investing in the Technology category because of its strong sales and profit contribution.
- Use targeted promotions to build on the Consumer segment's revenue contribution.
- Review pricing and discount strategies for low-margin categories.
- Strengthen supply and marketing planning for the APAC market.
- Evaluate opportunities to expand the Phones sub-category.
- Introduce customer loyalty initiatives for valuable customers.
- Use year-end sales trends to plan inventory and operations.

## Repository Structure

The repository contains the following project files:

```text
Global-Superstore-Sales-Analytics/
│
├── README.md
├── global-sales.pbix
├── global-sales.xlsx
└── Global_Superstore_Sales_Analytics_Dashboard_Report.pdf
```

- `global-sales.pbix` — Power BI report file containing the dashboard and data model.
- `global-sales.xlsx` — Excel source dataset.
- `Global_Superstore_Sales_Analytics_Dashboard_Report.pdf` — Detailed project documentation, dashboard descriptions, KPIs, insights, and recommendations.
- `README.md` — Project overview and documentation.

## How to Use the Project

1. Clone or download this repository.
2. Open `global-sales.pbix` using Microsoft Power BI Desktop.
3. If Power BI asks for the source file location, browse to `global-sales.xlsx` and update the data source path.
4. Refresh the data if required.
5. Navigate through the four dashboard pages.
6. Use the available slicers and filters to explore different years, markets, categories, and customer segments.

**Requirement:** Microsoft Power BI Desktop is needed to open and interact with the `.pbix` report.

## Challenges

Some of the challenges addressed during the project were:

- Working with a dataset containing more than 51,000 rows.
- Handling inconsistent category and sub-category naming.
- Establishing accurate date relationships between the Calendar and Superstore tables.
- Creating DAX measures that respond correctly to report filters.
- Maintaining dashboard readability across four analytical pages.
- Keeping formatting and visual design consistent.

## Future Improvements

Potential enhancements include:

- Add scheduled or automated data refresh.
- Apply forecasting to estimate future sales and profit.
- Incorporate marketing expenditure or economic data.
- Create a mobile-optimized report layout.
- Include returns and refunds for more complete profitability analysis.
- Automate report distribution through Power BI Service.

## Author

**Krish Patel**  
Data Analyst / Business Analyst

- **Project:** Global Superstore Sales Analytics Dashboard
- **Tools:** Power BI | Power Query | DAX | Excel

---

If you find this project useful, feel free to ⭐ the repository.
