This project explores how ChatGPT can assist in writing and analyzing SQL queries using a sample MySQL movie rental database. The goal was to practice prompt engineering and understand database structure by answering business-relevant analytical questions.

Objectives:
Practice prompt engineering using AI (ChatGPT)
Generate realistic business questions based on a movie rental schema
Use SQL to answer those questions
Validate query correctness

Explore an experimental method for structured prompt-query building

Sample Prompts and Output
This repository includes:
a) 4 structured prompt examples (based on different questioning techniques)
b) Validated SQL query that identifies top-performing movie categories
c) Experimental prompting method for query generation

Key SQL Query Example:

SELECT c.name AS category_name, COUNT(*) AS total_rentals
FROM rental r
JOIN inventory i ON r.inventory_id = i.inventory_id
JOIN film f ON i.film_id = f.film_id
JOIN film_category fc ON f.film_id = fc.film_id
JOIN category c ON fc.category_id = c.category_id
GROUP BY c.name
ORDER BY total_rentals DESC;

This query identifies the most rented movie categories.

Files in This Repo:
File	                                      Description
sql_prompts_analysis.md	         All prompts used (Q1–Q4) with ChatGPT
category_rentals_query.sql           	Final SQL query
query_validation_notes.txt	     ChatGPT evaluation of query correctness
(Optional) visualization.png	   Chart of top categories (if applicable)

Author Note
This was a guided exercise in combining LLMs + SQL for learning and analysis. It’s part of my training toward a Junior Data Analyst role, focusing on building practical skills with tools like SQL, ChatGPT, and MySQL. 
