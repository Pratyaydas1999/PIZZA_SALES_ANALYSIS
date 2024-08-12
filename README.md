Overview

Welcome to the Pizza Sales Analysis project repository! This project explores the world of pizza sales through a comprehensive data analysis, revealing insights that go beyond the crust. Leveraging the power of
MySQL and Power BI, this repository showcases a deep dive into key performance indicators (KPIs), monthly trends, and categorical analyses to provide a holistic view of pizza sales data.


Features



Key Performance Indicators (KPIs)

Total Revenue:
SQL Query: SELECT ROUND(SUM(total_price), 2) AS Total_Revenue FROM pizza_sales;
Unveiling the financial success by summing up total sales.

Average Order Value:
SQL Query: SELECT ROUND(SUM(total_price) / COUNT(DISTINCT order_id), 2) AS Avg_order_value FROM pizza_sales;
Analyzing the average value per order to understand customer spending patterns.

Total Pizzas Sold:
SQL Query: SELECT SUM(quantity) AS Total_pizza_sold FROM pizza_sales;
Revealing the total quantity of pizzas sold, a key metric for demand.

Total Orders:
SQL Query: SELECT COUNT(DISTINCT order_id) AS Total_orders FROM pizza_sales;
Counting distinct orders to understand the overall order volume.

Average Pizzas Per Order:
SQL Query: SELECT ROUND(SUM(quantity) / COUNT(DISTINCT order_id), 2) AS Avg_pizzas_per_order FROM pizza_sales;
Calculating the average number of pizzas per order, a crucial insight for inventory management.

Monthly Trend for Total Orders
SQL Query: SELECT MONTHNAME(STR_TO_DATE(order_date, '%Y-%m-%d')) AS order_day, COUNT(DISTINCT order_id) AS total_order FROM pizza_sales GROUP BY order_day;
Unveiling the monthly trends in total orders, helping identify peak sales periods.

Percentage Sales by Pizza Category
SQL Query: SELECT pizza_category, ROUND(SUM(total_price), 2) AS total_revenue, SUM(total_price) * 100 / (SELECT SUM(total_price) FROM pizza_sales) AS PCT FROM pizza_sales GROUP BY pizza_category;
Analyzing sales distribution across different pizza categories, providing insights into customer preferences.

Percentage Sales by Pizza Size
SQL Query: SELECT pizza_size, ROUND(SUM(total_price), 2) AS total_revenue, ROUND(SUM(total_price) * 100 / (SELECT SUM(total_price) FROM pizza_sales), 2) AS PCT FROM pizza_sales GROUP BY pizza_size;
Breaking down sales by pizza size, allowing for strategic marketing decisions.

Software Used
MySQL: Utilized for robust data querying and manipulation.
Power BI: Transformed raw data into visually compelling and interactive dashboards.
Dashboard Development: Crafted dynamic visualizations to highlight key KPIs and trends.

How to Use
Clone the repository to your local machine.(git clone "Path of this file") type this to your terminal
Import the provided database (pizza_sales.csv) into your MySQL server.
Open the Power BI file (pizza_sales_analysis.pbix) to explore the interactive dashboard.

Feel free to explore, analyze, and customize the project as needed. If you have any questions or suggestions, please don't hesitate to reach out.


Happy analyzing! 
