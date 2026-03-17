# Academic-Paper-Recommendation-System
# README
1. OpenAlex API Fetch
   - Fetch paper metadata from OpenAlex using the public API
   - Retrieve title, abstract, publication year, citation count, references, and concepts
   - Focus on NLP-related papers for the recommendation dataset

2. PostgreSQL Storage
   - Store fetched paper metadata in PostgreSQL tables
   - Maintain separate tables for papers, citation relationships, and concept mappings
   - Enable structured querying for recommendation and analysis

3. Embedding Generation
   - Generate abstract embeddings for papers with available abstracts
   - Use the all-MiniLM-L6-v2 sentence-transformer model
   - Store 384-dimensional vectors in PostgreSQL for semantic similarity computation
