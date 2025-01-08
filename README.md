# MySQL
(Continuing https://chatgpt.com/share/677df580-9120-8013-a08e-60daf80940d2 )
## 1. SELECT Statements

Concepts:

- The basic structure of a SELECT query.

- Selecting specific columns.

- Using DISTINCT to remove duplicate values.
```plaintext
-- Select all columns from a table

SELECT * FROM employees;

-- Select specific columns

SELECT employee_id, first_name, last_name FROM employees;

-- Remove duplicate values

SELECT DISTINCT department_id FROM employees;
```

## 2. Filtering Data with WHERE Clause

The WHERE clause allows you to filter rows based on conditions.

- Syntax:
```plaintext
SELECT column1, column2  
FROM table_name  
WHERE condition;
```
a. Operators:

-  =: Equals
-  Greater than / Less than( >/<)

- Greater than or equal / Less than or equal( >=/<=)

- BETWEEN: Within a range

- LIKE: Pattern matching
- IN: Match a list of values

-Example
```plaintext
SELECT *  
FROM sales  
WHERE amount > 1000;

SELECT *  
FROM products  
WHERE category = 'Electronics';

SELECT *  
FROM employees  
WHERE first_name LIKE 'J%';  -- Names starting with 'J'

SELECT * 
FROM your_table_name
WHERE date_column BETWEEN '2025-01-01' AND '2025-01-07';

```


## 3. Sorting Data with ORDER BY
Use ORDER BY to sort query results in ascending (ASC) or descending (DESC) order.
- Example
```plaintext
SELECT column1, column2  
FROM table_name  
ORDER BY column1 ASC, column2 DESC; --in col1 1st row will have smallest val & col2 will have max value
```


## 4. Aggregate Functions
### Aggregate functions summarize data, often used with GROUP BY.

Common Functions:

- COUNT(): Counts rows.

- SUM(): Calculates total.

- AVG(): Calculates average.

- MAX() / MIN(): Finds maximum / minimum value.

```plaintext

SELECT COUNT(*) AS total_sales  
FROM sales;

SELECT AVG(amount) AS average_sale  
FROM sales  
WHERE region = 'North';

SELECT MAX(salary) AS highest_salary  
FROM employees;
```

##  5. Grouping Data with GROUP BY
   
- The GROUP BY clause groups rows sharing a value into summary rows.
- Syntax
```plaintext
SELECT column1, aggregate_function(column2)  
FROM table_name  
GROUP BY column1;
```
![Screenshot 2025-01-08 085711](https://github.com/user-attachments/assets/0245fbe6-a18f-473a-b5eb-c3cc9ccb9bd7)

## 6. Filtering Groups with HAVING
- Use the HAVING clause to filter grouped data (used after GROUP BY).
- Syntax
```plaintext
SELECT column1, aggregate_function(column2)  
FROM table_name  
GROUP BY column1  
HAVING condition;
```

```plaintext
SELECT region, SUM(amount) AS total_sales  
FROM sales  
GROUP BY region  
HAVING SUM(amount) > 5000;
```


![Screenshot 2025-01-08 083516](https://github.com/user-attachments/assets/57cb6248-91e5-4791-b832-de745fedb963)



## 7. Aliases and Basic String Operations
### - Aliases: Assign temporary names to columns or tables using AS.
- Example :
```plaintext
SELECT first_name AS "First Name", last_name AS "Last Name"  
FROM employees;
```
### - String Functions:
 - CONCAT(): Combines strings.
   
 - UPPER() / LOWER(): Converts case.
   
 - SUBSTRING(): Extracts a portion of a string.
```plaintext
select concat(platform_id,'            ',platform) as Combined_table from bookings_info

SELECT CONCAT(first_name, ' ', last_name) AS full_name  
FROM employees;

SELECT UPPER(first_name)  
FROM employees;
```

