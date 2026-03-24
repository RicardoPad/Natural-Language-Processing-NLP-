# 🎬 How Budget Influences Horror Narratives?
### A Text Mining Study of Horror Movie Descriptions (TMDB)

> Ricardo Padilla Herrera

---

## 🎯 Objective

Does **production budget** shape how horror movies are described in their marketing text?

Movie overviews are key informational assets on streaming platforms and theatrical releases — they shape audience expectations, affect click-through decisions, and signal the type of horror experience a viewer can expect. This analysis identifies **systematic differences in narrative framing** between high-budget and low-budget horror films.

---

## 🗃️ Dataset

**TMDB Movies Dataset (2023)** — available on [Kaggle](https://www.kaggle.com/)

| Field | Description |
|---|---|
| `overview` | Marketing synopsis (primary text corpus) |
| `budget` | Production budget in USD |
| `genres` | Film genre tags |
| `release_date` | Year of theatrical release |

**Filtering applied:**
- Horror genre only
- Films released after **1975** (modern blockbuster era)
- Budgets > $10,000 USD
- Split by budget percentile: **Low ≤ 20th** · **High ≥ 80th**

---

## 🔬 Text Preprocessing Pipeline (8 steps)

| # | Step | Purpose |
|---|---|---|
| 1 | **Lowercasing** | Normalize token case |
| 2 | **Noise Removal** | Remove URLs, punctuation, numbers |
| 3 | **Tokenization** | NLTK `word_tokenize` |
| 4 | **Stopword Removal** | Remove NLTK English stopwords |
| 5 | **Domain Stopwords** | Remove generic movie terms (*film, movie, story*) |
| 6 | **Short Token Filter** | Remove tokens < 3 characters |
| 7 | **Lemmatization** | Reduce to dictionary base form |
| 8 | **POS Filtering** | Retain only **nouns** and **adjectives** |

---

## 📊 Methods

- **Bag-of-Words** (CountVectorizer)
- **TF-IDF** — discriminative term weighting
- **Word frequency analysis** — top terms per budget group
- **LDA Topic Modeling** — latent thematic structure

---

## 🔑 Key Findings

- **High-budget** horror overviews emphasize supernatural entities and atmosphere (*demon, haunted, dark, ancient*)
- **Low-budget** horror relies more on psychological themes (*secret, missing, fear, truth*)
- Budget groups use **systematically different vocabulary** to frame horror narratives

---

## ⚙️ Requirements

```bash
pip install nltk pandas matplotlib seaborn scikit-learn gensim
```

---

## 📚 Reference Paper

> Ryoo, J. H., Wang, X., & Lu, S. (2021). *Do spoilers really spoil?* Journal of Marketing, 85(2), 70–88.
