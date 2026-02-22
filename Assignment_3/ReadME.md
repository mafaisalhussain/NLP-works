# DATA 622 — Homework 3
## Sentence Embeddings & Similarity Analysis


## Overview
This project demonstrates a basic Natural Language Processing (NLP) workflow using a real-world news article. The notebook retrieves article text, processes it into sentences, converts sentences into numerical representations, and measures semantic similarity using a pre-trained transformer model.

The article analyzed is a Washington Post report on the Air India plane crash survivor Vishwash Kumar Ramesh (June 13, 2025).



## Requirements

Install dependencies:

pip install sentence-transformers nltk newspaper3k lxml_html_clean scikit-learn matplotlib seaborn

### Libraries Used
- newspaper3k — article retrieval and parsing
- nltk — sentence tokenization
- sentence-transformers — pre-trained embedding model
- scikit-learn — TF-IDF vectorization and cosine similarity
- matplotlib / seaborn — similarity visualization



## How to Run

1. Open `DATA622_HW3.ipynb` in Jupyter Notebook or JupyterLab
2. Run all cells from top to bottom
3. Each section corresponds to a step in the assignment



## Assignment Tasks

### 1. Read the Article
The notebook retrieves the news article and loads the first 700 characters of the text.

### 2. Sentence Tokenization
The text is split into sentences using NLTK’s `sent_tokenize()`.

### 3. Feature Representation
Two types of representations are created:
- TF-IDF vectors for the first 10 sentences
- Transformer sentence embeddings using the `all-MiniLM-L6-v2` model (384-dimensional vectors)

### 4. Sentence Embeddings
Each sentence is encoded into a dense numerical vector.  
The first sentence embedding has shape: (384,)

### 5. Cosine Similarity
Cosine similarity is computed between the first and second sentence to measure semantic similarity.



## Learning Outcomes
This project demonstrates:
- Web text extraction
- Sentence tokenization
- TF-IDF representation
- Transformer-based embeddings
- Semantic similarity measurement using cosine similarity


## Course Information
Course: DATA 622  
Assignment: Homework 3  
Topic: NLP — Sentence Embeddings & Similarity



## License
This repository is for educational purposes only.
