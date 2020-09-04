---
title: "Text Prediction Using N-gram Models"
date: 2020-08-23
tags: [natural language processing, data science]
header:
    image: "/images/wordcloud.png"
excerpt: "Web application that predicts the next word of a partial sentence using N-gram language models"
mathjax: "true"
---
#####[GitHub]((https://github.com/candaceng/data-science-capstone)  

### Background

Around the world, people are spending an increasing amount of time on their mobile devices for email, social networking, banking and a whole range of other activities. SwiftKey builds smart keyboards that makes it easier for people to type on their mobile devices. When someone types:

"I went to the "

the keyboard presents three options for what the next word might be. For example, the three words might be gym, store, restaurant. The focus of this project is to understand and build a predictive text model like those used by SwiftKey.

The project analyzes a large corpus of text documents to discover the structure in the data and find how words are put together. It will cover two main topics:

1. Cleaning and analyzing text data
2. Building and sampling from a predictive text model  

--------------------------------------------------------------------------------  

### 1. Exploratory Analysis

Three text files containing collections of blogs, news, and tweets were read in and cleaned to create a corpus of text, which was used to construct N-gram models. The focus was on the frequency of words, unigrams, bigrams, and trigrams. A [word cloud](https://github.com/candaceng/data-science-capstone/blob/master/2.%20Web%20Application/R%20Presentation/wordcloud.png) and several [bar charts](https://github.com/candaceng/data-science-capstone/blob/master/2.%20Web%20Application/R%20Presentation/ngram-barcharts.png) were constructed in R for visual aid. A detailed walkthrough of the data cleaning and exploratory analysis processes can be found [here](https://rpubs.com/candaceng/exploratory-analysis). 

--------------------------------------------------------------------------------  

### 2. Web Application

The [web application](https://candaceng.shinyapps.io/Text_Prediction_Using_N-grams/) was built using Shiny. The user interface presents the predictive model that makes the best guess of what the next word of an incomplete sentence will be. Simply enter a partial sentence in the input field and the predicted next word will be generated in live time. Users can also view statistics of the text corpus by toggling between bar charts of the most frequently occurring N-grams. We currently support unigrams, bigrams, and trigrams.