# Customer Churn Analysis Dashboard

## 1. Project Overview

This project focuses on analyzing customer churn in a telecommunications company using Power BI. The main objective is to identify customer segments with high churn rates, understand patterns associated with customer attrition, and provide data-driven recommendations to improve customer retention.

The analysis was performed using the Telco Customer Churn dataset, which contains customer demographic information, subscribed services, contract details, billing information, and churn status.

**Tools and Technologies:**

* Power BI Desktop
* Power Query (data cleaning and transformation)
* DAX (measures and calculations)
* CSV (data source)

## 2. Dataset

The analysis uses the Telco Customer Churn dataset, containing 7,043 customer records and 21 original columns.

The dataset includes:

* Customer demographics, such as gender, senior citizen status, and dependents
* Account information, including tenure and contract type
* Services, such as internet, phone, and technical support
* Billing information, including monthly and total charges
* Customer churn status

**Dataset source:** [Telco Customer Churn – Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

## 3. Data Cleaning and Transformation

Data preparation was performed entirely in Power Query within Power BI.

The following steps were included:

* Imported the original CSV dataset into Power BI.
* Reviewed column names, data quality, missing values, and data types.
* Assigned appropriate data types to the original columns.
* Converted `TotalCharges` into a numeric data type.
* Replaced 11 blank `TotalCharges` values with 0, as these records correspond to customers with zero tenure and no accumulated charges.
* Created a `TenureBand` column to group customers by account duration:

  * 0–12 months
  * 13–24 months
  * 25–48 months
  * 49+ months
* Created a `ChargeBand` column to group customers into four categories based on the quartiles of `MonthlyCharges`.
* Created a numeric `ChurnFlag` column, assigning 1 to customers who churned and 0 to customers who remained.

These transformations prepared the dataset for consistent analysis and visualization.

## 4. DAX Measures

DAX measures were used to calculate the main performance indicators in the dashboard.

| Measure                 | Description                                              |
| ----------------------- | -------------------------------------------------------- |
| Total Customers         | Total number of customer records                         |
| Churned Customers       | Number of customers who discontinued their services      |
| Churn Rate %            | Percentage of customers who churned                      |
| Avg Monthly Charges     | Average monthly charge per customer                      |
| Monthly Revenue at Risk | Sum of monthly charges associated with churned customers |

The churn rate was calculated by dividing the number of churned customers by the total number of customers, using the `DIVIDE()` function to handle potential division-by-zero cases.

## 5. Dashboard Overview

A single-page interactive dashboard was designed to provide an overview of customer churn and allow users to explore churn patterns across different customer segments.

### Key Performance Indicators (KPIs)

* Total Customers
* Churn Rate %
* Monthly Revenue at Risk
* Average Monthly Charges

### Visualizations

The dashboard includes churn-rate comparisons by:

* Contract type
* Internet service type
* Tenure band
* Payment method

### Interactive Filters

The following slicers allow users to explore specific customer segments:

* Contract
* Internet Service
* Tenure Band

The dashboard supports interactive filtering, allowing users to examine how churn rates change across different groups.

## 6. Key Findings

The analysis highlights several important patterns in customer churn:

### Contract Type

Customers with month-to-month contracts have a substantially higher churn rate than customers with longer-term contracts.

* Month-to-month: approximately 42.7%
* One-year: approximately 11.3%
* Two-year: approximately 2.8%

This indicates that customers without long-term commitments are considerably more likely to leave.

### Internet Service

Customers using fiber optic internet show a relatively high churn rate.

* Fiber optic: approximately 41.9%
* DSL: approximately 19%

This segment may require further investigation into service quality, pricing, and customer satisfaction.

### Payment Method

Customers using electronic checks have a comparatively high churn rate of approximately 45.3%.

This pattern suggests that payment method can help identify customer groups that may benefit from additional retention efforts.

### Customer Tenure

Customers in their first year have a higher churn rate than many longer-tenure groups.

The 0–12-month tenure segment has an approximate churn rate of 47.7%, highlighting the importance of early customer engagement and onboarding.

### Revenue at Risk

Monthly revenue at risk is approximately $139,000, representing the combined monthly charges associated with customers who churned.

This metric highlights the potential financial impact of customer attrition and the importance of retention strategies.

## 7. Recommendations

Based on the observed churn patterns, the following actions are recommended:

### 1. Improve Retention Among Month-to-Month Customers

Introduce targeted retention offers, loyalty incentives, and discounts for customers willing to switch to longer-term contracts. Communicate the benefits of longer contracts while ensuring that offers remain financially sustainable.

### 2. Investigate Fiber Optic Customer Churn

Examine customer feedback, service reliability, technical support experiences, and pricing among fiber optic users. Identify potential service or value-related issues and introduce targeted improvements where necessary.

### 3. Strengthen Early Customer Engagement

Develop a structured onboarding and follow-up process for new customers, especially during their first 12 months. Proactive communication, timely technical assistance, and early identification of dissatisfaction may help reduce customer attrition.

## 8. Limitations

This analysis is based on historical customer data and identifies associations between customer characteristics and churn. These relationships do not necessarily demonstrate that a particular service, contract, or payment method directly causes churn.

Further analysis using customer feedback, service complaints, and longitudinal data could provide deeper insight into the reasons behind customer attrition.

The revenue-at-risk measure represents the monthly charges associated with churned customers and should not be interpreted as a precise forecast of future lost revenue.

## 9. Conclusion

The Customer Churn Dashboard provides an interactive overview of customer attrition and its relationship with contract type, internet service, payment method, and customer tenure.

The analysis identifies month-to-month customers, fiber optic users, electronic check users, and customers with shorter tenure as important segments for further investigation and targeted retention efforts.

By using Power BI, Power Query, and DAX, the project demonstrates how data cleaning, analytical calculations, and interactive visualizations can be combined to support business decision-making.

## 10. Project Deliverables

* `churn_dashboard.pbix` – Interactive Power BI dashboard and data model
* `churn_dashboard.png` – Screenshot of the completed dashboard
* `churn_dashboard_filtered.png` – Screenshot demonstrating dashboard filtering
* `note.md` – Project documentation, key findings, and recommendations
