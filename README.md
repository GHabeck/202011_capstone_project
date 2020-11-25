# 202011_capstone_project
NeueFische Capstone Project-Spoiler detection

This project is the final project of the neue fische Data Science Bootcamp. The project was done in colaboration with [PsychOpilio](https://github.com/PsychOpilio/NF_Capstone_Spoiler_Detection)-please visit her profile for additional information.  
  
Have you ever skimmed through book reviews and suddenly found out that the gardener killed the house maid? Every reader's nightmare!  
This project aims to use text classification to identify spoilers in book reviews. As this is our first Natural language processing project, our focus lies on getting to know different approaches of text processing and text classification.  

We used a dataset collected from public reviews on [goodreads](https://www.goodreads.com/) in late 2017 and is available [here](https://sites.google.com/eng.ucsd.edu/ucsdbookgraph/home). For more information about the dataset see:  
  * Mengting Wan, Julian McAuley, "Item Recommendation on Monotonic Behavior Chains", in RecSys'18.
  * Mengting Wan, Rishabh Misra, Ndapa Nakashole, Julian McAuley, "Fine-Grained Spoiler Detection from Large-Scale Review Corpora", in ACL'19.

The dataset contains 1.3 million reviews of about 25,000 different books by 19,000 users. Besides the review texts, which contain a spoiler or non-spoiler label for every sentence, the data set also contains book metadata (genre, title,..) and anonymized information on the user.  

There are several challenges associated with this data set:  
* while all reviews are supposed to be in english, we found that a low percentage also contains or is completely written in other languages
* with only 6% spoiler reviews, the dataset is imbalanced
* reviews are very heterogeneous in terms of word composition
* a single spoiler sentence in a review spoils the whole review --> within the spoiler reviews only 25% of the sentences are labeled as spoilers on average
* what constitutes a spoiler might be very book/content-specific

Using different approaches we were able to predict spoilers at a recall of 0.8 and an overall accuracy of about 0.7 using different approaches. When using the whole review text a linear SVM classifier with SGD training on undersampled data yielded the best result. When we trained models on sentences from spoiler reviews, a Multinomial Naive Bayes classifier and a Ridge classifier trained on oversampled, count-vectorized training data gave the best results. Using these classifiers trained on the spoiler subset on all test reviews, the overall results were similar to the once obtained with the linear SVM trained on whole reviews. Combining the results of different approaches for a majority vote or using the probabilities/decision functions of different classifiers as input for supervised classification could not improve the overall results.   

Besides count and tfidf vectorization we also tested word vectors for classification of sentences from spoiler reviews of crime novels. With a recall of 0.66 and an overall accuracy of 0.66 the results were similar to other approaches, yet the model was not suited to be generalized on unseen crime novel reviews. 

Due to limited time we could only start text classification using a recurrent neural network. While we were able to set up a RNN, this model overfits on training data and did not yield better results. 

## Table of Contents
* __data_preparation.ipynb__: Jupyter lab notebook containing infromation on combining data from different tables and some basic word frequency analyses
* __text_features_and_processing.ipynb__: Jupyter lab notebook containing information on tetx processing and analyses of text features
* __fasttext.ipnyb__: text classification using fasttext and computing word vectors based on the book descriptions and book review texts
*__sentence_classification.ipynb__: Classification of single sentences 
* __word_embedding.ipnyb__: text classification using word vectors and different classification algorithms for crime and 
*__RNN_with_word2vec_embedding__: classification of sentences from spoiler reviews using an RNN and word2vec embedding vectors

