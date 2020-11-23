# 202011_capstone_project
NeueFische Capstone Project-Spoiler detection

This project is the final project of the neue fische Data Science Bootcamp. The project was done in colaboration with [PsychOpilio](https://github.com/PsychOpilio/NF_Capstone_Spoiler_Detection)-please visit her profile for additional information.  
  
Have you ever skimmed through book reviews and suddenly found out that the gardener killed the house maid? Every reader's nightmare!  
This project aims to use text classification to identify spoilers in book reviews. As this is our first Natural language processing project, our main focus lies on getting to know different approaches of text processing and text classification.  

We used a dataset collected from public reviews on [goodreads](https://www.goodreads.com/) in late 2017 and is available [here](https://sites.google.com/eng.ucsd.edu/ucsdbookgraph/home). For more information about the dataset see:  
  * Mengting Wan, Julian McAuley, "Item Recommendation on Monotonic Behavior Chains", in RecSys'18.
  * Mengting Wan, Rishabh Misra, Ndapa Nakashole, Julian McAuley, "Fine-Grained Spoiler Detection from Large-Scale Review Corpora", in ACL'19.

The dataset contains 1.3 million reviews of about 25,000 different books by 19,000 users. Besides the review texts, which contain a spoiler or non-spoiler label for every sentence, the dataset alo contains book metadata (genre, title,..) and anonymized information on the user.  

## Table of Contents
* __data_preparation.ipynb__: Jupyter lab notebook containing infromation on combining data from different tables and some basic word frequency analyses
* __text_features_and_processing.ipynb__: Jupyter lab notebook containing information on tetx processing and analyses of text features
* __fasttext.ipnyb__: text classification using fasttext and computing word vectors based on the book descriptions and book review texts
*__sentence_classification.ipynb__: Classification of single sentences 
* __word_embedding.ipnyb__: text classification using word vectors and different classification algorithms for crime and 

