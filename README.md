## 📊 Sales Performance Dashboard — Excel, Power BI, SQL & Python

 -- An end-to-end analytics project examining 500 sales transactions (Jan–Dec 2025) across regions, product categories, payment modes, and a 10-person sales team to uncover revenue concentration, leakage points, and profit drivers.

# 🖼️ Dashboard Preview

<img width="549" height="431" alt="{8EA63D8E-2CA8-4567-82C8-C345EAF99850}" src="https://github.com/user-attachments/assets/8e41a700-adf1-4504-891c-ebae5594c890" />


# 🛠️ Tech Stack & Workflow
1. Python (Pandas): Exploratory data analysis, cleaning raw transactional data, and establishing database connections.

2. Microsoft Excel: Initial data validation and cross-tab exploratory PivotTables.

3. Power BI Desktop: Data modeling, Power Query, 15+ custom DAX measures, time-intelligence, and an interactive dashboard.

4. PostgreSQL: Advanced analysis using 27 queries covering window functions (RANK, LAG), CTEs, subqueries, Pareto (80/20) analysis, and table joins.

# 📌 Key Business Insights
1. Revenue Concentration: Laptops drive ~29% of total revenue. Just 6 of 20 products account for ~80% of revenue (confirmed via Pareto SQL analysis).
2. Seasonality: October peaked at ₹30.7L in sales—over 3× May’s ₹8.1L low.
3. Order Leakage: 9.6% of orders are cancelled, representing ₹22.7L in lost revenue, with the West region accounting for over half of it.
4. Team Performance: Every salesperson maintains a consistent profit margin between 21% and 25%.

📁 Dataset

sales-performance-dashboard/

├── README.md

├── SalesPerformanceDashboard.pbix       ← Power BI Interactive Dashboard

├── analysis.ipynb                       ← Python Data Cleaning & Exploration Notebook

├── data/

│   └── Dashboard_SalesPerformance.xlsx  ← Source dataset

├── sql/

│   ├── schema.sql                       ← PostgreSQL table & index definitions

│   ├── queries.sql                      ← 27 analytical PostgreSQL queries

│   └── sales_performance.csv            ← Cleaned dataset for SQL import

└── screenshots/

   └── dashboard-overview.png

# 🚀 Quick Setup
 
 Python / EDA: Open analysis.ipynb in Jupyter to view data processing and database loading.
 
 Power BI: Open SalesPerformanceDashboard.pbix in Power BI Desktop.
 
 PostgreSQL: Execute sql/schema.sql, load sql/sales_performance.csv, and run sql/queries.sql

# 🎯 Business Questions Answered


•	What's the total sales, profit, and overall margin — and how does it trend month to month?

•	Which region and which product category drive the most revenue and profit?

•	What are the top-selling products by revenue, and how concentrated is that revenue?

•	Which salesperson generates the most profit — not just the most sales?

•	What share of orders are Delivered vs. Pending vs. Cancelled, and how much revenue does that represent?

•	Which region has the highest cancellation rate, and what's the revenue impact?

•	Which payment mode is used most, and does it correlate with order cancellations?

•	Who are the top customers by revenue, and how much of total sales do they represent?

•	(SQL) Do a small number of products account for a disproportionate share of revenue — and exactly how much? (Pareto / 80-20 analysis)

•	(SQL) How does actual quarterly revenue compare against a target, by region? (JOIN across a targets table)

# 🔑 Key Insights

•	October peaked at ₹30.7L in sales — more than 3× May's ₹8.1L low, the clearest seasonal swing in the year.

•	Laptops alone drive ~29% of total revenue — a single product carrying nearly a third of the topline, a concentration risk worth flagging.

•	Just 6 of the 20 products account for ~80% of total revenue (Laptop, Bed, Sofa, Monitor, Office Desk, Office Chair) — a textbook Pareto split, confirmed   
via cumulative-distribution SQL analysis.

•	West region accounts for over half of all cancelled-order revenue (₹11.6L of ₹22.7L total) — disproportionate to its share of orders, and a clear          
fulfilment issue to investigate.

•	Every salesperson holds a margin between 21–25% — consistent performance across the team rather than one standout or one laggard.

•	Top 10 of 50 customers generate ~39% of total revenue — meaningful customer concentration.

•	9.6% of all orders are cancelled, representing ₹22.7L in lost revenue; another 23% of booked revenue is still pending.


# 🧮 Core DAX Measures

DAX

•	Total Sales        = SUM(Sales_Dashboard[Total Sales])

•	Total Profit        = SUM(Sales_Dashboard[Profit])

•	Profit Margin %     = DIVIDE([Total Profit], [Total Sales])

•	Total Orders        = DISTINCTCOUNT(Sales_Dashboard[Order ID])

•	Avg Order Value     = DIVIDE([Total Sales], [Total Orders])

•	Cancellation Rate % = DIVIDE(CALCULATE([Total Orders], Sales_Dashboard[Order Status]="Cancelled")[Total Orders])

•	MoM Sales Growth %  = DIVIDE([Total Sales] - CALCULATE([Total Sales],DATEADD('Date'[Date], -1, MONTH)),CALCULATE([Total Sales], DATEADD('Date'[Date], -1, MONTH)))

# 📬 Connect

•	LinkedIn : www.linkedin.com/in/krarnv

•	Gmail : karnav513@gmail.com

