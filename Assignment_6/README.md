# DATA 622 – Homework 6  
## Natural Language Processing: Story Generation

### Overview
This assignment explores two different approaches to automated story generation in Natural Language Processing (NLP):

1. **Markov Chain Story Generation**
2. **Large Language Model (LLM) Story Generation**

The goal is to understand the difference between traditional probabilistic text generation methods and modern deep learning language models.

The implementation was completed using **Python in Google Colab**.

---

# Exercise 1: Markov Chain Story Generation

### Objective
Generate a short story using a **Markov Chain model** trained on fairy tale text.

### Method
1. Load a fairy tale dataset (Grimm’s Fairy Tales from Project Gutenberg).
2. Preprocess the text (remove punctuation and convert to lowercase).
3. Build a **word-level Markov chain** that learns transitions between words.
4. Generate a story starting with the phrase:

> "Once upon a time there was a kingdom..."

### Key Concepts
- Markov Chains
- Word transition probabilities
- Random text generation
- Basic NLP preprocessing

### Output
The model produces a randomly generated story based on learned word transitions from the training text.

---

# Exercise 2: LLM Generated Story

### Objective
Use a **Large Language Model (LLM)** to generate a creative story answering:

> **Why Study Data Science Today?**

### Method
1. Install the `transformers` and `torch` libraries.
2. Load a pretrained **GPT-2 text generation model**.
3. Prompt the model to generate a creative story about the importance of studying data science.

### Key Concepts
- Large Language Models
- Prompt-based text generation
- Transformer models

---

# Technologies Used
- Python
- Google Colab
- Transformers Library
- PyTorch
- Requests
- Regular Expressions

---

# Files



**
---

# Summary
This assignment demonstrates two different paradigms of text generation:

| Method | Approach |
|------|------|
| Markov Chain | Probabilistic word transition model |
| LLM (GPT-2) | Deep learning transformer-based model |

The comparison highlights how **modern LLMs produce more coherent and context-aware stories**, while **Markov chains rely on simple probability-based transitions**.

