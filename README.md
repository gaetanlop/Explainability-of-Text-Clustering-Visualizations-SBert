# Explainability-of-Text-Clustering-Visualizations-SBert

## Related Work
Recently, pretrained transformer models like BERT (Devlin et al., 2019) have shown great performances to generate sentence embeddings for text clustering (Reimers and Gurevych, 2019). Since then, a lot of clustering approaches leveraged the dense vector representations generated by pre-trained bidirectional transformers. Khaustov et al. (2020) proposed two methods based on BERT for news clustering. Subakti et al. (2020) compared BERT and TF-IDF as data representation of text clustering and found out that BERT outperformed TF-IDF on most of the metrics explored. Shi et al. (2021) developed a self-supervised document clustering approach based on BERT. Mehta et al. (2021) combined TF-IDF and BERT to improve clustering performance on large datasets.\n
In this part, we introduce a method that combines dense vector representations with sparse vectors to improve the interpretability of clustering results. To the best of our knowledge, only BERTopic (Grootendorst, 2022) seems to combine SBERT (Reimers and Gurevych, 2019) and TF-IDF for sentence embeddings and cluster explainability respectively. They used pre-trained transformer-based language models and a class-based TF-IDF to generate document embeddings and topic representations. Our approach also combines the performance of pre-trained transformers, but we use TF-IDF to create relevant features to improve the interpretability of cluster visualizations.

