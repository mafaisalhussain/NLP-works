readme_content = f"""# DATA 622 — Homework 9
## NLP Analysis: Sentiment, Intent, Emotion & Topic Classification
### Article: AP News — *A look at Boeing's recent troubles after Air India crash*
> Source: [AP News](https://apnews.com/article/boeing-aviation-aircraft-air-india-crash-f12b20e65dc57ae655a1e0759b58938f)  
> Date: June 12, 2025

---

## 📌 Objective
Apply NLP methods to analyze a real-world news article across three dimensions:
1. Classify **sentiment**, **intent**, and **emotions**
2. Determine topical coverage: **technology**, **aviation**, and **policy**
3. Compare **LLM-based** vs **Deep Learning** methods

---

## 🛠️ Tools & Libraries

| Tool | Version | Purpose |
|------|---------|---------|
| `newspaper3k` | latest | Article extraction & NLP summary |
| `nltk` | latest | Sentence tokenization |
| `vaderSentiment` | latest | Lexicon-based sentiment (baseline) |
| `transformers` | latest | Transformer model pipelines |
| `torch` | latest | Deep learning backend |
| `matplotlib` | latest | Visualization dashboard |
| `seaborn` | latest | Plot styling |

---

## 🤖 Models Used

| Task | Model | Type |
|------|-------|------|
| Sentiment | VADER | Lexicon / Rule-based |
| Sentiment | `cardiffnlp/twitter-roberta-base-sentiment-latest` | LLM (Fine-tuned) |
| Intent | `facebook/bart-large-mnli` | LLM (Zero-Shot NLI) |
| Emotion | `facebook/bart-large-mnli` | LLM (Zero-Shot NLI) |
| Emotion | `j-hartmann/emotion-english-distilroberta-base` | Deep Learning (Fine-tuned) |
| Topic | `facebook/bart-large-mnli` | LLM (Zero-Shot NLI) |

---

## 📰 Article Extraction — newspaper3k
```python
from newspaper import Article
article = Article(URL)
article.download()
article.parse()
article.nlp()
```

| Field | Value |
|-------|-------|
| Title | A look at Boeing's recent troubles after Air India crash |
| Date | June 12, 2025 |
| Word Count | 534 words |
| Clean Sentences | 21 (after noise removal) |
| Keywords | boeing, crash, air, india, 787, max, jets, troubles |

---

## 📊 Results

### Q1 — Sentiment

| Method | Label | Score |
|--------|-------|-------|
| VADER (Lexicon) | **NEGATIVE** | compound = -0.2475 |
| RoBERTa (LLM) | **NEGATIVE** | 11/21 sentences negative |

**Interpretation:**  
Both methods agree the article is **negative** in sentiment.  
Driven by crash deaths, financial losses ($11.8B), criminal prosecution,  
and repeated safety failures across Boeing's product lines.

---

### Q1 — Intent

| Rank | Intent | Confidence |
|------|--------|------------|
| #1 | Investigating causes and analyzing evidence | **0.9973** |
| #2 | Informing and reporting facts | 0.9634 |
| #3 | Expressing editorial opinion | 0.9368 |
| #4 | Warning and alerting the public | 0.8615 |
| #5 | Advocating for policy or regulatory change | 0.8031 |

**Interpretation:**  
The article primarily **investigates Boeing's history of failures**  
while simultaneously **reporting facts** in AP News wire style.  
All 5 intents scored above 0.80 — reflecting a rich, multi-purpose article.

---

### Q1 — Emotions

#### LLM Zero-Shot (BART-MNLI)
| Rank | Emotion | Score |
|------|---------|-------|
| #1 | **Surprise** | 0.5748 |
| #2 | Grief | 0.3942 |
| #3 | Trust | 0.3332 |
| #4 | Anger | 0.3256 |
| #5 | Sadness | 0.3097 |

#### Deep Learning (DistilRoBERTa — Fine-Tuned)
| Rank | Emotion | Score |
|------|---------|-------|
| #1 | **Anger** | 0.7661 |
| #2 | Sadness | 0.6737 |
| #3 | Joy | 0.6702 |
| #4 | Neutral | 0.6574 |
| #5 | Fear | 0.5435 |

---

### Q2 — Topic Proportions

| Topic | Proportion | Key Sentences |
|-------|-----------|---------------|
| **Technology** | 46.0% | 787 batteries, Dreamliner engineering, MCAS sensor |
| **Aviation** | 45.7% | Crash narrative, MAX groundings, safety failures |
| **Policy** | 8.3% | DOJ criminal deal, regulators, production cap |

**Interpretation:**  
The article is **equally split between Technology and Aviation** (≈46% each),  
reflecting how deeply intertwined Boeing's engineering failures are  
with aviation safety outcomes. Policy plays a supporting role only.

---

### Q3 — Method Comparison

| Criterion | LLM Zero-Shot (BART-MNLI) | Deep Learning (DistilRoBERTa) |
|-----------|--------------------------|-------------------------------|
| Paradigm | NLI Inference | Supervised Fine-Tuning |
| Training needed | ❌ None | ✅ Labeled emotion corpora |
| Label flexibility | ✅ Any custom labels | ❌ Fixed 7 classes |
| Dominant emotion | Surprise | Anger |
| Second emotion | Grief | Sadness |
| Sentiment | NEGATIVE | NEGATIVE |
| Strength | Flexible, no labeled data needed | Higher precision on trained classes |
| Weakness | Lower calibration, NLI not ideal for emotion | Cannot generalize beyond 7 emotions |
| Overall agreement | ✅ Both detect negative sentiment and distress-related emotions |

**Key Insight:**  
- **BART-MNLI** sees **Surprise** first — it captures the *framing* of unexpected disasters  
- **DistilRoBERTa** sees **Anger** first — it captures the *language* of loss, prosecution, failure  
- Both are valid perspectives — they measure different aspects of emotion in text

---

## 📁 Files in This Repository

| File | Description |
|------|-------------|
| `DATA622_HW9.ipynb` | Main Colab notebook with all code |
| `hw9_dashboard.png` | Full NLP results visualization dashboard |
| `hw9_heatmap.png` | Sentence-level emotion heatmap |
| `README.md` | This file |

---

## 🔄 How to Reproduce

1. Open `DATA622_HW9.ipynb` in Google Colab
2. Set runtime to **GPU** (Runtime → Change runtime type → T4 GPU)
3. Run all cells in order
4. All outputs auto-saved to `/content/`
```bash
# Install dependencies
pip install newspaper3k transformers torch vaderSentiment matplotlib seaborn accelerate lxml_html_clean

# NLTK data
python -m nltk.downloader punkt_tab punkt stopwords
```

---

## 👤 Author
**DATA 622 — Machine Learning at Scale**  
Homework 9 | NLP Sentiment, Intent & Emotion Analysis  
*Spring 2025*
"""

# Write to file
with open('README.md', 'w') as f:
    f.write(readme_content)

print("✅ README.md generated successfully!")
print(f"   Characters : {len(readme_content)}")
print(f"   Lines      : {len(readme_content.splitlines())}")
print("\n📌 To download from Colab:")
print("   Files panel (left sidebar) → right-click README.md → Download")
