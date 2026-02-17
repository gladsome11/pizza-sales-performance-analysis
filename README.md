# pizza-sales-performance-analysis
<img width="1000" height="500" alt="screenshot" src="https://github.com/user-attachments/assets/1b3cc410-af19-4819-9304-ab0c95f83d83" />

# Overview
This project presents a comprehensive exploratory and business-focused analysis of transactional pizza sales data. The objective is to uncover demand drivers, pricing dynamics, sales patterns, and time-based performance trends that can inform operational and strategic decision-making.
Using relational datasets (orders, order details, pizza_types and pizzas), this analysis transforms raw transactional data into actionable business insights.

# Business Objectives
The analysis addresses the following key business questions:

- Which pizza types and sizes drive the highest demand?

- Which pizza categories generate the most revenue?

- What is the pricing distribution across the menu?

- Is there a relationship between price and quantity sold?

- Which days generate the highest sales volume and revenue?

- What does the distribution of daily sales look like?

- What is the average order frequency?

- What are the peak sales periods during the day?

- How do sales vary between weekdays and weekends?

- How do sales vary monthly?

# Dataset Description
The dataset consists of four relational tables:
1. orders.csv
   - order_id – Unique identifier for each order
   - date – Date the order was placed
   - time – Time the order was placed

2. order_details.csv
   - order_details_id – Unique identifier for each pizza line item
   - order_id – Foreign key linking to Orders
   - pizza_id – Foreign key linking to Pizzas
   - quantity – Number of pizzas ordered
  
3. pizzas.csv
   - pizza_id – Unique pizza identifier
   - pizza_type_id – Foreign key that ties each pizza to its broader pizza type
   - size – Size of the pizza (Small, Medium, Large, X Large, or XX Large)
   - price – Price of the pizza in USD

4. pizza_types.csv
   - pizza_type_id – Unique identifier for each pizza type
   - name – Name of the pizza as shown in the menu
   - category – Category that the pizza fall under in the menu (Classic, Chicken, Supreme, or Veggie)
   - ingredients – Comma-delimited ingredients used in the pizza as shown in the menu (they all include Mozzarella Cheese, even if not specified; and they all include Tomato Sauce, unless another sauce is specified)


# Data Relationships
The data follows a relational structure:
- One order can contain multiple pizzas.

- Each pizza has descriptive attributes such as size, category, and price.

- The order_details table serves as the transactional fact table driving analysis.

# Features & Analytical Components
 ## Feature Engineering

 - Extracted day of week
 
 - Extracted hour of day

 - Derived revenue column (quantity × price)

 - Created weekday vs weekend indicators

 - Generated monthly features

 ## Demand & Product Performance
 
 - Total quantity sold by pizza type and size

 - Category-level sales performance

 - Size-level demand analysis

 - Identification of top-performing products

 ## Pricing & Sales Analysis

 - Menu price distribution analysis

 - Revenue contribution by product

 - Relationship between price and quantity sold

 - Total quantity vs total sales comparison

 ## Time Series Analysis

 - Sales by day of week

 - Revenue by day

 - Distribution of daily sales

 - Average order frequency

 - Peak hourly sales periods

 - Weekday vs weekend comparison

 - Monthly sales variation


   

