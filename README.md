# Explainability-of-Text-Clustering-Visualizations-SBERT

This repository contains supporting code, analysis and documentation for article ``Explainability of Text Clustering Visualizations – Twitter Misinformation Case Study''.

Content:

* 100_Preprocessing_Russian_Trolls.ipynb: This notebook is a reproduction of the preprocessing steps involved in the creation of the dataset. It follows what was done in the following notebook: https://github.com/KIZI/evaluation-of-comprehensibility/blob/master/clustering_analysis_v2/LINVILLWARREN-AlternativeB-full-100features.ipynb
* 100_Preprocessing_explode_tweets.ipynb: The goal of the notebook is to apply the preprocessing steps we developped in the paper for the SBERT configuration.
* 100_Generate_embeddings_explode.ipynb: Create the embeddings for each 300 chunks of tweets.
* 100_Clustering_explode_majority_vote.ipynb: Visualization and Clustering results