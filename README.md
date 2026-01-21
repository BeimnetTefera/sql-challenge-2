# 🍕 8 Week SQL Challenge - Case Study #2: Pizza Runner

![SQL](https://img.shields.io/badge/SQL-Advanced-blue)
![Databricks](https://img.shields.io/badge/Platform-Databricks-orange)
![Status](https://img.shields.io/badge/Status-Complete-success)

## 📖 Introduction

This repository contains my solutions for **Case Study #2: Pizza Runner** from Danny Ma's [8 Week SQL Challenge](https://8weeksqlchallenge.com/case-study-2/). 

Danny launched "Pizza Runner" - an Uber for Pizza concept combining "80s Retro Styling and Pizza Is The Future!" with a pizza delivery service. This case study focuses on cleaning messy data and using SQL to answer business questions about pizza metrics, runner performance, ingredient optimization, and pricing strategies.

## Database Schema

The Pizza Runner database consists of 6 main tables:

### Core Tables
- **`runners`** - Registration information for Pizza Runner delivery personnel
- **`customer_orders`** - Customer pizza orders with customizations (exclusions/extras)
- **`runner_orders`** - Order assignment and delivery details per runner
- **`pizza_names`** - Lookup table for pizza types (Meatlovers, Vegetarian)
- **`pizza_recipes`** - Standard toppings for each pizza
- **`pizza_toppings`** - Lookup table for all available toppings


##  Data Cleaning

Before answering business questions, significant data cleaning was required:

### Cleaned Tables
1. **`runner_orders_cleaned`**
   - Converted `'null'` strings to actual NULL values
   - Standardized distance and duration columns (removed units like 'km', 'minutes')
   - Cast distance and duration to appropriate numeric types
   - Normalized cancellation values

2. **`customer_orders_cleaned`**
   - Converted empty strings and `'null'` to NULL
   - Standardized exclusions and extras columns

## Case Study Questions

### A. Pizza Metrics (10 Questions)
1. How many pizzas were ordered?
2. How many unique customer orders were made?
3. How many successful orders were delivered by each runner?
4. How many of each type of pizza was delivered?
5. How many Vegetarian and Meatlovers were ordered by each customer?
6. What was the maximum number of pizzas delivered in a single order?
7. For each customer, how many delivered pizzas had at least 1 change and how many had no changes?
8. How many pizzas were delivered that had both exclusions and extras?
9. What was the total volume of pizzas ordered for each hour of the day?
10. What was the volume of orders for each day of the week?

### B. Runner and Customer Experience (7 Questions)
1. How many runners signed up for each 1 week period?
2. What was the average time in minutes it took for each runner to arrive at Pizza Runner HQ to pickup the order?
3. Is there any relationship between the number of pizzas and how long the order takes to prepare?
4. What was the average distance travelled for each customer?
5. What was the difference between the longest and shortest delivery times for all orders?
6. What was the average speed for each runner for each delivery?
7. What is the successful delivery percentage for each runner?

### C. Ingredient Optimisation (6 Questions)
1. What are the standard ingredients for each pizza?
2. What was the most commonly added extra?
3. What was the most common exclusion?
4. Generate an order item for each record in the customers_orders table (e.g., "Meat Lovers - Exclude Cheese")
5. Generate an alphabetically ordered comma separated ingredient list for each pizza order with 2x notation for duplicates
6. What is the total quantity of each ingredient used in all delivered pizzas sorted by most frequent first?

### D. Pricing and Ratings (5 Questions)
1. If a Meat Lovers pizza costs $12 and Vegetarian costs $10 with no charges for changes - how much money has Pizza Runner made?
2. What if there was an additional $1 charge for any pizza extras?
3. Design a ratings table allowing customers to rate their runner (1-5) - generate schema and sample data
4. Join all information together for successful deliveries (customer_id, order_id, runner_id, rating, order_time, pickup_time, preparation time, delivery duration, average speed, total pizzas)
5. Calculate Pizza Runner profit after paying runners $0.30 per kilometre

## Technologies Used

- **SQL** - Advanced queries including CTEs, window functions, string manipulation
- **Databricks** - Cloud-based analytics platform
- **Jupyter Notebook** - Interactive SQL development environment

## Key SQL Techniques Demonstrated

- **Data Cleaning**: String manipulation, type casting, NULL handling
- **Common Table Expressions (CTEs)**: Multi-level CTEs for complex transformations
- **String Functions**: `SPLIT()`, `EXPLODE()`, `CONCAT()`, `CONCAT_WS()`, `REGEXP_REPLACE()`
- **Aggregate Functions**: `COUNT()`, `SUM()`, `AVG()`, `MAX()`, `MIN()`
- **Date/Time Functions**: `TIMESTAMPDIFF()`, `HOUR()`, `DATE_FORMAT()`, `DATE_PART()`
- **Conditional Logic**: `CASE` statements for business rule implementation
- **Joins**: Multiple table joins including LEFT/INNER joins
- **Array Operations**: Using `LATERAL VIEW EXPLODE()` for array expansion

## Repository Structure

```
sql-challenge-2/
├── README.md                 # This file
└── week-2-code.ipynb        # Databricks notebook with all SQL solutions
```

## How to Use

1. **View the Solutions**: Open `week-2-code.ipynb` to see all SQL queries and solutions
2. **Run in Databricks**: Import the notebook into your Databricks workspace
3. **Execute Step-by-Step**: Run cells sequentially, starting with table creation and data cleaning


## Resources

- [Case Study #2: Pizza Runner](https://8weeksqlchallenge.com/case-study-2/)

## Author

Solutions implemented as part of the 8 Week SQL Challenge journey.

---

*Part of the [#8WeekSQLChallenge](https://8weeksqlchallenge.com/)*
