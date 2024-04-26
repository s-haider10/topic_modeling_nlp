# Topic Modeling with Document Clustering and Dimensionality Reduction

This project aims to perform topic modeling on a collection of documents using document clustering and dimensionality reduction techniques. The process involves several key steps:

1. **Data Extraction and Preprocessing**: The PDF documents are processed to extract text data. This involves using the PyMuPDF library to read the PDFs and extracting text from each page. The extracted text is then preprocessed to remove noise, such as special characters and stopwords. Additionally, the text is tokenized, converted to lowercase, and lemmatized to normalize the text data.

2. **Embedding Generation**: Two embedding techniques, Word2Vec and BERT, are applied to convert the preprocessed text into numerical representations suitable for clustering. Word2Vec generates word embeddings based on the context of words in sentences, while BERT generates contextual embeddings for sentences. These embeddings capture semantic information about the text, which is crucial for clustering.

3. **Clustering and Dimensionality Reduction**: The document embeddings generated using Word2Vec and BERT are then clustered using KMeans clustering algorithm. Clustering helps group similar documents together based on their embeddings. Additionally, dimensionality reduction using Principal Component Analysis (PCA) is applied to visualize the clusters in a lower-dimensional space. PCA reduces the dimensionality of the embeddings while preserving their variance, making it easier to visualize and interpret the clusters.

4. **Visualization**: The clusters are visualized using a scatter plot, where each point represents a document and its position is determined by the reduced feature space obtained from PCA. The color of each point indicates the cluster to which the document belongs, allowing for easy interpretation of the clustering results.


## Usage

The main steps of the project include:        

1. **Data Extraction and Preprocessing**
2. **Embedding Generation**
3. **Clustering and Dimensionality Reduction**
4. **TF-IDF**
5. **Visualization**

## Acknowledgments

- Syed Ali Haider (sh6070) - Undergraduate
- Harsh Tambi (ht2293) - Undergraduate
- Big Data Science - Professor Anasse Bari
---
