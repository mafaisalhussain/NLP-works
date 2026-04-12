#  DATA 622 

## Topic Modeling & NLP Analysis of Climate Change Article

---

##  Overview

This project analyzes a research article from *Frontiers in Sustainable Cities* using Natural Language Processing (NLP) techniques. The goal is to extract meaningful topics, visualize their relationships, and summarize the content using transformer-based models.

---

## 📄 Article Used

* *Towards Sustainable Cities: Climate Change Perspective in Achieving Sustainable Development Goal (Climate Action)*
* Source: https://www.frontiersin.org/journals/sustainable-cities/articles/10.3389/frsc.2023.1308684/full

---

##  Methodology

### 🔹 Step 1: Data Collection & Preprocessing

* Extracted text from the article using `BeautifulSoup`
* Converted text to lowercase
* Removed punctuation and numbers
* Tokenized text using `NLTK`
* Removed stopwords and short words
* Split article into **paragraph-level documents**

---

### 🔹 Step 2: Topic Modeling (LDA & LSI)

####  LDA (Latent Dirichlet Allocation)

* Created dictionary and corpus using `Gensim`
* Applied filtering (`no_below=2`, `no_above=0.5`)
* Trained LDA model with 5 topics

**LDA Topics:**

* Climate change impacts and pollution
* Urban sustainability and infrastructure
* Urban heat and land-use changes
* Green spaces and temperature regulation
* Environmental mitigation strategies

---

####  LSI (Latent Semantic Indexing)

* Built LSI model using same corpus
* Extracted semantic relationships between terms

**Insight:**
LSI revealed connections between climate change, urbanization, and environmental factors.

---

### 🔹 Step 3: Hierarchical Clustering

* Converted LDA topics into vectors
* Applied hierarchical clustering using `scipy`
* Visualized results using a **dendrogram**

**Results:**

* Cluster 1 → Climate change, pollution, health
* Cluster 2 → Urban development and sustainability

---

### 🔹 Step 4: LLM & Transformer-Based Analysis

####  Model Used:

* GPT-2 (via Hugging Face Transformers)

####  Summary Output:

> The article examines the impact of climate change on urban areas in India, highlighting issues such as rising temperatures, pollution, extreme weather events, and rapid urbanization. It discusses how vulnerable communities are disproportionately affected and emphasizes the role of sustainable urban planning, green infrastructure, and policy interventions. The study also outlines mitigation and adaptation strategies to address environmental challenges and achieve sustainable development goals.

---

##  Top Keywords

**Top 5 Keywords:**

* climate
* change
* urban
* india
* pollution

---

##  Key Findings

* Climate change and urbanization are deeply interconnected
* Urban heat and pollution are major challenges in Indian cities
* Sustainable infrastructure and policy interventions are essential
* Topic modeling effectively identified major research themes

---

##  Tools & Libraries Used

* Python (Google Colab)
* NLTK
* Gensim
* Scikit-learn
* Scipy
* Matplotlib
* Transformers (Hugging Face)

---

##  Conclusion

This project demonstrates how NLP techniques like LDA, LSI, clustering, and transformer models can be used to extract insights from research articles. The analysis highlights key environmental challenges and supports the importance of sustainable urban development.

---

##  How to Run

1. Open Google Colab
2. Install required libraries
3. Run preprocessing code
4. Execute LDA & LSI models
5. Generate clustering visualization
6. Run transformer-based summarization

---
