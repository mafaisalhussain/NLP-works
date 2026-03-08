# DATA 622 --- Homework 5

## Text Summarization Techniques

This project implements several **text summarization methods** on a news
article using Python and NLP libraries.\
The article is scraped from USA Today using the `newspaper3k` library
and summarized using both extractive and abstractive techniques.

**Article Source**\
https://www.usatoday.com/story/news/politics/2025/06/13/pete-hegseth-pentagon-invade-greenland-plan/84188458007/

------------------------------------------------------------------------

# Project Tasks

## 1. TextRank Extractive Summary

Implements the **TextRank algorithm**, a graph-based ranking approach
similar to PageRank.\
Sentences are represented as nodes and ranked based on similarity.

Libraries: - networkx - scikit-learn - nltk

------------------------------------------------------------------------

## 2. Frequency-Based Sentence Scoring

Sentences are scored using **word frequency importance** after removing
stopwords and punctuation.

Steps: 1. Tokenize text 2. Calculate word frequency 3. Score sentences
based on important words 4. Select top ranked sentences

------------------------------------------------------------------------

## 3. Abstractive Summary (Transformer)

Uses a pretrained **transformer model** to generate a new summary.

Model example: - `facebook/bart-large-cnn`

Library: - HuggingFace Transformers

------------------------------------------------------------------------

## 4. Lead‑3 Summary

A baseline method that selects the **first three sentences** of the
article.

------------------------------------------------------------------------

## 5. Manual Compression Summary

Reduces the article to approximately **20% of the original sentences**.

------------------------------------------------------------------------

## 6. LLM Summary

Uses a **large language model** to generate a natural language summary.

Example model: - `google/pegasus-xsum`

------------------------------------------------------------------------

# Technologies Used

-   Python
-   Google Colab
-   newspaper3k
-   NLTK
-   scikit-learn
-   networkx
-   HuggingFace Transformers
-   PyTorch

------------------------------------------------------------------------

# Installation

Install dependencies:

``` bash
pip install newspaper3k nltk networkx scikit-learn transformers torch
```

Download NLTK datasets:

``` python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
```

------------------------------------------------------------------------

# Running the Project

1.  Open the notebook in **Google Colab**
2.  Run the cells sequentially
3.  The notebook will:
    -   Scrape the article
    -   Process the text
    -   Generate summaries using six methods

------------------------------------------------------------------------

# Repository Structure

    Assignment_5/
    │
    ├── DATA622_HW5.ipynb
    ├── README.md

------------------------------------------------------------------------

# Learning Objectives

This assignment demonstrates:

-   Web scraping for NLP
-   Extractive summarization techniques
-   Graph-based ranking algorithms
-   Transformer-based summarization
-   Comparison of traditional NLP and LLM-based approaches
