# TV Script Generation Project

## Project Source

This repository contains project#1 related to Udacity's [Deep Learning Nanodegree program](). 

## Project Overview

In this project, you'll generate your own Seinfeld TV scripts using RNNs. You'll be using a Seinfeld dataset of scripts from 9 seasons. The Neural Network you'll build will generate a new, "fake" TV script.

## Project Instructions

Clone the repository and navigate to the downloaded folder.
	
	```	
		git clone https://github.com/udacity/deep-learning-v2-pytorch.git
		cd deep-learning-v2-pytorch/project-tv-script-generation
	```
	
## My Answer Method (Tuning hyperparameters of the model).

To decide between hyperparameters, I assigned random values to each one and tried to change just one parameter at a time. Then, I trained the model for two epochs.

The values as follows: sequence_length = 12, batch_size = 256, lr = 0.001, embedding_dim = 200, hidden_dim = 300, n_layers = 2

* First: I tried to change only the “sequence_length” to 30 and 15 and I found that the value of 30 took more training time and its training loss was greater than the value of 15.
* Second: I attempted to change “hidden_dim” to 100 and 200 and I noticed that value of 200 gave training loss less than the value of 100. The time-consuming of the value of 200 was the larger, however, it was close to the value of 100.
* Third: I tried to change “n_layers” to 3, however, the n_layers = 2 outperformed n_layers = 3 in both the time-consuming and accuracy.

As known, the large value of sequence length will give the model an opportunity to learn the text context. However, according to my observation, I noticed that the large value consumes too large time. So, I decided to set it equal to 12 to balance between time-consuming and loss value.

Hidden dimension refers to the number of features that the model detects, so a large value will allow the network to learn more features. Accordingly, I went with a value equal to 300.

Regarding the number of layers, as we mentioned before, two layers outperformed three layers, so I set n_layers = 2.

As for batch size, a small value will lead to a slow training process while a large value consumes more computational resources, therefore we need to trade-off between them. The common use is the range between 32 to 256, so I decided to pick 256.