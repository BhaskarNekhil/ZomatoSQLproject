# Zomato Dataset Analysis with SQL

## Overview
This project utilizes a sample dataset from **Zomato**, a popular restaurant discovery and food delivery platform, to perform data analysis using SQL queries. We have 4 different data tables for analysis. By joining them as per requirements, we will discover key data solutions.

## Requirements
1. **SQL Database Engine:** (e.g., MySQL Workbench, PostgreSQL, or SQL Server)
2. **Zomato Dataset Tables:** Create table queries are available in the repository files.

## Database Setup
1. **Create Database:** Open your SQL database management system and create a new database.
2. **Execute Script:** Run the SQL script provided in the `zomato data files script.sql` file to build the necessary tables and populate the data.

## Sample Queries

### 1. Customer Visit Frequency
* **Question:** How many days has each customer visited Zomato?
```sql
SELECT userid, COUNT(DISTINCT created_date) 
FROM sale 
GROUP BY userid;
```

### 2. Total Customer Expenditure
* **Question:** What is the total amount each customer spent on Zomato?
```sql
SELECT 
    s.userid, 
    SUM(p.price) AS total_expenditure 
FROM sale AS s 
LEFT JOIN product AS p 
    ON s.product_id = p.product_id 
GROUP BY s.userid 
ORDER BY s.userid;
```

## Acknowledgments
This project was inspired by the need for analyzing restaurant data for better insights. Feel free to contribute, provide feedback, or customize the project according to your needs. **Happy coding!**
