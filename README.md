# LITA-Customer-Analysis-Pro2
---------------------------
## Project Title- Customer Data Analysis
--------------------------

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Data Cleaning and Preparation](#data-cleaning-preparation)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Analysis](#analysis)

[Summary](#summary)

### Project Overview
---------------------
This project is all about my second project with the Incubators Hub. This projects aims to generates an insights into the customers subscription performance within a year. 
By analysing the various parameters in the data received by identifying segments and trends of subscription type and the key trends in cancellation and renewals. we seek to gather enough insight to make reasonable decisions which then enables us to tell a compelling stories around our 
data ferom the insight gotten and to know the best subscription performance from our data.

### Data Sources
The primary source of data used here is Customer Data.csv and this is an open source data that can be freely downloaded from an open source online such as kaggle or FRED or any
other data repository site.

### Tools Used
-Miscrosoft Excel-[Download Here](https://www.microsoft.com)
1. For cleaning
2. For data formatting
3. For analysis and visualization
 -SQL- Structured Querying Language [Download Here](https://www.microsoftSQLserver.com)
   For querying data.
-PowerBI - [Download Here](https://www.microsoftpowerbi.com)
  1. For data validation
  2. Using DAX functions to create calculated column or quick measures.
  3. For data Visualization
   -Github for portfolio building.

   ### Data Cleaning and Preparations
   -----------------------------------
   In the initial phase of the data cleaning and preparations, we perform the following actions;
   Data loading and inspection
   Handling duplicate values
   Data Cleaning and formatting

   ### Exploratory Data Analysis
   -----------------------------
   EDA involved the exploration of the data to answer some questions about customers Data such as;
   - Retrive the total numbers of customers from each region
   - Find the most popular subscription type by the numbers of customers
   - Find customers who canceled their subscription within 6 months
   - Calculate the average subscription duration of all customers
   - Find customers with subscription longer than 12 months
   - Calculate total revenue by subscription type
   - Find top 3 regions by subscription cancellation
   - Find the total numbers of active and cancelled

   ### Analysis
   -------------------------
   This is where we include some basic lines of code or queries or even some of the DAX expressions used during the analysis;
   ```SQL
SELECT Region, Count(CustomerID)AS Region_Customers FROM [Customers Data csv]
GROUP BY Region

SELECT TOP 1 SubscriptionType, Count(CustomerID) AS SubCustomer_No FROM [Customers Data csv]
GROUP BY SubscriptionType

SELECT AVG(Duration) AS Avgsub_Duration
FROM [Customers Data csv]

SELECT Duration FROM [Customers Data csv]
WHERE Duration > '366'

SELECT SubscriptionType, SUM(Revenue) AS SubType_Revenue
FROM [Customers Data csv]
GROUP BY SubscriptionType

SELECT Region, Count(Canceled) AS Region_Canc
FROM [Customers Data csv]
GROUP BY Region

SELECT CustomerID FROM [Customers Data csv]
WHERE datediff(month, SubscriptionStart, SubscriptionEnd) <= 6

SELECT Region, COUNT(Canceled) AS Canceled_customers FROM [Customers Data csv] 
WHERE Canceled > 0
GROUP BY Region

SELECT Region, COUNT(Canceled) AS Active_customers FROM [Customers Data csv]
WHERE Canceled < 1
GROUP BY Region

```

![Customers Pivot](https://github.com/user-attachments/assets/9d8cb9d7-9bb2-4692-9190-ea507a4c1f85)

![Customers Charts](https://github.com/user-attachments/assets/99d4d35d-fd09-4909-8c28-7e317d43ba00)

![Customer Data PowerBI](https://github.com/user-attachments/assets/0706eae4-1c72-4857-9b94-2bf7b2059157)

### Summary
In conclusion the east has the highest numbers of customers and the revenue and all the duration of the subscription is either a year/leap year not more than 12 months.
The most common subscription type with the highest revenue is the basic. The East customers are the most active customers and there's no cancellation while other regions Five thousands customers canceled.





