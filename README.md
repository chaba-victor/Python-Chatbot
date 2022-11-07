# Python Chatbot Project 
Today chatbots are everywhere, they are improving efficiency. Chatbot reduces the dependence on humans and can smartly answer the questions in real-time.

A chatbot is an intelligent piece of software that is capable of communicating and performing actions similar to a human. Chatbots are used a lot in customer interaction, marketing on social network sites, and instant messaging the client. There are two basic types of chatbot models based on how they are built; Retrieval based and Generative based models.

  Project: Python Chatbot

  Category: Machine Learning

  Programming Language: Python

  Tools & Libraries: Keras, Tensorflow, NLTK

  Front End: Python – Tkinter

  Back End: Python

  Prerequisites: Python, Machine Learning




# Python-Chatbot
A chatbot is an intelligent piece of software that is capable of communicating and performing actions similar to a human. 
Chatbots are used a lot in customer interaction, marketing on social network sites and instantly messaging the client. 
There are two basic types of chatbot models based on how they are built; Retrieval based and Generative based models.

1. Retrieval based Chatbots
A retrieval-based chatbot uses predefined input patterns and responses. It then uses some type of heuristic approach to select the appropriate response. 
It is widely used in the industry to make goal-oriented chatbots where we can customize the tone and flow of the chatbot to drive our customers with the best experience.

2. Generative based Chatbots
Generative models are not based on some predefined responses.
They are based on seq 2 seq neural networks. It is the same idea as machine translation. 
In machine translation, we translate the source code from one language to another language but here, we are going to transform input into an output. 
It needs a large amount of data and it is based on Deep Neural networks.

About the Python Project – Chatbot
In this Python project with source code, we are going to build a chatbot using deep learning techniques. 
The chatbot will be trained on the dataset which contains categories (intents), pattern and responses. 
We use a special recurrent neural network (LSTM) to classify which category the user’s message belongs to and then we will give a random response from the list of responses.

Let’s create a retrieval based chatbot using NLTK, Keras, Python, etc.


Prerequisites
The project requires you to have good knowledge of Python, Keras, and Natural language processing (NLTK). 
Along with them, we will use some helping modules which you can download using the python-pip command.

                          pip install tensorflow, keras, pickle, nltk

# Making a Chatbot in Python?
Now we are going to build the chatbot using Python but first, let us see the file structure and the type of files we will be creating:
Intents.json – The data file which has predefined patterns and responses.
train_chatbot.py – In this Python file, we wrote a script to build the model and train our chatbot.
Words.pkl – This is a pickle file in which we store the words Python object that contains a list of our vocabulary.
Classes.pkl – The classes pickle file contains the list of categories.
Chatbot_model.h5 – This is the trained model that contains information about the model and has weights of the neurons.
Chatgui.py – This is the Python script in which we implemented GUI for our chatbot. Users can easily interact with the bot.

Here are the 5 steps to create a chatbot in Python from scratch:

Import and load the data file
Preprocess data
Create training and testing data
Build the model
Predict the response

1. Import and load the data file

First, make a file name as train_chatbot.py. We import the necessary packages for our chatbot and initialize the variables we will use in our Python project.

The data file is in JSON format so we used the json package to parse the JSON file into Python.
                               import nltk
                               from nltk.stem import WordNetLemmatizer
                               lemmatizer = WordNetLemmatizer()
                               import json
                               import pickle

                               import numpy as np
                               from keras.models import Sequential
                               from keras.layers import Dense, Activation, Dropout
                               from keras.optimizers import SGD
                               import random

                               words=[]
                               classes = []
                               documents = []
                               ignore_words = ['?', '!']
                               data_file = open('intents.json').read()
                               intents = json.loads(data_file)
