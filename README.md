# Pizza Sales Analysis  

## Description  
This project analyzes pizza sales data using MySQL to uncover insights into customer preferences, sales trends, and popular menu items.  

## Table of Contents  
1. [Prerequisites] 
2. [Database Schema]  
3. [Data Sources]
4. [SQL Scripts]  
5. [Usage Instructions]
6. [Analysis Techniques] 
7. [Examples and Results]


## Prerequisites  
- MySQL Server (version 8.0 or later is recommended)  
- MySQL Workbench or any other MySQL client for running the scripts  

## Database Schema  
- **Tables:**  
  - `Orders`:   
    - `OrderID` (INT, Primary Key): Unique identifier for each order  
    - `order_Date` (DATE): Date of the order  
    - `order_time' (TIME): Time of the order
  - `order_details`:   
    - `order_details_id` (INT, Primary Key): Unique identifier ensuring each entry is uniquely identified 
    - `order_id` (INT): foreign key that connects the Order Details table to the Orders table,
                        allowing for the establishment of a relationship between each order detail and its corresponding order.
    - `pizza_id` (TEXT): Used to retrieve detailed information about the pizza associated with each order
    - 'quantity' (INT)
  - `Pizzas`:   
    - `PizzaID` (TEXT, Primary Key): Unique identifier for each pizza  
    - `Pizza_Type` (TEXT): Type/category of the pizza  
    - `Price` (DOUBLE): Price of the pizza
    - 'size' (TEXT): Describes the size of the pizza
  - `pizza_types`:   
    - `name` (TEXT): Represents the name of the pizza. 
    - 'ingredients` (TEXT): Lists the ingredients used in the pizza. 
    - `pizza_type_id` (TEXT): Enables filtering and sorting of pizzas based on their type
    - 'category' (TEXT):Indicates the category of the pizza, such as "veggie","classic" or "supreme", etc.

## Data Sources  
The data is sourced from simulated sales records for the year 2023, specifically designed for this analysis.  

## SQL Scripts  
- `sales_summary.sql`: Generates a summary of total sales by month and pizza type.  
- `top_pizza_items.sql`: Lists the top 10 most sold pizzas in the timeframe analyzed.  

## Usage Instructions  
1. Install MySQL server and MySQL Workbench.  
2. Configure a new connection in MySQL Workbench to connect to your database.  
3. Run the SQL scripts from the Workbench or any other MySQL client of your choice.  

## Analysis Techniques  
- Utilized aggregate functions like `SUM()` and `COUNT()` to analyze sales data.  
- Employed `JOIN` operations to combine relevant data from multiple tables.  

## Examples and Results  
- Example Query:   
```sql  
SELECT * FROM pizzas WHERE pizza_type_id='bbq ckn';
