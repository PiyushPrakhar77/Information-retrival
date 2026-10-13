# Boolean Information Retrieval Using an Inverted Index

## Overview
This lab demonstrates a basic Information Retrieval (IR) system using an inverted index and Boolean queries in Python.

## Objectives
- Normalize document text by converting it to lowercase.
- Remove non-alphabetic characters.
- Build an inverted index mapping each term to the set of document IDs containing it.
- Retrieve documents using simple Boolean operators: `AND`, `OR`, and `NOT`.

## Implementation
1. **Text preprocessing** — `preprocess_text()` lowercases text, removes characters other than English letters and whitespace, and splits the text into words.
2. **Inverted index** — `build_inverted_index()` processes each document and stores the document IDs associated with each term.
3. **Boolean retrieval** — `boolean_query()` evaluates a simple sequence of terms and Boolean operators against the index.
4. **Sample documents and queries** — four small sample documents are indexed and queried.

Example queries in the notebook:
- `fox AND quick`
- `fox AND NOT lazy`
- `dog OR sunshine`

## Requirements
- Python 3.8 or later
- No third-party Python packages are required; the implementation uses the standard-library `re` module.

## Run
1. Open `IR_Lab02.ipynb` in Jupyter Notebook or Google Colab.
2. Run the cells from top to bottom.
3. Inspect the printed inverted index and Boolean query results.

## Limitations
- The Boolean query parser is intentionally basic. It does not fully parse arbitrary Boolean expressions, parentheses, or operator precedence.
- Query terms are split on whitespace and are not passed through the same preprocessing function as document text. For example, punctuation in a query may affect matching.
- The `NOT` behavior subtracts a term's postings from the current result set, so results depend on the order of tokens in the query.
- The sample corpus contains only four documents and is for demonstration, not performance evaluation.
