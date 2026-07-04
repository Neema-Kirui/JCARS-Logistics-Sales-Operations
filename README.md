# JCARS-Logistics-Sales-Operations

JCARS Logistics Sales & Operations Dashboard

Project Objective

The objective of this project was to analyze JCARS Logistics sales and operational performance using Power BI. The dashboard provides insights into revenue, profitability, sales performance, customer behavior, operational efficiency, and delivery performance to support business decision-making.

Dataset

The dataset contains 276 sales records and includes information such as:

Customer Details
Sales Representatives
Vehicle Information
Branches
Regions
Revenue
Costs
Delivery Information
Payment Information
Customer Ratings
Data Cleaning

The dataset was cleaned using Power Query before analysis.

The following transformations were performed:

Removed duplicate records.
Corrected inconsistent text values.
Converted numeric values stored with "M" into actual numbers.
Changed incorrect data types.
Removed null values where necessary.
Standardized customer and sales representative names.
Created a Date Table for time intelligence.
Importing Data into Aiven

The cleaned dataset was imported into an Aiven PostgreSQL database.

Steps followed:

Created a PostgreSQL service in Aiven.
Downloaded the connection details.
Created the required database table.
Imported the cleaned dataset into PostgreSQL.
Verified that all records were successfully loaded into the database.
Connecting Power BI to Aiven

Power BI was connected to the Aiven PostgreSQL database by:

Selecting Get Data → PostgreSQL Database.

Entering:
Server Name
Database Name

Selecting Import mode.

Authenticating using the PostgreSQL username and password.

Loading the sales table into Power BI.

Dash Model

A separate Date Table was created and related to the sales table using the Order Date field.

Relationships were configured to support:

Monthly analysis
Quarterly analysis
Yearly analysis
Time intelligence calculations
Measures and Calculations Created

The following DAX measures were created:

Total Revenue
Total Revenue = SUM('powerbi jcars'[Revenue Recorded])

Total Cost
Total Cost =
SUM('powerbi jcars'[Unit Cost]) +
SUM('powerbi jcars'[Delivery Fee]) +
SUM('powerbi jcars'[Logistics Cost])

Profit
Profit = [Total Revenue] - [Total Cost]

Profit Margin
Profit Margin =
DIVIDE([Profit],[Total Revenue],0)

Total Orders
Total Orders =
DISTINCTCOUNT('powerbi jcars'[Order ID])

Total Cars Sold
Total Cars Sold =
SUM('powerbi jcars'[Units Sold])

Average Rating
Average Rating =
AVERAGE('powerbi jcars'[Customer Rating])

Average Delivery Days
Average Delivery Days =
AVERAGE('powerbi jcars'[Delivery Days])

Dashboard Page

The main dashboard contains:

KPI Cards
Total Revenue
Profit
Total Cars Sold
Total Orders
Average Rating
Profit Margin
Average Delivery Days
Revenue, Profit and Units Sold by Month
Revenue by Car Make
Units Sold by Car Model
Revenue by Branch
Revenue by Car Model
Revenue by Region (Treemap)

Interactive slicers for:
Region
Branch
Month

Key Insights

Toyota generated the highest total revenue among all car brands.

The Toyota Harrier recorded the highest number of units sold, making it the most popular vehicle model.

Kakamega Branch generated the highest revenue compared to the other branches.

Rift Valley contributed the highest regional revenue.

Facebook was the most effective lead source, generating the highest number of customer orders.

Recommendations

Increase inventory and marketing efforts for Toyota vehicles, particularly the Harrier, to capitalize on customer demand.

Replicate the successful sales strategies used by the Kakamega branch across lower-performing branches.

Invest more in Facebook marketing campaigns while improving underperforming lead sources such as WhatsApp and Website channels.

Tools Used
Power BI Desktop
Power Query
DAX
PostgreSQL
Aiven
GitHub

Author

Neema Cherono Kirui
