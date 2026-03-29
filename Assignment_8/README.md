# DATA 622 — Homework 8: Article Similarity & NLP Analysis

**Course:** DATA 622 — Natural Language Processing | UMBC M.P.S. Data Science

Compares two climate change articles with opposing perspectives using AI/ML similarity metrics, sentiment analysis, emotion detection, and LLM summarization.

---

## Articles Used
| Source | Perspective |
|--------|-------------|
| [WMO — Climate Change Impacts 2024](https://wmo.int/media/news/climate-change-impacts-grip-globe-2024) | Mainstream science |
| [Heritage Foundation — Climate Rhetoric](https://www.heritage.org/climate/commentary/climate-change-the-science-doesnt-support-the-heated-rhetoric) | Conservative/skeptic |

> **Note:** The originally assigned URLs (NYT, Fox News) block automated scrapers (403/404). These open-access replacements cover the same topic with the same contrasting perspectives.

---

## Questions Answered
| # | Question | Method |
|---|----------|--------|
| 1 | Measure similarity between articles | TF-IDF Cosine, Sentence Embeddings, Jaccard |
| 2a | Do they share similar topics? | TF-IDF term overlap |
| 2b | Do they share similar sentiment? | VADER, Naïve Bayes, SVM |
| 2c | Do they share similar emotions? | DistilRoBERTa 6-class classifier |
| 3 | Top 5 keywords per article | TF-IDF |
| 4 | Summarize findings | BART LLM |

---

## Pipeline Overview
```
Article Extraction (newspaper3k)
        │
        ▼
  Raw Article Text
        │
   ┌────┴──────────────────────────────────┐
   ▼                                       ▼
Similarity Analysis               Sentiment & Emotion
  - TF-IDF Cosine                   - VADER (lexicon)
  - Sentence Embeddings             - Naïve Bayes (TF-IDF)
  - Jaccard                         - SVM / LinearSVC
                                    - DistilRoBERTa (emotion)
   └────┬──────────────────────────────────┘
        ▼
   Keyword Extraction (TF-IDF Top-5)
        │
        ▼
   BART LLM — Comparative Summary
        │
        ▼
   Visualizations
   - Similarity bar chart
   - Emotion grouped bar chart
   - VADER sentiment arc
```

---

## Models Used
| Model | Type | Purpose |
|-------|------|---------|
| `facebook/bart-large-cnn` | Seq2Seq LLM | Article summaries + comparative findings |
| `all-MiniLM-L6-v2` | Sentence Transformer | Semantic similarity embeddings |
| `j-hartmann/emotion-english-distilroberta-base` | Classifier | 6-class emotion detection |
| VADER | Lexicon-based | Sentence-level sentiment scoring |
| Naïve Bayes + SVM | Classical ML | Sentiment classification via TF-IDF |

---

## Tech Stack
`transformers` · `sentence-transformers` · `newspaper3k` · `vaderSentiment` · `scikit-learn` · `nltk` · `matplotlib` · `torch`

---

## Notebook Structure
| Cell | Description |
|------|-------------|
| 1 | Install packages & imports |
| 2 | Load BART, MiniLM, emotion classifier |
| 3 | Scrape & extract articles |
| 4 | Q1 — Similarity (TF-IDF, embeddings, Jaccard) |
| 5 | Q2a — Shared topics |
| 6 | Q2b — Sentiment comparison |
| 7 | Q2c — Emotion comparison |
| 8 | Q3 — Top 5 keywords |
| 9 | Q4 — BART summaries + comparative findings |
| 10 | Visualizations |

---

## Outputs
- Console tables for similarity scores, sentiment, emotion, and keywords
- `hw8_analysis.png` — 3-panel figure: similarity scores, emotion distribution, VADER sentiment arc

---

## Run on Google Colab
> Requires **T4 GPU** — `Runtime → Change runtime type → T4`

Run all cells top to bottom. BART model download (~1.6 GB) takes ~2 min on first run.

---

## Key Findings Summary
The two articles share overlapping vocabulary around climate and weather but differ sharply in framing and tone. The WMO article carries an urgent, data-driven narrative while the Heritage Foundation article takes a skeptical stance questioning policy responses. Sentiment and emotion scores reflect this divide — the mainstream article trends more negative/fearful in tone while the skeptic article trends more neutral/dismissive. Despite topical overlap, semantic similarity scores remain low, confirming the articles are framing the same subject from fundamentally different perspectives.

---

## Author
**Mohammed Abdul Faisal Hussain** — UMBC M.P.S. Data Science  
[GitHub](https://github.com/mafaisalhussain) 
