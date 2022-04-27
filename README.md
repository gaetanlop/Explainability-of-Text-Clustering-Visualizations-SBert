# Explainability-of-Text-Clustering-Visualizations-SBert

## Related Work
Recently, pretrained transformer models like BERT (Devlin et al., 2019) have shown great performances to generate sentence embeddings for text clustering (Reimers and Gurevych, 2019). Since then, a lot of clustering approaches leveraged the dense vector representations generated by pre-trained bidirectional transformers. Khaustov et al. (2020) proposed two methods based on BERT for news clustering. Subakti et al. (2020) compared BERT and TF-IDF as data representation of text clustering and found out that BERT outperformed TF-IDF on most of the metrics explored. Shi et al. (2021) developed a self-supervised document clustering approach based on BERT. Mehta et al. (2021) combined TF-IDF and BERT to improve clustering performance on large datasets.

In this part, we introduce a method that combines dense vector representations with sparse vectors to improve the interpretability of clustering results. To the best of our knowledge, only BERTopic (Grootendorst, 2022) seems to combine SBERT (Reimers and Gurevych, 2019) and TF-IDF for sentence embeddings and cluster explainability respectively. They used pre-trained transformer-based language models and a class-based TF-IDF to generate document embeddings and topic representations. Our approach also combines the performance of pre-trained transformers, but we use TF-IDF to create relevant features to improve the interpretability of cluster visualizations.

## Our approach
Inspired by the topic model BERTopic (Grootendorst, 2022), we used SBERT (Reimers and Gurevych, 2019) to convert documents into dense vector representations and use those embeddings to cluster semantically similar documents. We then applied TF-IDF to generate the features for our word cloud visualizations. 

We applied the same preprocessing steps as in the TF-IDF configuration, except that we didn’t tokenize, lemmatize, or remove stop-words. The concatenation of tweets resulted in the creation of documents of more than 512 tokens (the maximum context length of SBERT [z]). Therefore, we splitted each document into chunks of 300 words. Each chunk was converted into a dense vector using SBERT. To reduce the dimensionality, we experimented with PCA, t-SNE and UMAP. We decided to apply UMAP for two reasons, it performed best in terms of purity/silhouette score and Allaoui et al (2020) revealed that it could improve K-means performance. As we wanted our results to be comparable with the bag-of-words model, we applied the best TF-IDF clustering configuration (k-means clustering with random starts, cosine metric and six clusters). To come back to the data preprocessing set up used in the previous method, we aggregated all chunks of tweets from each author and used a majority vote to assign them to a specific cluster. 

Figure x summarizes the different steps involved in the preprocessing and modeling of the SBERT configuration. Furthermore, average silhouette scores and purity scores are presented in Table x. Based on those metrics, vectors generated by SBERT lead to higher quality clusters than the ones generated using TF-IDF. In terms of silhouette score, the clusters are denser and better separated in the dense vector configuration than using sparse vectors. It suggests a higher quality of clusters (better cohesion and separation). In terms of purity, there is 6 points difference between the SBERT configuration and the TFIDF one. It suggests that the contextualized word representations generated by SBERT correlates better with the labels of our dataset (without any fine-tuning). 

![<img src="graph.png" width="500"/>](https://github.com/gaetanlop/Explainability-of-Text-Clustering-Visualizations-SBert/blob/main/images/graph.png)
<img src="https://github.com/gaetanlop/Explainability-of-Text-Clustering-Visualizations-SBert/blob/main/images/graph.png" width="300" height="300">
