


# AYERA MILK Ltd- PL/SQL Window Functions Assignment

**NAMES:** Anitha Mushimiyimana
**ID:**27383
**COURSE:** PL/SQL
**DEPARTMENT:** Software Engineering
**DATE:**September 27,2025

Ayera Milk Ltd is a Rwandan dairy company that produces and distributes milk and dairy products such as yogurt, cheese, and fresh milk.  
As the company grows, it needs better tools to analyze customer purchases, sales performance, and product trends.  
Traditional reporting methods give totals, but they do not explain **who are the top customers, how sales change over time, or which products perform best in different regions**.  

This project applies **PL/SQL window functions** to Ayera Milk Ltd’s sales data in order to gain deeper insights that support business decisions.

## Table of Contents
1. [Introduction](#introduction)  
2. [Problem Definition](#problem-definition)  
3. [Success Criteria](#success-criteria)  
4. [Database Schema](#database-schema)  
5. [Window Functions Implementation](#window-functions-implementation)  
    - [Ranking Functions](#ranking-functions)  
    - [Aggregate Functions](#aggregate-functions)  
    - [Navigation Functions](#navigation-functions)  
    - [Distribution Functions](#distribution-functions)  
6. [Results Analysis](#results-analysis)  
7. [References](#references)  

## Step 1: Problem Definition
### Business Context

**Company:**AYERA MILK Ltd
**Department:** Sales and Distribution
**Industry:**Dairy Production and Marketing
**Location:**Rwanda,East Africa

### Data Challeng


Even though every sale is recorded, **Ayera Milk Ltd** struggles to generate meaningful insights from its data. The company faces challenges in: Identifying top-selling dairy products per region and per quarter,Tracking monthly sales growth and detecting trends over time,  Segmenting customers for marketing and loyalty programs based on purchasing behavior.  

Without these insights, management cannot fully optimize product distribution, design targeted promotions, or strengthen customer retention strategies.  

### Expected Outcome
Provide insights into top products, customer segments, and regional trends to improve inventory planning and marketing strategies and it will help to improve our products and services.

## Step 2: Success Criteria

1. **Top 5 dairy products per region** → Using `RANK()` function to identify best-selling products in each region.  
2. **Running total of monthly milk sales** → Using `SUM() OVER()` function to track cumulative sales each month.  
3. **Month-over-month sales growth** → Using `LAG()` function to calculate percentage change in sales compared to the previous month.  
4. **Customer segmentation by purchase frequency** → Using `NTILE(4)` function to divide customers into quartiles for targeted marketing.  
5. **3-month moving average of milk sales** → Using `AVG() OVER()` function to monitor short-term sales trends and seasonality.


## Step 3: Database Schema
### Table Descriptions

| Table Name    | Purpose                  | Key Columns (PK/FK)                                               | Sample Data |
|---------------|--------------------------|------------------------------------------------------------------|-------------|
| customers     | Store customer info      | customer_id (PK), name, region                                    | 1001, Anitha Kell, Kigali |
|               |                          |                                                                  | 1002, Alice Wera, Huye |
|               |                          |                                                                  | 1003, Bosco Irakiza, Musanze |
| products      | Store product info       | product_id (PK), name, category                                   | 2001, Milk, Dairy |
|               |                          |                                                                  | 2002, Cheese, Dairy |
|               |                          |                                                                  | 2003, Yogurt, Dairy |
| transactions  | Record sales             | transaction_id (PK), customer_id (FK), product_id (FK), sale_date, amount | 3001, 1001, 2001, 2025-01-05, 2500 |
|               |                          |                                                                  | 3002, 1002, 2002, 2025-01-10, 4000 |
|               |                          |                                                                  | 3003, 1003, 2003, 2025-02-01, 3500 |

### ER Diagram - Ayera Milk Ltd 
+-----------+ +-----------+ +--------------+
| customers | 1 * | transactions | * 1 | products |
+-----------+----------+-----------+----------+--------------+
| customer_idPK |<---->| customer_idFK | | product_idPK |
| name | | product_idFK |<---->| name |
| region | | transaction_idPK | | category |
+-----------+ | sale_date | +--------------+
| amount |
+---------------+
---
## Step 4: Window Functions Implementation 
### Ranking Results
![alt text](<screenshots/Screenshot 2025-09-28 181715.png>)
![alt text](<screenshots/Screenshot 2025-09-28 190218.png>)

### Aggregate Results
![alt text](<screenshots/Screenshot 2025-09-28 192739.png>)
![alt text](<screenshots/Screenshot 2025-09-28 190321.png>)
### Navigation Results
![alt text](<screenshots/Screenshot 2025-09-28 193747.png>)
![alt text](<screenshots/Screenshot 2025-09-28 190421.png>)

### Distribution Results
![alt text](<screenshots/Screenshot 2025-09-28 195457.png>)
![alt text](<screenshots/Screenshot 2025-09-28 190505.png>)
---
## Step 5: SQL scripts data
### SQL scripts of data
![alt text](<screenshots/Screenshot 2025-09-28 200235.png>)
![alt text](<screenshots/Screenshot 2025-09-28 200249.png>)
![alt text](<screenshots/Screenshot 2025-09-28 200306.png>)
![alt text](<screenshots/Screenshot 2025-09-28 200535.png>)
![alt text](<screenshots/Screenshot 2025-09-28 200731.png>)
This is the table i created.
---
![alt text](<screenshots/Screenshot 2025-09-29 142312.png>)
![alt text](<screenshots/Screenshot 2025-09-29 144714.png>)
![alt text](<screenshots/Screenshot 2025-09-29 142333.png>)
![alt text](<screenshots/Screenshot 2025-09-29 145019.png>)
![alt text](<screenshots/Screenshot 2025-09-29 142351.png>)
![alt text](<screenshots/Screenshot 2025-09-29 144918.png>)
![alt text](<screenshots/Screenshot 2025-09-29 142418.png>)
This is the data i inserted.
---
## Step 6: Results Analysis
### Descriptive Analysis - What Happened?
**Key Findings:**
Fresh milk remains the highest-selling product, representing 45% of total sales.
Yogurt demand increased steadily, with an average 12% monthly growth.
Customers in the Southern Province made larger bulk purchases compared to other regions.
Top 5 distributors accounted for 50% of overall revenue.
### Diagnostic Analysis – Why?

Fresh milk is widely consumed daily, making it the backbone of sales.
Yogurt’s growth is driven by young consumers and schools adopting it in their menus.
Southern Province distributors benefit from organized cooperatives, which encourages collective bulk buying.
Large distributors get preferential delivery services, making them more consistent buyers.


### Prescriptive Analysis – What Next?

**-Strengthen Milk Supply Chains:** Ensure reliable cold storage and delivery trucks to meet rising fresh milk demand.

**_Target Youth Market:** Expand yogurt marketing campaigns in schools and universities.

**_Support Cooperatives:** Partner with cooperatives in the Southern Province to grow bulk distribution.

**_Distributor Incentives:** Offer loyalty rewards or rebates to top distributors to maintain their high purchase levels.

**_Product Diversification:** Introduce value-added dairy products (e.g., cheese, flavored milk) to reach new markets.
---
## Step 7: References
1.youtube tutorial[https://www.youtube.com/results?search_query=how+to+use+github]
2. orcale[http://127.0.0.1:8080/apex/f?p=4500:1003:1654333471078993::NO:::]
3. My business Idea ,it is in the process.
### Academic Integrity Statement
 “All sources were properly cited. Implementations and analysis represent original work. No AI
generated content was copied without attribution or adaptation."
---
**Repository:**https://github.com/anithamushimiyimana61-beep/plsql-window-functions--mushimiyimana---Anitha-