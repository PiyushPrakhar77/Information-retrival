# TF-IDF Search and Retrieval Evaluation

## Overview
This notebook builds a simple ranked document-retrieval system using TF-IDF vectorization and cosine similarity. It accepts a user-entered query, ranks three sample documents by similarity, and evaluates binary relevance predictions using common classification metrics.

## Dataset
The notebook uses three manually defined documents:
- `d1`: “The quick brown fox jumps over the lazy dog”
- `d2`: “Never jump over the lazy dog quickly”
- `d3`: “A quick brown dog outpaces a quick fox”

The search query is entered by the user at runtime.

## Workflow
1. Combine the three documents and the user query.
2. Use `TfidfVectorizer(stop_words='english')` to create TF-IDF vectors.
3. Separate the document vectors from the query vector.
4. Compute cosine similarity between each document and the query.
5. Sort documents by similarity score in descending order.
6. Predict relevance as `1` when a document's similarity score is greater than zero, otherwise `0`.
7. Compare the predictions with the notebook's fixed labels `[1, 0, 1]` using precision, recall, accuracy, and F1 score.

## Requirements
- Python 3.8 or later
- NumPy
- pandas
- scikit-learn

## Run
1. Open `code.ipynb` in Jupyter Notebook or Google Colab.
2. Install the packages in `requirements.txt` if needed.
3. Run the cells in order and enter a search query when prompted.

## Limitations
- The corpus contains only three short, manually written documents.
- The relevance labels `[1, 0, 1]` are hard-coded and may not match every user-entered query.
- Any positive cosine similarity is treated as relevant, so the relevance threshold is very permissive.
- Because the query is included in `fit_transform`, the vocabulary and IDF statistics are computed over both documents and the current query. This is a simple demonstration rather than a production retrieval evaluation.
