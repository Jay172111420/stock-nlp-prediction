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
