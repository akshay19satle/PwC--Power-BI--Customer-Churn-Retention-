# PwC-Power-BI-Customer-Churn-Retention-

## Overview
This project analyzes customer churn for a telecom company using Power BI. The dataset, sourced from PwC, includes customer demographics, subscription details, billing information, and customer support interactions. The goal is to identify churn patterns and provide insights to improve customer retention.

## Problem Statement
The purpose of this task is to:

•	Define proper KPI's

•	Create a dashboard for the retention manager reflecting the KPI's

•	Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed

•	Customers who left within the last month

•	Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies

•	Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges and number of tickets opened in the categories administrative and technical

•	Demographic info about customers – gender, age range, and if they have partners and dependents

## Dataset
The dataset contains 7,043 customer records with 23 columns, including:

•	Customer Demographics: Gender, SeniorCitizen, Partner, Dependents

•	Services Used: PhoneService, MultipleLines, InternetService, OnlineSecurity, TechSupport, Streaming Services

•	Billing & Contracts: Contract Type, PaperlessBilling, PaymentMethod, MonthlyCharges, TotalCharges

•	Customer Support: numAdminTickets, numTechTickets

•	Churn Status: Yes/No

## Data Preparation
Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Data Cleaning for the dataset was done in the power query editor as follows:

•	Replaced the value is SeniorCitizen N coverted No and Y converted Yes

•	Removed Unnecessary columns

•	Removed Unnecessary rows

•	Each of the columns in the table were validated to have the correct data type


## Data Analysis (DAX):
•	Revenue = SUM('ChurnData'[TotalCharges])

•	Total customers = COUNT('ChurnData'[customerID])

•	Charges = IF('ChurnData'[MonthlyCharges]<=51.75,"Low charges",IF('ChurnData'[MonthlyCharges]>=51.76 && 'ChurnData'[MonthlyCharges]<=85.25,"Medium Charges",IF('ChurnData'[MonthlyCharges]>=85.26 && 'ChurnData'[MonthlyCharges]<=120,"High Charges")))

•	Deviceprotection% = ROUND(DIVIDE(COUNTAX(FILTER(ChurnData, ChurnData[DeviceProtection] = "Yes"), ChurnData[CustomerID]),COUNT(ChurnData[CustomerID]),0),1) 

•	Churn Rate = DIVIDE(CALCULATE(COUNT(ChurnData[Churn]),ChurnData[Churn] = "Yes"),COUNT(ChurnData[Churn]),0)

•	Multiplelines% = ROUND(DIVIDE(COUNTAX(FILTER(ChurnData, ChurnData[MultipleLines] = "Yes"), ChurnData[CustomerID]),COUNT(ChurnData[CustomerID]),0),1)  

•	OnlineBackup% = ROUND(DIVIDE(COUNTAX(FILTER(ChurnData, ChurnData[OnlineBackup] = "Yes"), ChurnData[CustomerID]),COUNT(ChurnData[CustomerID]),0),1)

•	onlineSecurity % = ROUND(DIVIDE(COUNTAX(FILTER(ChurnData, ChurnData[OnlineSecurity] = "Yes"), ChurnData[CustomerID]),COUNT(ChurnData[CustomerID]),0),1)

•	PhoneService% = ROUND(DIVIDE(COUNTAX(FILTER(ChurnData, ChurnData[PhoneService] = "Yes"), ChurnData[CustomerID]),COUNT(ChurnData[CustomerID]),0),1) 

•	 Streamingmovies% = ROUND(DIVIDE(COUNTAX(FILTER(ChurnData, ChurnData[StreamingMovies] = "Yes"), ChurnData[CustomerID]),COUNT(ChurnData[CustomerID]),0),1) 

•	StreamingTV% = ROUND(DIVIDE(COUNTAX(FILTER(ChurnData, ChurnData[StreamingTV] = "Yes"), ChurnData[CustomerID]),COUNT(ChurnData[CustomerID]),0),1)  

•	Techsupport% = ROUND(DIVIDE(COUNTAX(FILTER(ChurnData, ChurnData[TechSupport] = "Yes"), ChurnData[CustomerID]),COUNT(ChurnData[CustomerID]),0),1)  

## Power BI Dashboard
The Power BI report includes the following key visualizations:

•	KPI Metrics: Total Customers, Churn Rate, Average Monthly Charges, etc.

•	Demographic Analysis: Churn by gender, senior citizen status, and partner status.

•	Subscription Analysis: Churn based on internet service, contract type, and additional services.

•	Billing & Payment Analysis: Relationship between churn and payment methods, monthly charges, and total charges.

•	Customer Support Impact: How the number of support tickets affects churn.

## Key Insights

•	Customers with month-to-month contracts have a higher churn rate.

•	Fiber optic users have a higher churn rate compared to DSL users.

•	Electronic check payments are associated with a higher churn rate.

•	Customers with no online security and tech support are more likely to churn.

## Recommendation
•	Customers using Checks tend to have a higher churn rate compared to AutoPay users , Suggestion encourage customers to switch to AutoPay by offering discounts or incentives.

•	Month-to-Month contracts have the highest churn rate, while Two-Year contracts have the lowest, Suggestion Introduce loyalty rewards or bundle discounts for long-term plans.

•	New customers (0-6 months tenure) churn the most, Suggestion Improve onboarding experience and provide early-stage retention offers.

•	Young member have a higher churn rate compared to Older customers, Suggestion Offer senior-friendly support, such as dedicated customer service or special pricing.









