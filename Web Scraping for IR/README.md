# Web Text Extraction and Preprocessing for Information Retrieval

A Information Retrieval (IR) projecct that extracts text from a web page and preprocesses it for downstream text retrieval tasks.

## Project Overview

This notebook demonstrates a basic text-preprocessing pipeline:

1. **Web scraping:** Downloads a web page using `requests` and extracts readable text with Beautiful Soup.
2. **Tokenization:** Converts the extracted text to lowercase and splits it into word tokens using NLTK.
3. **Stop-word removal:** Removes common English stop words.
4. **Stemming:** Reduces tokens to their stems using NLTK's `PorterStemmer`.

The notebook currently processes the Natural Language Processing tutorial page from GeeksforGeeks:
`https://www.geeksforgeeks.org/nlp/natural-language-processing-nlp-tutorial`

## Project Files

```text
.
├── IR_lab01.ipynb
├── README.md
└── requirements.txt
```

## Requirements

- Python 3.9 or newer
- Packages listed in `requirements.txt`
- Internet access to fetch the source web page
- NLTK data resources: `punkt` and `stopwords` (downloaded by the notebook)

The version pins in `requirements.txt` are recommended reproducible versions; they are not claimed to be the exact versions used when the notebook was originally run.

## Setup and Run

1. Clone or download this project.
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Open `code.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
4. Run the cells from top to bottom.

The notebook downloads the NLTK resources with `nltk.download('punkt')` and `nltk.download('stopwords')`. Depending on the installed NLTK version, tokenization may also require the `punkt_tab` resource. If you encounter a `LookupError` mentioning `punkt_tab`, run:

```python
import nltk
nltk.download("punkt_tab")
```

## Main Functions

- `extract_text_from_url(url)`: fetches a URL, removes `script`, `style`, and `noscript` elements, and returns whitespace-normalized page text.
- `tokenize_text(text)`: lowercases the text and tokenizes it with `word_tokenize`.
- `remove_stopwords(tokens)`: filters out English stop words.
- `stem_tokens(tokens)`: applies Porter stemming to each remaining token.

## Notes and Limitations

- The notebook demonstrates preprocessing, not a complete search engine. It does not build an inverted index, rank documents, or evaluate retrieval quality.
- The URL is hard-coded in the current notebook; change the `url` variable to process another accessible page.
- Websites may block automated requests or change their HTML structure. Always respect a site's terms and scraping policies.
- Stemming can produce word fragments; stems are not always valid dictionary words.
