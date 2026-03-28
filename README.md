# pharma-sales-analysis
PROJECT OVERVIEW
This project focuses on analyzing a global pharmaceutical sales dataset using SQL. The objective is to extract meaningful business insights related to revenue trends, regional performance, demand versus stock, and product-level efficiency.

The analysis serves as a foundation for further visualization using Power BI, which will be added in the next phase.

DATASET DESCRIPTION

The dataset contains sales, pricing, and inventory-related information across multiple regions and products.

Key fields included:

Date, Year, Month, Day: Used for time-based analysis
Region, Country: Used for geographic segmentation
Category, Medicine: Product classification
Age_group: Customer segmentation
Units_sold, Unit_price: Sales metrics
Stock_level: Inventory availability
Expiry_days_remaining: Shelf-life tracking
Covid_flag: Indicates pandemic-related impact

DATABASE SETUP

A database named "Pharma_db" was created and used for this analysis.

A table named "pharma_sales" was created with fields covering date, geography, product details, sales metrics, inventory levels, and expiry information.

The dataset was imported from a cleaned CSV file using LOAD DATA INFILE. The date field was transformed into proper DATE format using STR_TO_DATE function.

DATA TRANSFORMATION

To simplify analysis, a SQL view named "pharma_base" was created.

This view includes all original columns along with a calculated field:
Revenue = Units_sold * Unit_price

This allowed easier and cleaner querying for all further analysis.

ANALYSIS PERFORMED

MONTHLY REVENUE TREND
Revenue was aggregated by year and month to understand overall performance and identify seasonal trends.
MONTH-OVER-MONTH GROWTH
Window functions (LAG) were used to compare revenue with the previous month and calculate percentage growth. This helps in tracking business momentum.
REGIONAL PERFORMANCE ANALYSIS
Revenue was analyzed across regions to identify top-performing and underperforming markets.
DEMAND VS STOCK ANALYSIS
Units sold (demand) was compared with stock levels to detect:
Stock shortages (high demand, low stock)
Overstock situations (low demand, high stock)
PRODUCT-LEVEL INSIGHTS
Analysis was performed at medicine and region level to evaluate:
Demand patterns
Stock distribution
Average expiry days

This helps in identifying inefficiencies in inventory management.

KEY INSIGHTS

Revenue trends reveal clear monthly patterns and fluctuations
Certain regions show strong demand but insufficient stock, indicating supply gaps
Some products have high stock but low demand, increasing expiry risk
Expiry data highlights areas where inventory management can be improved
