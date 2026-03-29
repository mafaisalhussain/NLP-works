# DATA 622 — Homework 7: NLP Article Analysis

**Course:** DATA 622 — Natural Language Processing | UMBC M.P.S. Data Science

Analyzes Sam Altman's TED 2025 interview using an LLM pipeline vs. classical NLP models.

**Article:** [VentureBeat — Sam Altman at TED 2025](https://venturebeat.com/ai/sam-altman-at-ted-2025-inside-the-most-uncomfortable-and-important-ai-interview-of-the-year/)

---

## Questions Answered
1. **Summary** — LLM-generated article summary (BART)
2. **Topics & Sentiment** — Key topics + BART vs. VADER vs. Naïve Bayes vs. SVM comparison
3. **Emotion** — Dominant emotion via DistilRoBERTa classifier
4. **Theme** — Main theme extracted via prompted BART completion

---

## Models Used
| Model | Purpose |
|-------|---------|
| `facebook/bart-large-cnn` | Summarization, topics, sentiment, theme |
| `j-hartmann/emotion-english-distilroberta-base` | 6-class emotion detection |
| VADER | Lexicon-based sentence sentiment |
| Naïve Bayes + SVM (TF-IDF) | Classical sentiment classification |

---

## Stack
`transformers` · `newspaper3k` · `vaderSentiment` · `scikit-learn` · `nltk` · `matplotlib`

---

## Run on Google Colab
> Requires **T4 GPU** — `Runtime → Change runtime type → T4`

Run cells top to bottom. BART model download (~1.6 GB) takes ~2 min on first run.

> **Note:** VentureBeat blocks scrapers. A full open transcript mirror (`singjupost.com`) is used as the data source.

---

## Author
**Mohammed Abdul Faisal Hussain** — UMBC M.P.S. Data Science  
[GitHub](https://github.com/mafaisalhussain) 
