# Query Expansion with WordNet for Information Retrieval

## Overview
This lab explores query expansion for Information Retrieval (IR) using WordNet synonyms. It compares document rankings for the ambiguous query `light` before and after adding synonyms.

## Dataset
The notebook defines three sample documents about different meanings of “light”:
1. Scientific light and wavelength in a laboratory.
2. Lightness, morning light, and a cheerful mood during a journey.
3. A firefighter using a light in a dark corridor and carrying light equipment.

## Workflow
1. Download WordNet and the Open Multilingual WordNet data through NLTK.
2. Create TF-IDF vectors for the three documents using `TfidfVectorizer(stop_words='english')`.
3. Display the highest TF-IDF terms in each document.
4. Calculate and print the pairwise cosine-similarity matrix for the documents.
5. Expand a query by adding WordNet synonyms for each token, removing duplicate terms.
6. Rank the documents by cosine similarity for the original query (`light`) and the expanded query.

## Requirements
- Python 3.8 or later
- NLTK
- NumPy
- scikit-learn

## Run
1. Open `IR_Lab06.ipynb` in Jupyter Notebook or Google Colab.
2. Install dependencies from `requirements.txt`.
3. Run cells from top to bottom. The first run requires internet access to download WordNet resources.

## Limitations
- The query expansion function collects synonyms from every WordNet synset for a word, without disambiguating the intended sense. This can add irrelevant terms.
- The expanded query is limited to the first 10 unique expanded terms when ranking, so ordering affects which terms are included.
- The notebook prints a conclusion that expansion improves retrieval, but it does not use relevance judgments or a formal retrieval metric to verify that claim.
- The document set is a small hand-written demonstration corpus.
