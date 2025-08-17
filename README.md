# Pizza_Sales_Dashoboard
## 🍕 Pizza Sales Dashboard 
### Table of Contents :
- Problem Statement 
- Datasource 
- Data Preparation
- Data Analysis (DAX)
- Data Visualization Dashboard
- Insights

### Problem Statement :
In this project, the goal is to create a Pizza Sales Dashboard in Power BI that provides insights into sales performance, customer behavior, and product demand.

The dashboard should help management answer key business questions such as:

- What is the total revenue and total orders?
- Which pizza categories and sizes are most popular?
- What are the best-selling pizzas (by revenue, quantity, and orders)?
- How does sales performance vary by day, month, and time?
- What is the average pizzas per order?

### Datasource :
Source: Pizza Sales Dataset

The dataset contains details of pizza orders including order date, pizza type, category (classic, supreme, etc.), size, quantity, price, Pizza ID and Order ID

### Data Preparation :

Data cleaning and transformation in Power Query Editor included:

- Removed unnecessary columns (e.g., duplicate identifiers).
- Changed data types (date for order_date, whole number for quantity, decimal for price fields).
- Standardized text fields (pizza categories, names).

## Data Analysis (DAX):
  
Measures used in  all visualization are:
 
- Total Revenue = `SUM('Pizza Sales'[total_price])`
- Total Orders =  `DISTINCTCOUNT('Pizza Sales'[order_id])`
- Total Quantity Sold =  `SUM('Pizza Sales'[quantity])`
- Avg Pizzas per Order =  `DIVIDE([Total Quantity Sold], [Total Orders], 0)`
- Revenue by Category =  `SUMMARIZE('Pizza','Pizza'[pizza_category],"Revenue",[Total Revenue])`
- Revenue by Size =  `SUMMARIZE('Pizza','Pizza'[pizza_size],"Revenue",[Total Revenue])`
- Top Pizza by Revenue =  `TOPN(5, SUMMARIZE('Pizza','Pizza'[pizza_name],"Revenue",[Total Revenue]), [Total Revenue], DESC)`
- Top Pizza by Orders =  `TOPN(5, SUMMARIZE('Pizza','Pizza'[pizza_name],"Orders",[Total Orders]), [Total Orders], DESC)`
- Top Pizza by Quantity =  `TOPN(5, SUMMARIZE('Pizza','Pizza'[pizza_name],"Quantity",[Total Quantity Sold]), [Total Quantity Sold], DESC)`

## Data Visualization (Dashboard) :

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Shows visualizations from Pizza Sales Dashborad :
| Pizza Sales dashboard (Overview) |
| ----------- |
| ![Pizza Sales Dashboard-1](https://github.com/rohitaage17/Pizza_Sales_Dashoboard/blob/main/Pizza_Sales_Dashboard.png) |

| Pizza Sales Dashboard (Best & Worst Sales Performance) |
| ----------- |
| ![Pizza Sales Dashboard-2](https://github.com/rohitaage17/Pizza_Sales_Dashoboard/blob/main/Best_Worst_Pizza_Sales.png) |

## Insights :

From the dashboard, the following insights were observed:

- Total Revenue from pizza sales was highest in July, while January showed the lowest revenue
- Large size pizzas generated the most revenue, while XL & XXL sizes had fewer sales but higher unit prices.
- Classic pizzas contributed the most to total revenue among all categories.
- The Thai Chicken Pizza was the top-selling pizza in terms of revenue.
- The Classic Deluxe Pizza was the most frequently ordered.
- Most orders were placed during evening hours (5–8 PM), showing peak demand at dinner time.
- Friday and Saturday recorded the highest sales, while Monday had the lowest.
- On average, customers ordered ~2.3 pizzas per order.


