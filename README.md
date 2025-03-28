# AdventureWorks Data Exploration and Dashboard Project

## Introduction

This project analyzes the popular AdventureWorks Cycle dataset detailing transactional and operational data for a fictitious bike manufacturer, across 5 main database schemas and 68 tables. The work utilizes PostgreSQL for exploratory data analysis (EDA) querying, Python (via SQLAlchemy) for data extraction, and Tableau for creating insightful dashboards. The project aims to demonstrate an end-to-end business intelligence workflow: querying data, exporting it for analysis, and building dashboards that communicate actionable insights.

**Objectives & Approach:**
- Perform EDA using SQL queries.
- Extract select tables from the database and export to Excel.
- Design dashboards to answer key business questions and visualize KPIs.

## Key Outputs

The cumulative output and insights of this work are presented in the following:

[AdventureWorks Interactive Tableau Dashboard](https://public.tableau.com/views/AdventureWorksDashboard_17409660938970/OverviewDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

**Dashboard Preview 1:** Overview Dashboard - focuses on total sales, profit, quantity sold, and monthly trends.

<img src="visualizations/01. Overview Dashboard.png" alt="overview_dashboard" width="1000"/>

**Dashboard Preview 2:** Customer Insights Dashboard - highlights total unique customers, average order value, geographic distribution, and top customers.

<img src="visualizations/02. Customer Insights Dashboard.png" alt="customer_dashboard" width="1000"/>

**Dashboard Preview 3:** Vendor Insights Dashboard - displays total vendor spend, quantities purchased, and vendor dependency.

<img src="visualizations/03. Vendor Insights Dashboard.png" alt="vendor_dashboard" width="1000"/>

## Prerequisites

- PostgreSQL
- Python with the pandas and SQLAlchemy libraries
- Tableau

## Data Source

The data used for this project is available at this [Github repository](https://github.com/lorint/AdventureWorks-for-Postgres?tab=readme-ov-file), which provides the scripts needed to set up the OLTP database for Postgres.

The orignal sample data for AdventureWorks was created and made accessible by Microsoft for training and testing their stack (e.g. MS SQL Server) but has since been adapted for other applications like Postgres, as is the case here. 

## How to Use

1. Setup local Postgres database via two options:

	1. Option 1 - Direct setup: 
		1. Download the [adventure_works-oltp-install-script](https://github.com/Yishak-Ali/AdventureWorks-Business-Analytics/tree/main/adventure_works-oltp-install-script) folder which has the SQL install script and preprocessed CSV data files modified to work with Postgres.

		2. Run the following in your terminal / command prompt to set up a new local Postgres database and load the data:
			``` 
			psql -c "CREATE DATABASE \"adventureworks\";"
			psql -d adventureworks < install.sql
		    ```
	2. Option 2 - Setup from source:
		1. Download [AdventureWorks OLTP script](https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks-oltp-install-script.zip) as well as the update_csvs.rb and install.sql files in the [linked repository](https://github.com/lorint/AdventureWorks-for-Postgres?tab=readme-ov-file).
		
		2. Extract the .zip and compile all of the CSV files, update_csvs.rb and install.sql files into the same folder.

		3. Run the following in your terminal / command prompt to modify the CSVs to work with Postgres:
			```
			ruby update_csvs.rb
			```
		4. Finally, run the below to set up a new local Postgres database and load the data:
			```
			psql -c "CREATE DATABASE \"adventureworks\";"
			psql -d adventureworks < install.sql
		    ```
2. Download the [AdventureWorks Queries.ipynb](https://github.com/Yishak-Ali/AdventureWorks-Business-Analytics/blob/main/AdventureWorks%20Queries.ipynb) script and upload to your local Jupyter Notebook environment.

3. Modify the database connection string in the first code chunk with your relevant username, host, and port information and run the .ipynb script.

4. To export the used tables as Excel files for Tableau, prior to running the .ipynb script, uncomment the last line of each code chunk in the 'Export files for Tableau' section. Alternatively, download the [combined_tables.xlsx](https://github.com/Yishak-Ali/AdventureWorks-Business-Analytics/tree/main/data) file, which has all the tables used for analysis compiled in a single Excel workbook for Tableau connection. 


