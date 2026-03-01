# NLP — Gettysburg Address

This assignment performs basic Natural Language Processing (NLP) analysis on the first two sentences of Abraham Lincoln’s Gettysburg Address using Python in Google Colab.

## Tasks Implemented
1. Tokenization (spaCy, benepar)
2. Part-of-Speech (POS) Tagging
3. Dependency Parsing
4. Constituency Parsing (benepar + NLTK)
5. Noun Phrase Extraction (spaCy noun chunks)
6. Short theory: CRF vs HMM

---

## Libraries Used
- Python 3.12
- spaCy 3.7
- benepar
- NLTK
- PyTorch
- HuggingFace Transformers

---

## Key Results
- spaCy used for tokenization, POS tagging, dependency parsing, and noun phrases
- benepar used to generate a Penn Treebank constituency parse tree
- Extracted meaningful noun phrases such as *our fathers*, *a new nation*, and *a great civil war*

---

## Problems Faced & Fixes

### 1. NumPy Conflict
**Error:** binary incompatibility (`numpy.rec`)
  
**Fix:**
```
pip install numpy==1.26.4
```

### 2. Transformers Version Issue
**Error:** `T5Tokenizer` attribute missing

**Fix:**
```
pip install transformers==4.38.2 tokenizers==0.15.2
```

### 3. spaCy + benepar Integration Failure
**Error:** `unregistered extension attribute 'parse_tree'`

**Fix:**  
Used benepar directly with NLTK instead of attaching it to the spaCy pipeline.

---

## Final Setup
| Tool | Purpose |
|------|------|
| spaCy | Tokenization, POS, dependency parsing, noun chunks |
| benepar + NLTK | Constituency parsing |

---

## Learning Outcome
This assignment demonstrated both NLP concepts and an important engineering lesson:  
**environment compatibility and dependency management are crucial in real-world NLP projects.**
