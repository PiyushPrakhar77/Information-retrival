# Multinomial Naive Bayes Text Classification

## Overview
This notebook implements a simple Multinomial Naive Bayes classifier from scratch. It learns word frequencies from a small labeled text dataset, calculates class prior and smoothed conditional probabilities, and predicts the class of a test document.

## Dataset
The notebook uses four short training documents labeled with two classes:
- `c`: `Taipei Taiwan`, `Macao Taiwan Shanghai`
- `j`: `Japan Sapporo`, `Sapporo Osaka Taiwan`

The test document is `Taiwan Taiwan Sapporo`.

## Workflow
1. **Tokenization:** Convert text to lowercase and split on whitespace.
2. **Vocabulary and counts:** Build a vocabulary and count word occurrences per class.
3. **Class priors:** Calculate each class's fraction of training documents.
4. **Conditional probabilities:** Apply Laplace smoothing:
   `P(word | class) = (count(word, class) + 1) / (total words in class + vocabulary size)`
5. **Log posterior scores:** Add the log prior and log conditional probabilities for every test token. Log probabilities help avoid numerical underflow.
6. **Prediction:** Select the class with the highest log score.

## Requirements
- Python 3.8 or later
- No third-party packages required; the notebook uses Python standard-library modules `collections` and `math`.

## Run
1. Open `code.ipynb` in Jupyter Notebook or Google Colab.
2. Run all cells in order.
3. Review the vocabulary, class counts, priors, log posterior scores, and predicted class.

## Limitations
- The dataset contains only four short training documents, so results are illustrative rather than reliable.
- The model uses whitespace tokenization and does not handle punctuation or more advanced text normalization.
- The code does not explicitly handle words in the test document that are absent from the training vocabulary. With the current conditional-probability function, such words still receive a smoothed probability, but the denominator and vocabulary are based only on training data.
- The labels `c` and `j` are not explained in the notebook, so their real-world meaning should not be assumed.
