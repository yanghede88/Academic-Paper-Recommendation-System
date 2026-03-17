# Academic-Paper-Recommendation-System
Data Source

Paper metadata is collected from OpenAlex:

https://openalex.org

The project focuses on NLP-related papers.

Fetched fields include:

paper title

abstract

publication year

citation count

references

concepts

Database Setup

Create a PostgreSQL database before running the notebook.

Example:

CREATE DATABASE paper_recommendation;

Update database connection parameters inside the notebook:

DB_CONFIG = {
    "dbname": "...",
    "user": "...",
    "password": "...",
    "host": "...",
    "port": "5432"
}

Required tables are created automatically in notebook cells.
Required Python Packages

Install dependencies before execution:

pip install requests pandas numpy psycopg2-binary sentence-transformers tqdm scikit-learn gradio

Notebook Execution Order

Run notebook cells in the following order:

1. Fetch data from OpenAlex

This step retrieves paper metadata through OpenAlex API.

The API query can be adjusted by topic or publication year.

2. Store papers into PostgreSQL

This step inserts:

works

references

concepts

work_concepts

3. Generate embeddings

Abstract embeddings are generated using:

all-MiniLM-L6-v2

Only papers with abstracts are embedded.

Embeddings are stored in PostgreSQL.
