##  Problem Statement

The objective of this project is to evaluate whether daily financial news headlines can predict next-day market direction.

Using historical DJIA news headlines (2008–2016), we build classical NLP models to determine whether aggregated daily headlines contain predictive signal for next-day index movement.

The task is framed as a supervised binary classification problem:
- 1 → Market Up
- 0 → Market Down

##  Methodology

1. Aggregated 25 daily headlines into a single text feature per trading day.
2. Applied aggressive text preprocessing:
   - Lowercasing
   - Stopword removal
   - Lemmatization
   - Punctuation removal
3. Used TF-IDF vectorization (max_features=5000, bi-grams).
4. Performed time-series train/test split (no shuffling).
5. Trained Logistic Regression baseline model.
6. Compared performance against naive baseline.
7. Conducted additional sentiment-based experiments (VADER).
## Results

| Model | Accuracy |
|-------|----------|
| Naive Baseline (Majority Class) | ~51.8% |
| TF-IDF + Logistic Regression | ~49% |
| Sentiment Only | ~48% |
| Rolling Sentiment | ~48% |

None of the models outperformed the naive baseline.

Confusion matrices and classification reports are available in the `/outputs` directory.

## Discussion

The experiments indicate that daily aggregated financial headlines do not provide statistically meaningful predictive signal for next-day market direction under classical linear NLP models.

This aligns with:
- The difficulty of short-horizon financial forecasting
- Efficient Market Hypothesis at daily frequency
- The limitations of bag-of-words representations for capturing market dynamics

## Future Work

- Use contextual transformer models (e.g., BERT, FinBERT)
- Incorporate intraday timestamp alignment
- Combine news features with technical indicators
- Predict multi-day (3-day / 5-day) returns
- Explore nonlinear models (SVM, XGBoost)
- Evaluate statistical significance of results


# stock-nlp-prediction
Build a supervised binary classification model to predict whether TCS closing price at time t+1 is higher than at time t, using textual information available at time t.
# This project shows:

1️⃣ Proper ML pipeline design
2️⃣ Time-series split awareness
3️⃣ Leakage prevention
4️⃣ Baseline comparison discipline
5️⃣ Feature engineering attempts
6️⃣ Structured experimentation
7️⃣ Honest reporting of negative results

# Results
Short-horizon directional prediction using generic daily headlines exhibits no statistically meaningful edge under linear models, suggesting either market efficiency at daily frequency or the need for richer contextual representations (e.g., transformers, event extraction, intraday alignment).
