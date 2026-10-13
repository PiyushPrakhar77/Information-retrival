# Positional Indexing and Phrase Search

## Overview
This notebook demonstrates positional indexing for Information Retrieval (IR). It builds an index that records where each term occurs in each document, then uses those positions to answer exact phrase queries.

## Objectives
- Tokenize document text into lowercase terms.
- Build a positional index mapping each term to document IDs and word positions.
- Display each term's total occurrence count and postings.
- Search for a phrase by checking whether its terms occur consecutively in the same document.

## Dataset
The notebook uses three small, manually defined sample documents:
1. “The quick brown fox jumps over the lazy dog.”
2. “The lazy dog sleeps.”
3. “A quick brown dog outpaces a quick fox”

## Workflow
1. `build_comprehensive_positional_index(documents)` uses a regular expression to tokenize each document and stores zero-based word positions.
2. The index is printed with document IDs and positions converted to one-based numbering for readability.
3. `phrase_query_with_positions(positional_index, phrase)` finds documents where all phrase terms appear consecutively and returns their starting positions.
4. The notebook asks the user to enter a phrase query and displays matching documents and positions.

## Run
Open `code.ipynb` in Jupyter Notebook or Google Colab and run the cells from top to bottom.

## Requirements
- Python 3.8 or later
- No third-party packages are required; the notebook uses Python's standard-library `re` and `collections` modules.

## Important note
The first code cell currently has a syntax error: the `for` statement in `build_comprehensive_positional_index()` is missing a colon after `enumerate(documents)`. Add the colon before running the notebook. Also, the phrase-query function splits the query on whitespace rather than applying the same regular-expression tokenizer used for documents, so punctuation in queries may affect matching.
