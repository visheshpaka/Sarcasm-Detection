# 📰 Sarcasm Detection in News Headlines

## 🤖 Overview

Sarcasm is a form of speech that means the opposite of what it says, often to mock or convey contempt. Detecting sarcasm in text is crucial for improving sentiment analysis, content moderation, and understanding natural human communication.

This project aims to build robust **Deep Learning models** to **classify news headlines as *sarcastic* or *non-sarcastic*** using advanced **Natural Language Processing (NLP)** techniques. Our final model achieved up to **80.1% accuracy** on unseen test data using **GloVe embeddings** and an **LSTM-based architecture**.

---

## 📚 Dataset

- **28,619** labeled headlines
- `is_sarcastic`: `1` if sarcastic, `0` otherwise
- `headline`: the news headline text
- Data sourced from **The Onion** (satirical) and **HuffPost** (real news)

 ---

## 🧼 Data Preprocessing

- Lowercasing all text
- Removing punctuation, numbers, stopwords, URLs, and HTML tags
- Lemmatization using `WordNetLemmatizer`
- Tokenization and feature engineering:
  - `headline_length`
  - `headline_tokens`
- Outlier removal (e.g., a 106-word headline)

---

## 📊 Exploratory Data Analysis (EDA)

- Class distribution (balanced dataset)
- Word clouds for sarcastic vs. non-sarcastic headlines
- Word length and character length distributions
- TF-IDF to extract top keywords in each category
- Top words: `trump`, `new`, `man`, `report`, `say`

---

## 🧠 Models Developed

| Model | Embedding | Architecture | Train Acc | Test Acc | Notes |
|-------|-----------|--------------|-----------|----------|-------|
| **Model 1** | None | BiLSTM + BiGRU | 99.4% | 78.5% | Overfitting observed |
| **Model 2** | None | Simple LSTM | 64.5% | 59.8% | Simplified but underperforms |
| **Model 3** | Word2Vec | BiLSTM + BiGRU | 63.7% | 64.0% | Slight improvement |
| **Model 4** | GloVe | BiLSTM | **83.1%** | **80.1%** | Best performance |

> ✅ **GloVe-based model** provided the best generalization with the highest test accuracy.

---

## 🧪 Sample Predictions

```python
headline = "Weather Report: Sunny Skies Expected Until Someone Makes Outdoor Plans"
→ Output: Sarcastic statement

headline = "Cloudy Skies Expected Until tomorrow"
→ Output: Non-sarcastic statement
```

---

## 🔍 Key Insights

- Pre-trained embeddings (especially GloVe) significantly improved performance.
- Complex models like BiLSTM + GRU tend to overfit on small datasets.
- Simpler models generalize poorly, even with regularization.
- TF-IDF and EDA revealed strong lexical signals tied to sarcasm.

---

## 📌 Future Work

- 🔁 **Ensemble methods** for boosting performance
- 🧠 **Transformer-based models** like BERT for contextual embeddings
- 📹 **Multimodal sarcasm detection** (text + audio/visual)
- 🌍 **Cross-domain and multilingual generalization**
- ⏳ **Longitudinal studies** of sarcasm trends in media

---

## 📎 References

- [Sciencedirect Sarcasm Detection Article](https://www.sciencedirect.com/science/article/pii/S2666651023000013)

---
