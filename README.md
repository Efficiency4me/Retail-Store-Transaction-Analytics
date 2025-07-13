**🛍️ Retail Transaction Analytics Dashboard (Power BI)**

This project presents a detailed retail transaction analysis dashboard developed using Power BI, based on synthetic transactional data across different regions, customer demographics, product categories, and acquisition channels. It aims to uncover key trends in sales performance, customer behavior, product profitability, and fraud detection, with actionable business insights and recommendations.


**📁 Project Objectives**
1.	Visualize and monitor retail KPIs across countries, acquisition sources, and product lines.
2.	Identify top-performing customers, sales channels, and product categories.
3.	Detect patterns of fraudulent transactions.
4.	Provide data-driven recommendations to optimize marketing, inventory, and revenue strategies.

📸 Dashboard Snapshot

 
**📊Dashboard Overview** 
1.  The Power BI dashboard includes: 
  a.  Summary Cards: Total transactions, revenue, profit, quantity ordered, and percentage of revenue without fraud. .
  b.  Charts and Visuals:
    1.	Profit by Country and Acquisition Source
    2.	Total Quantity Ordered per Product Category
    3.	Revenue and Profit by Product Category
    4.	Contribution of Fraud and Filtering by Segment (Gender, Country, Fraud, etc.)
    5.	Profit and Order Trends Over Time
    6.	Top Customers Table by Order Value and Volume
  
       
**🧾Dataset Schema**
| Column Name       | Data Type   | Description                                                        |
| ----------------- | ----------- | ------------------------------------------------------------------ |
| OrderID           | Integer     | Unique identifier for each order                                   |
| Region            | Text        | Geographic region of the customer or store                         |
| Country           | Text        | Country where the order was placed                                 |
| CustID            | Integer     | Unique identifier for each customer                                |
| Customer\_Name    | Text        | Full name of the customer                                          |
| ProductSKU        | Text        | Stock keeping unit code for the product                            |
| Product\_Category | Text        | Category the product belongs to (e.g., Plants, Pots)               |
| OrderLineItem     | Integer     | Sequence number identifying items within an order                  |
| OrderQuantity     | Integer     | Quantity of the product purchased                                  |
| ProductCost       | Float       | Cost price of the product                                          |
| ProductPrice      | Float       | Selling price of the product                                       |
| OrderDate         | Date        | Date when the order was placed                                     |
| AcquisitionSource | Text        | Source/channel that acquired the customer (e.g., Google Ads, Meta) |
| TransactionID     | Integer     | Unique identifier for the payment transaction                      |
| Fraud             | Boolean     | Indicates if the order is flagged as fraudulent                    |
| PaymentMethod     | Text        | Method of payment (e.g., Card, PayPal, Bank Transfer)              |
| CardType          | Text        | Type of card used (e.g., Visa, MasterCard)                         |
| Gender            | Categorical | Gender identity of the customer                                    |



**⚙️Steps Taken to Build the Dashboard**
1.	Data Cleaning and Transformation (Power Query): 
  a.  Removed duplicates, handled null values.
  b.  Standardized date and numeric formats.
  c.  Created calculated columns:
      1.  TotalRevenue = OrderQuantity * ProductPrice,
      2.  TotalProfit = (ProductPrice - ProductCost) * OrderQuantity. .
      3.  FraudEncode = If(Fraud="True",0,1)
      4.  TransactionOrder = OrderQuantityProductPrice
      5.  TransactionwithNoFraud = FraudEncodeTransactionOrder
3.	Data Modeling: .
  a.  Star schema with one fact table and relevant dimension tables (e.g., Product Category, Country, Acquisition Source).
5.	DAX Measures Created:
       1.  PercentageTransactionwithNoFraud = sum(FraudEncode)/COUNT(FraudEncode)*100
7.	Visualization:
  a.  Bar charts, Donut charts, Line charts, Card KPIs, and interactive filters/slicers.
  b.  User-level interactivity with slicers for country, gender, fraud status, acquisition source, card type, and time filters.


**🔍 Key Insights**
1.	Plants are the highest-performing product category, accounting for 93% of total profit.
2.	The United States and Australia generated the highest profits among all countries.
3.	Google Ads drives the most profitable and voluminous transactions.
4.	Only 4.66% of revenue is linked to fraud, indicating effective fraud control.
5.	Notable profit dip observed in late 2022, despite high order quantities.
6.	A few customers significantly impact revenue, suggesting high-LTV (lifetime value) users.


**📌Recommendations**
1.	Product Strategy: Double down on Plants category through targeted promotions and bundled sales with low-performing categories like Pots.
2.	Customer Retention: Launch loyalty programs or exclusive offers for high-value repeat customers.
3.	Marketing Optimization: Allocate more budget to Google Ads, and investigate why Meta and YouTube campaigns underperform.
4.	Geographic Targeting: Increase inventory and campaign intensity in top regions (USA, Australia).
5.	Trend Monitoring: Investigate causes behind profit drop post-July 2022 (e.g., rising costs, seasonality, fraud spikes).
6.	Fraud Management: Maintain current fraud controls and continue monitoring, especially in Q3/Q4.


**🔗 Connect with Me** 
1.  I'm a medical doctor and data analyst with experience applying data science to public health and commerce.
2.  Open to collaborations and remote roles globally.
3.  🔗 LinkedIn Profile: www.linkedin.com/in/uchechukwu-efifie-b7420047
