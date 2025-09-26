## ChatGPT SQL Rental Analysis

This project explores how **ChatGPT** can assist in writing and analyzing SQL queries using a sample MySQL movie rental database.
The project also extends the analysis with **Python (pandas) to demonstrate how SQL and Python** can answer the same analytical questions in different ways.

Cílem projektu je ukázat, jak lze využít **AI nástroje (ChatGPT) a Python společně s SQL pro trénink analytického myšlení** a budování praktických dovedností v oblasti datové analytiky.

## Project Highlights / Hlavní přínosy projektu

**Practical SQL Training** – Wrote and validated SQL queries on a movie rental database (**MySQL schema**).
**Prompt Engineering with AI** – Used ChatGPT to generate and refine SQL queries based on structured prompts.
**Python (pandas) Integration** – Replicated SQL queries in pandas to validate results and strengthen Python data analysis skills.
**Business-Relevant Analysis** – Focused on identifying top-performing movie categories and rental trends.
**Validation Process** – Compared generated queries with schema to ensure correctness and reliability.
**Visual Documentation** – Added query screenshots, Python outputs and results for clarity and portfolio presentation.
**Bilingual Project** – Documentation available in both English and Czech for broader accessibility.

## Objectives:
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

## Key SQL Query Example and Python Example:

SELECT c.name AS category_name, COUNT(*) AS total_rentals  
FROM rental r  
JOIN inventory i ON r.inventory_id = i.inventory_id  
JOIN film f ON i.film_id = f.film_id  
JOIN film_category fc ON f.film_id = fc.film_id  
JOIN category c ON fc.category_id = c.category_id  
GROUP BY c.name  
ORDER BY total_rentals DESC;

import pandas as pd   

Malý dataset podobný Sakila

data = {"category": ["Action", "Comedy", "Drama", "Action", "Drama", "Comedy", "Action", "Drama", "Comedy", "Action"],
    "rental_id": [1,2,3,4,5,6,7,8,9,10]}  
    
df = pd.DataFrame(data)

print(df)

This query identifies the most rented movie categories.
### Visualization
![Query 3 Example](obrazek%20do%20ChatGpt_question3.JPG)
![Query 4 Example](obrazek%20do%20ChatGpt_question4.JPG)
![SQL File Example](obrazek_category_rentals_query.JPG)

## Python (pandas) Example
EN: Example of analyzing movie rental data with pandas. The dataset is grouped by film category to count total rentals, similar to the 
SQL query.
CZ: Ukázka analýzy dat o půjčovnách filmů pomocí pandas. Dataset je seskupen podle filmové kategorie pro výpočet počtu půjčoven, podobně 
jako SQL dotaz.

```python
import pandas as pd
## Malý dataset podobný Sakila
df_with_totals = df.merge(rentals_by_category, on="category")
print(df_with_totals)

   category  rental_id  total_rentals
0   Action          1              4
1   Comedy          2              3
2   Drama           3              3
3   Action          4              4
4   Drama           5              3
5   Comedy          6              3
6   Action          7              4
7   Drama           8              3
8   Comedy          9              3
9   Action         10              4


## Conclusion / Závěr

EN:
This project demonstrates how SQL and Python (pandas) can be used side by side to answer the same business question — which film categories generate the most rentals.
Through this exercise, I strengthened my skills in prompt engineering, SQL query validation, and Python data manipulation with pandas.
The combination of both tools adds value to my portfolio and shows versatility in working with data.

CZ:
Tento projekt ukazuje, jak lze SQL a Python (pandas) využít paralelně pro zodpovězení stejné obchodní otázky — které filmové kategorie generují nejvíce výpůjček.
Díky tomuto cvičení jsem posílila své dovednosti v prompt engineeringu, validaci SQL dotazů a práci s daty v Pythonu pomocí pandas.
Kombinace obou nástrojů přidává hodnotu mému portfoliu a dokládá mou všestrannost v oblasti datové analytiky.

## Learning Sources / Zdroje učení

EN: This project builds on knowledge gained from online courses and training:
Python for Everybody (University of Michigan, Coursera)
Generative AI Data Analyst Specialisation (Vanderbilt University, Coursera)
DaPython (PyLadies CZ, Charles University, Faculty of Mathematics and Physics)

CZ: Tento projekt vychází z poznatků získaných během online kurzů a školení:
Python for Everybody (University of Michigan, Coursera)
Generative AI Data Analyst Specialisation (Vanderbilt University, Coursera)
DaPython (PyLadies CZ, Matematicko-fyzikální fakulta Univerzity Karlovy)

Copyright © Denisa Pitnerová, 2025

