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

 - Derived sale(revenue) column (quantity × price)

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

# Techniques Used
- Relational data merging (primary–foreign key joins)

- Data Cleaning
  
- Time-based feature extraction

- GroupBy aggregation

- Revenue derivation

- Distribution analysis (histograms)

- Categorical comparison (bar charts)

- Peak detection and annotation

- Comparative analysis across temporal dimensions

# Visualizations
The project includes:

- Bar charts (demand by type and size)

- Revenue comparison visuals

- Time-series line charts

- Peak hour analysis charts

- Weekday vs weekend comparisons
Visualizations are designed for business readability and decision-making clarity.

# Business Impact
This analysis demonstrates how transactional restaurant data can be leveraged to:
- Optimize staffing during peak hours

- Improve inventory planning

- Identify high-performing products

- Support pricing strategy evaluation

- Detect revenue concentration risks

- Enhance demand forecasting

# Key Insights
 ## Menu Structure & Revenue Distribution
The menu includes 32 pizza types across 91 size variations (S, M, L, XL, XXL). Revenue is moderately distributed:
 - 	Highest revenue-contributing pizza type: Thai Chicken (5.3%)
 - 	Lowest revenue-contributing pizza type: Brie Carre (1.4%)
No single pizza dominates revenue excessively, indicating a moderately diversified demand structure rather than extreme SKU dependency.

 ## Pricing & Demand Relationship
A low negative correlation exists between price and quantity sold. This means: As price increases, quantity demanded tends to decrease. However, the relationship is weak that is, price alone does not fully describe demand.
This was observed from the analysis
 - 	Most demanded variant: Big Meat (Small) – $12.00
 - 	Least demanded variant: Greek Pizza (XXL) – $35.50
 - 	Most expensive variant overall: Greek Pizza (XXL) 
 - 	Least expensive variant: Pepperoni (Small) 
 - 	Most affordable pizza type on average: Big Meat
 - 	Most premium pizza type on average: Brie Carre
Customers are sensitive to extreme price (e.g., XXL variants), but mid-range pricing performs consistently well. This shows that Price matters, but it is not the only driver. There are likely to be more factors like; Value perception, flavor preference, and size which might play a stronger role than price alone.

 ## Category Performance

- Highest revenue contribution: Classic (26.9%)

- Lowest revenue contribution: Veggie (23.7%)

The gap between highest and lowest categories is relatively narrow, which indicates that Category-level performance is balanced. No category is underperforming severely, but Classic leads as the main category.

 ## Size Preference Dynamics
- Large (L) is the most purchased size.
- XXL is the least purchased size.
Customers constantly prefers Large indicating it represents the best perceived value-to-price ratio. XXL pricing likely exceeds customer willingness to pay for incremental size.

 ## Customer Purchase Behavior
- Average order size: 2.3 pizzas per order
- Average daily orders: 59
- Most orders contain 1–2 pizzas
- Orders of 5+ pizzas are statistical outliers 
This confirms that revenue is driven by steady transaction volume rather than bulk purchases.

 ## Product Preference Patterns
The two most frequently purchased variants are:
- BBQ Chicken (Medium)
- Big Meat (Small)
Both are in the mid-price range. This shows that customers prefer perceived value rather than extreme budget or premium offerings.

## Time & Seasonality Patterns
- Peak hour: Between 12 PM – 6 PM 

- Revenue highest on Fridays

- Highest average daily sales occur on Tuesdays

- Weekdays generate higher total sales than weekends and a slightly high sale on average than weekends. This suggests that weekdays bring more traffic and total revenue, but weekends bring customers who spend more per visit. 

- Peak sales month: July, followed by November

- Increasing decline observed in August

- Order frequency trend peaks around November

This shows that

 - Lunch and early evening are core revenue windows.

 - Friday drives total volume, but Tuesday shows stronger per-day average performance.

 - Seasonal lift in July suggests summer demand surge.

 - August dip may reflect seasonal travel or reduced foot traffic.

# Recommendations
- Consider repricing XXL variants Or introduce bundle discount for XXL
- Anchor promotions around Large size
- Focus product development within this mid-price tier
- Run seasonal promotions in August(Introduce back-to-school or summer-end campaigns or something)
- With AOV at 2.3 pizzas Implement “Buy 3 Save X%” campaigns
- Align staffing intensity with afternoon–evening demand
- Avoid overstaffing during low-volume hours
- Prepare inventory for July and November peaks

# Tools & Technologies

- Python

- Pandas

- NumPy

- Matplotlib

- Seaborn

- Jupyter Notebook

# Future Improvements

- Implement dashboard version (e.g., dash,Streamlit or Power BI)

- Add revenue concentration (Pareto) analysis

- Perform price elasticity modeling

- Introduce predictive forecasting

- Automate data pipeline


   

