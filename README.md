# Customer-Churn-Analysis-PowerBI
This Power BI project analyzes customer churn in a telecom company using interactive visuals, DAX measures, and real-world data. It highlights churn patterns based on gender, contract type, tenure, and internet service to help identify at-risk customers and improve retention strategies.


Telco Customer Churn Analysis using Power BI

This project presents an interactive **Power BI dashboard** that analyzes customer churn behavior using a real-world telecommunications dataset. The goal is to understand why customers leave the service and identify key patterns using visuals, KPIs, and filters.

## Project Objectives
Analyze customer behavior to understand churn patterns
Identify which customer segments are more likely to leave
Use DAX measures to calculate churn KPIs
Create a user-friendly dashboard for insights

## Dataset Overview
Source: [Kaggle - Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
Records: 7,043 customer entries
Target variable: `Churn` (Yes/No)

## Key Fields:
`gender`, `SeniorCitizen`, `Partner`, `Dependents`
`tenure`, `InternetService`, `Contract`, `MonthlyCharges`
`PaymentMethod`, `TotalCharges`, `Churn`


##  Power BI Visuals

Total Customers & Churn Count (Card visuals)
Churn by Gender, Contract Type, Internet Service, Senior Citizen
Churn by Tenure Range
Monthly Charges vs Churn (Bar/Line chart)
Slicer filters: Gender, Internet Service, Contract, Churn Status


## DAX Measures Used

DAX
Total Customers
Total Customers = COUNTROWS('WA_Fn-UseC_-Telco-Customer-Churn')

Churned Customers
Churned Customers = CALCULATE(COUNTROWS('WA_Fn-UseC_-Telco-Customer-Churn'), 
                               'WA_Fn-UseC_-Telco-Customer-Churn'[Churn] = "Yes")

Churn Rate (%)
Churn Rate (%) = DIVIDE([Churned Customers], [Total Customers], 0)

Gender-based Churn
Female Churn = CALCULATE(COUNTROWS('WA_Fn-UseC_-Telco-Customer-Churn'),
                         'WA_Fn-UseC_-Telco-Customer-Churn'[gender] = "Female",
                         'WA_Fn-UseC_-Telco-Customer-Churn'[Churn] = "Yes")

Male Churn = CALCULATE(COUNTROWS('WA_Fn-UseC_-Telco-Customer-Churn'),
                       'WA_Fn-UseC_-Telco-Customer-Churn'[gender] = "Male",
                       'WA_Fn-UseC_-Telco-Customer-Churn'[Churn] = "Yes")
