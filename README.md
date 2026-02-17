#  Stock Price Movement Prediction using NLP

##  Problem Statement

Can daily financial news headlines predict next-day market direction?

This project evaluates whether aggregated daily news headlines contain predictive signal for next-day Dow Jones Industrial Average (DJIA) movement using classical Natural Language Processing (NLP) techniques.

The task is framed as a supervised binary classification problem:

- 1 → Market Up  
- 0 → Market Down  

---

## 🏗 Project Structure

---

## Dataset

- **Source**: Kaggle – Combined News DJIA Dataset  
- **Time Period**: 2008 – 2016  
- **Features**:
  - 25 daily news headlines per trading day
  - Binary market direction label (Up/Down)

Each day's 25 headlines were aggregated into a single text feature for modeling.

---

## Methodology

### 1️⃣ Data Preparation
- Aggregated Top1–Top25 headlines into a single text string
- Time-series train/test split (no shuffling to avoid look-ahead bias)

### 2️⃣ Text Preprocessing
- Lowercasing
- Stopword removal
- Lemmatization
- Punctuation removal

### 3️⃣ Feature Engineering
- TF-IDF Vectorization
  - max_features = 5000
  - Unigrams + Bigrams

### 4️⃣ Models Tested
- Logistic Regression (Baseline)
- Logistic Regression with class balancing
- Sentiment-only model (VADER)
- Rolling sentiment features

---

## Results

| Model | Accuracy |
|--------|----------|
| Naive Baseline (Majority Class) | ~51.8% |
| TF-IDF + Logistic Regression | ~49% |
| Sentiment Only | ~48% |
| Rolling Sentiment | ~48% |

None of the classical NLP approaches outperformed the naive baseline.

---

## Discussion

The results suggest that:

- Daily aggregated financial headlines do not provide statistically meaningful predictive signal for next-day market direction under linear lexical models.
- Short-horizon financial prediction is extremely noisy.
- Public macro news may already be efficiently incorporated into prices.
- Bag-of-words approaches are insufficient for capturing complex market dynamics.

This aligns with the difficulty documented in academic financial machine learning research.

---

## Future Improvements

- Transformer-based models (BERT / FinBERT)
- Intraday news alignment
- Event extraction instead of bag-of-words
- Multi-day (3-day / 5-day) prediction horizon
- Hybrid models combining technical indicators + news features
- Statistical significance testing of results

---

## Key Takeaways

- Proper time-series validation is critical.
- Avoiding data leakage is essential in financial ML.
- Baseline comparison prevents false confidence.
- Honest reporting of negative results demonstrates research maturity.

---

## Tech Stack

- Python
- Pandas
- Scikit-learn
- NLTK
- TF-IDF
- VADER Sentiment
- Google Colab

---

## Author

Jay Mishra  
Mechanical Engineering | Quantitative Finance Enthusiast  
