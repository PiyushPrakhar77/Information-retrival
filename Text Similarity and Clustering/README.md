# Document Clustering for Information Retrieval

## Overview
This notebook explores document clustering and similarity-based retrieval using TF-IDF features. It applies K-Means clustering to six short documents, assigns a test query to a cluster, computes document cosine similarities, and visualizes hierarchical relationships with a dendrogram.

## Sample documents
- **D1:** Information retrieval system
- **D2:** Retrieval models and ranking
- **D3:** Machine learning algorithms
- **D4:** Clustering and classification
- **D5:** Search engines and retrieval
- **D6:** Deep learning for NLP

**Test document:** `Retrieval and search systems`

## Workflow
1. **TF-IDF representation:** Use `TfidfVectorizer(stop_words='english')` to convert the six documents into vectors.
2. **K-Means clustering:** Fit `KMeans(n_clusters=3, random_state=42)` and print the cluster assigned to each document.
3. **Test-document assignment:** Transform the test text with the same vectorizer and predict its K-Means cluster.
4. **Cosine similarity:** Compute the pairwise cosine-similarity matrix for the six original documents.
5. **Hierarchical clustering:** Append the test vector, compute Ward linkage, and display a dendrogram.
6. **Most-similar document:** Calculate the test document's cosine similarity to each original document and identify the most similar document.

## Requirements
- Python 3.8 or later
- NumPy
- pandas
- scikit-learn
- SciPy
- Matplotlib

## Run
1. Open `code.ipynb` in Jupyter Notebook or Google Colab.
2. Install the dependencies listed in `requirements.txt`.
3. Run all cells in order to see the TF-IDF matrix, cluster labels, similarity matrices, dendrogram, and most-similar document.

## Implementation note
The final cell prints `Final Cluster` by looking up the cluster label of the most-similar original document. This is not necessarily the same as the test document's K-Means prediction printed earlier. If the goal is the test document's assigned cluster, use `test_cluster[0]`.

## Limitations
- The corpus has only six very short documents, so clustering results are illustrative.
- K-Means cluster IDs are arbitrary labels and do not imply a ranking.
- The dendrogram uses Ward linkage on TF-IDF vectors; its grouping is a separate hierarchical clustering view, not the same model as K-Means.
