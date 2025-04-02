# Multimodal-Rating-Analysis-with-NLP

This project explores multiple modeling strategies to predict credit *ratings* using structured financial features and unstructured text.

---

## Objective

Predict the categorical *Rating* of financial entities using:
- Structured numeric features (financial ratios, bond info, etc.)
- Textual descriptions (string_values)
- Sentiment and Topic modeling insights

The rating is grouped into 3 classes: *High, **Medium, **Low* for interpretability.

---

## Dataset

- Artificial_Data.xlsx — structured data + text descriptions
- data_with_dominant_topic.csv — includes sentiment scores and topic assignments

---

## Modeling Approaches

### 1. Structured-Only Model
- Random Forest on scaled financial features
- Accuracy: ~5%

### 2. Text-Only Model
- TF-IDF + Sentiment + Topic modeling + Random Forest
- Accuracy: ~5%

### 3. Combined Model
- Structured + sentiment + topics
- Accuracy: ~20%

### 4. Regression Models (RandomForest, XGBoost, LinearRegression)
- Target: Encoded numeric rating
- Accuracy (rounded prediction): ~40%
- Best model: XGBoost

### 5. Neural Model: Hybrid CNN+LSTM
- Conv1D+LSTM on text
- Conv1D+LSTM on structured data
- Combined via dense layers
- Accuracy: ~40% (Best overall)

---

## Exploratory Insights

### Sentiment vs Rating Class
- High-rated records have slightly *higher sentiment scores*
- Negative sentiment correlates with *lower ratings*

### Topic Distribution
- Topics related to financial risk appear more in *low-rated* classes

---

## Decision-Making Insights

### 1. Sentiment as a Leading Indicator
- Negative sentiment in string_values may indicate *rating downgrades*
- Could be used in early warning systems

### 2. Topics Reveal Risk Signatures
- Some topics correlate with *rating classes*
- Can inform document flagging and analyst review

### 3. Structured + Text Fusion Improves Accuracy
- Multimodal learning improves predictive power
- Recommend blending text with numeric metrics in rating engines

---

## Requirements

```bash
pip install pandas numpy scikit-learn nltk tensorflow xgboost shap matplotlib seaborn
