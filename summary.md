# Answers to theory questions and problem results

## 1. What is the curse of dimensionality? 

Computation: Clustering algorithms applied to high-dimensional word embeddings may experience increased computational complexity. Many clustering algorithms involve distance computations between data points, which become computationally expensive in high-dimensional spaces. As the dimensionality of the word embeddings increases, the computational requirements for clustering also increase, leading to longer processing times and higher resource usage.

Distance Metrics: In high-dimensional spaces, distance metrics such as Euclidean distance become less informative. Distances between word embeddings tend to become more uniform, making it difficult to distinguish between similar and dissimilar words based on distance alone. Consequently, clustering algorithms that rely on distance-based similarity measures may struggle to accurately identify clusters in high-dimensional word embedding spaces.

Overfitting: High-dimensional word embeddings pose a risk of overfitting when used in clustering algorithms. With a large number of dimensions relative to the number of data points (i.e., words), clustering algorithms may capture noise or spurious relationships in the data, leading to the creation of artificial clusters that do not generalize well to unseen data. Overfitting can result in poor clustering performance and hinder the ability to extract meaningful insights from the word embeddings.

Noise: High-dimensional embeddings are more susceptible to noise and outliers, which can distort clustering results and affect cluster quality.

## 2. Explain in brief the embedding techniques you have used. 

Word2Vec: Word2Vec generates dense vector representations of words in a high-dimensional space. The word2vec() function tokenizes text into words, converts them to lowercase, and trains a Word2Vec model. Document embedding is computed by averaging word embeddings for words present in the model vocabulary.

BERT (Bidirectional Encoder Representations from Transformers): BERT learns contextualized representations of words in text. The bert() function preprocesses text and encodes it using a pre-trained BERT-based SentenceTransformer model. BERT embeddings capture contextual information and semantic relationships within the text at the sentence or document level.

## 2.2. Calculate the 3 most similar papers (using cosine similarity) using the embedding and provide a short analysis of whether or not the results are relevant (when you actually look at the document).

BERT: Top Three Most Similar Documents:
Document 9 and Document 11: Max Similarity Score: 0.9282512664794922
Both documents talk about Ion Beam and electron beam.

Document 2 and Document 12: Max Similarity Score: 0.9219457507133484
Both documents talk about Heat Production and Deuterium into Palladium and LENR.

Document 8 and Document 9: Max Similarity Score: 0.915703535079956
Both documents talk about Heat Production and Deuterium into Palladium.

Wrod2Vec: Top Three Most Similar Documents:
Document 20 and Document 25: Max Similarity Score: 0.9899647831916809
20 talks about Excess heat generated in the glow discharge plasma electrolysis and 25 talks about cold fusion to produce transmutation products as well as excess heat, vaguely related.

Document 2 and Document 13: Max Similarity Score: 0.9865404963493347
X-RAY EMISSION LASER BEAMS FROM SOLID-STATE CATHODE MEDIUM OF HIGH-CURRENT GLOW DISCHARGE while document 2 talks about Heat Production During Electrochemical Loading of Deuterium into Palladium, not similiar

Document 3 and Document 25: Max Similarity Score: 0.9862829446792603
Document 25 talks about EXCESS HEAT PRODUCTION IN Pd/D and palladium–deuteride and document 3 talks about Extensive evidence exists for cold fusion to produce transmutation products as well as excess heat and palladium–deuteride. Both similar.

## 3. From the two embedding models used, which model performs better? Why do you think so?

BERT:
Document pairs such as Document 9 and Document 11, Document 2 and Document 12, and Document 8 and Document 9 have high cosine similarity scores, indicating strong semantic similarity between the documents.
These pairs appear to be relevant as they discuss similar topics such as ion beam and electron beam, heat production, and deuterium into palladium, which suggests that BERT effectively captures the semantic relationships between documents.

Word2Vec:
Document pairs such as Document 20 and Document 25, Document 2 and Document 13, and Document 3 and Document 25 also have high cosine similarity scores.
However, the relevance of these pairs seems to vary. While some pairs discuss related topics such as excess heat generation and cold fusion, others have less apparent semantic similarity.
Document 20 and Document 25 appear to be less relevant as they discuss different aspects of heat generation and fusion processes.

Overall, BERT appears to perform better than Word2Vec. BERT embeddings provide more context-aware representations of text, allowing for a better understanding of semantic similarity between documents.BERT captures the nuances of language and can identify similarities in meaning even if the wording is slightly different, leading to more accurate similarity scores. Word2Vec, while effective in some cases, may struggle to capture the full semantic context of documents, leading to varying levels of relevance in the identified similar document pairs.

## 4. If you are using algorithms like KMeans, justify the choice of the number of clusters (hyperparameter) using the Elbow method or Silhouette Score.

We implemnted both the elbow and silhouette score. In the elbow method as the number of clusters increases, the inertia typically decreases. However, beyond a certain point, the rate of decrease slows down: The "elbow point" on the plot represents the optimal value of k. In the silhouette method the value of k that maximizes the average Silhouette Score is considered the optimal number of clusters. When both the Elbow method and Silhouette Score suggest the same optimal value of k (such as k=2 in our case), it provides stronger justification for the choice of the number of clusters as 2.


We are using a cocktail method, we are using the embeddings from w2v to get the most optimal number of cluster i.e 2. And then we are using embeddings from the BERT to take the k-means clustering. This approach is giving us the most accurate results. 
