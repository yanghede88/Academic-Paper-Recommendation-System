# Academic-Paper-Recommendation-System
# README

This notebook consists of three main stages. First, paper metadata is collected through the OpenAlex API, where NLP-related papers are fetched together with key metadata such as title, abstract, publication year, citation count, references, and concept labels. Second, the retrieved data is stored in PostgreSQL, where separate tables are created for papers, citation relationships, and concept mappings to support efficient querying and recommendation. Third, abstract embeddings are generated for papers with available abstracts using the all-MiniLM-L6-v2 sentence-transformer model, producing 384-dimensional vectors that are stored in the database for later semantic similarity computation during recommendation.
