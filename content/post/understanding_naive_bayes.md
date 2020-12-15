+++
title = "Sentiment Analysis With Naive Bayes"
author = ["knarfamlap"]
date = 2020-11-02
tags = ["machine-learning", "classifiers", "nlp"]
draft = false
aliases = "/post/understanding-naiv-bayes-classifier"
+++


## What is sentiment analysis?

In sentiment analysis, we extract the positive or negative orientation that the writer expreses toward some subject.
The writter can express his orientation through a book, review, a youtube comment, and other mediums.

The simplest type of sentment analysis is with binrary classfication. In binary classfication, 0 denotes negative and 1 denotes postive Lets say you have the following sentences:

  - I loved this movie! It made me cry at the end. 

  - Complete garbage, I can't believe they showed this.

  - The sauce was ok but the dough was too cheewy.


You could say we can assign the first sentence the positive class or 1. For the second and third sentences, we could assign a negative class of 0. 

Assigning a classfication of 0 or 1 to a sentence is pretty straight for foward for humans to do, but how can we teach a computer to do the same? Here is where the Naive Bayes Classifier comes in handy. 

## Naive Bayes Classifier

Lets dive into a some quick details about the Naive Bayes Classifer.

The Naive Bayes Classifier is a **generative** classfier. This means that the classifiers tries to learn the model that generates the data. In the other hand you can have **discrimanitive** classfiers that learn features that are most useful to discciminate between different classes given an input. 

Lets say we want to hire a Naive Bayes classifier to predict whether a document (piece of text) is positve or nagetive. In order for the Naive Bayes to be useful, we have to make some simplying assumptions. 

### Assumptions
1. We have to represent each document as a **bag of words**. What this means is that if we are given a document, we entirely omit how the document was ordered and instead we keep the frequencies of words in each document.

Lets say we were given the documents "I like food" and "tacos are the best".

The bag of words model would forget how these documents are structured and simple count how many times each words appeared. 

The bag of words would store the following:
- i : 1, like: 1, tacos : 1, and so on. 



