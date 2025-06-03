# SQL Prompts and Analysis – ChatGPT + Rental Data

This document contains the full prompt history and responses used in analyzing the movie rental database.

---

## Question 1 – General Analytical Questions

Prompt:  
Using the provided MySQL database schema, generate a list of insightful SQL questions that can be answered using the data.

---

## Question 2 – Questions Focused on Increasing Rentals

Prompt:  
Using the provided MySQL database schema, generate a list of SQL questions that focus on identifying trends to increase video rentals.

---

## Question 3 – Query + Validation

Prompt 1: Which film categories generate the most rentals?  
Prompt 2: Write an SQL query to return category name and total rentals.  
Prompt 3: Analyze the correctness of this query using the schema.

Generated SQL query:
```sql
SELECT c.name AS category_name, COUNT(*) AS total_rentals
FROM rental r
JOIN inventory i ON r.inventory_id = i.inventory_id
JOIN film f ON i.film_id = f.film_id
JOIN film_category fc ON f.film_id = fc.film_id
JOIN category c ON fc.category_id = c.category_id
GROUP BY c.name
ORDER BY total_rentals DESC;
```

---

## Question 4 – Experimental Prompting Technique

Prompt 1: Identify relevant tables for rental activity and category.  
Prompt 2: Construct query logic based on relationships.  
Prompt 3: Generate SQL query that returns category and total rentals.

Generated SQL query:
```sql
SELECT c.name AS category_name, COUNT(*) AS total_rentals
FROM rental r
JOIN inventory i ON r.inventory_id = i.inventory_id
JOIN film f ON i.film_id = f.film_id
JOIN film_category fc ON f.film_id = fc.film_id
JOIN category c ON fc.category_id = c.category_id
GROUP BY c.name
ORDER BY total_rentals DESC;
```
