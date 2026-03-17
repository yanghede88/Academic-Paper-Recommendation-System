# Academic-Paper-Recommendation-System
# README

This notebook implements a research paper recommendation system that combines citation-based bibliometric methods with semantic similarity. The project uses paper metadata collected from OpenAlex through its public API, focusing primarily on NLP-related papers. For each paper, the system retrieves metadata including title, abstract, publication year, citation count, references, and concept labels, then stores the processed data in a PostgreSQL database for downstream recommendation.

To run the notebook, first create a PostgreSQL database and update the database connection parameters inside the notebook, including database name, username, password, host, and port. Required Python packages include `requests`, `pandas`, `numpy`, `psycopg2-binary`, `sentence-transformers`, `tqdm`, `scikit-learn`, and `gradio`. These can be installed using pip before execution.

The notebook should be executed sequentially from top to bottom. The first section fetches paper metadata from OpenAlex and inserts the cleaned results into PostgreSQL tables, including paper metadata, citation relationships, and concept mappings. The next section generates abstract embeddings using the `all-MiniLM-L6-v2` sentence-transformer model. Only papers with available abstracts are embedded, and the resulting 384-dimensional vectors are stored in the database.

The notebook also includes a Gradio-based demo interface that allows users to search by paper title and optionally filter by publication year range. The system returns ranked recommended papers together with explanation text indicating why each paper was selected.

Because OpenAlex does not provide abstracts for every paper, only papers with available abstracts are used in semantic similarity computation. If API requests fail due to rate limits, rerunning the affected cells usually resolves the issue. For reproducibility, it is recommended to execute all notebook cells in order starting from database setup through recommendation output.
