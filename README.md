# Sentiment-Analysis-of-IMDB-reviews-using-RNN-models

## Problem Statement¶
* Create a dataset loader for the IMDB reviews dataset here (You will need to write some python code to download and extract it in your notebook!). Use it to load the training/testing set, and break reviews up by words. (i.e., "This movie was terrible!" -> ["this", "movie", "was", "terrible"] -> torch.tensor([1, 8, 2, 9])

* Train some form of RNN model on the dataset. Its up to you to select the type, single-bidirectional, number of layers, etc. Explain your choices and show the comparisons that lead you to your conclusions! If you need to down sample the training set to make training faster, that is OK. Just explain why!

I used pytorch for this analysis.

I used RNN models like LSTM, bi-directional LSTM, GRU, bi-directional GRU to perform sentiment analysis of IMDB reviews. The dataset is segregated into 4 files each labelled training_positive, training_negative, testing_positive, testing_negative. I initially cleaned the data and removed stopwords, punctuations, converted them to lower case and split each sentence into individual words (tokens).Later, I created a vocabulary containing all unique words in the data with each word having a unique integer value (like a dictionary with words as keys and integers as values). I converted each review from words into an array of tensors and attached lables to them (0 for negative and 1 for positive) to identify the type of review. Finally, I loaded the tensor data to a data loader and employed embedding, pad&pack. I created different models by varying parameters like number of hidden layers, batch sizes, active nodes, learning rate and number of features to predict if a review is positive or negative.
