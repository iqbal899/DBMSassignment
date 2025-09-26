# DBMSassignment
DBMS assignment to convert NL queries to SQL queries
## Project Readme

### Project Overview
This project demonstrates how to build and query a simple in-memory SQL database using Python, Pandas, and a pre-trained **text-to-SQL model** from Hugging Face. The goal is to translate natural language queries into executable SQL commands to retrieve data from a mock database. This assignment covers fundamental SQL concepts, from basic `SELECT` and `WHERE` clauses to more complex `JOIN` and **subqueries**.

---

### Technologies Used
* **Google Colab:** The primary environment for running the notebook.
* **Pandas:** Used for creating and managing the in-memory data tables (`DataFrames`).
* **PandasQL:** A library that allows running SQL queries directly on Pandas DataFrames.
* **Hugging Face `transformers`:** Used to load a pre-trained text-to-SQL model (`gaussalgo/T5-LM-Large-text2sql-spider`).

---

### Project Structure
The core of this project is a single Jupyter notebook (`.ipynb` file) that contains all the code and analysis.

1.  **Setup and Data Generation:** The notebook starts by installing necessary libraries (`pandasql`, `transformers`). It then creates two in-memory tables (Pandas DataFrames): `student` and `course`. The `course` table is linked to the `student` table via a `course_id` foreign key.
2.  **Schema Definition:** A `db_schema` string is defined in `CREATE TABLE` syntax. This string is not executed but serves as a **contextual prompt** for the Hugging Face model, helping it understand the database structure and relationships between tables.
3.  **Query Generation and Execution:** For each query, a natural language (NL) prompt is passed to the text-to-SQL model. The model generates an SQL query. This generated SQL is then executed on the Pandas DataFrames using `pandasql`, and the results are printed.

---

### Key Queries Explored

The notebook is divided into several sections, each demonstrating a specific type of query.

* **V1 - V5: Basic Operations**
    * Filtering with `WHERE`.
    * Ordering results with `ORDER BY`.
    * Aggregation with `AVG`, `COUNT`.
    * Grouping with `GROUP BY`.
* **V6: Multi-Table Queries**
    * Joining the `student` and `course` tables using a `JOIN` clause.
* **V7 - V10: Advanced Queries**
    * Handling synonyms (e.g., "show" vs. "list").
    * Comparative queries using **subqueries**.
    * Filtering by date and time.

---

### How to Run the Notebook
1.  Open the notebook in **Google Colab**.
2.  Run the cells sequentially to install dependencies, create the dummy data, and execute each query.
3.  Modify the natural language prompts to test the model's performance with your own queries.
