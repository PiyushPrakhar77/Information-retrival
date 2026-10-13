# TF-IDF and Cosine Similarity for Information Retrieval

## Overview
This notebook implements a small ranked-retrieval system. It preprocesses sample documents and a query, builds TF-IDF vectors, computes cosine similarity, and ranks documents by their similarity to the query.

## Dataset
The notebook defines five sample documents in Python:
- Document 1 combines information about Stanford University, California, Berkeley, MIT, and Harvard.
- Document 2 discusses artificial intelligence, machine learning, deep learning, healthcare, autonomous vehicles, and AI ethics.
- Documents 3–5 repeat the Berkeley, MIT, and Harvard passages already included in Document 1.
- Query: `top universities in California`

## Workflow
1. Download NLTK English stop words.
2. Lowercase text, remove non-alphabetic characters, split into tokens, remove stop words, and apply Porter stemming.
3. Build a vocabulary from the processed documents.
4. Calculate smoothed inverse document frequency: `log((N + 1) / (df + 1)) + 1`.
5. Calculate term frequency as term count divided by the number of processed words, then multiply by IDF.
6. Represent documents and the query as vectors over the same document vocabulary.
7. Calculate cosine similarity and rank documents from highest to lowest score.

## Requirements
- Python 3.8 or later
- NumPy
- NLTK

## Run
1. Open `code.ipynb` in Jupyter Notebook or Google Colab.
2. Install the packages listed in `requirements.txt` if needed.
3. Run the notebook cells in order. The first run may need an internet connection to download NLTK stop words.

## Limitations and implementation notes
- The TF-IDF vocabulary is built from the documents. Query terms not present in that vocabulary do not get their own vector dimensions.
- The notebook uses a custom TF-IDF weighting formula rather than scikit-learn's `TfidfVectorizer`.
- Documents 3–5 duplicate passages contained within Document 1, which can affect the ranking.
- This is a small demonstration corpus, not a large-scale search engine.
