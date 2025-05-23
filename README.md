# Helpful Review Prediction Using Machine Learning

This project focuses on predicting the **helpfulness of Amazon customer reviews** for major appliances using Natural Language Processing (NLP) and machine learning techniques.

## 📁 Dataset

- Source: [Amazon Customer Reviews Dataset (Major Appliances)](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt)
- Format: TSV
- Features: Review text, star rating, helpful votes, total votes, etc.

## 🧠 Objective

To classify whether a customer review is *helpful* (based on votes) using:
- Textual review features
- Readability and sentiment metrics
- Metadata like star rating

## 🔧 Pipeline Overview

1. **Text Preprocessing**:
   - Lowercasing, HTML and URL removal
   - Lemmatization using `spaCy`
   - Readability score (Flesch Reading Ease)

2. **Feature Engineering**:
   - TF-IDF vectorization
   - Dimensionality reduction with Truncated SVD

3. **Labeling**:
   - Helpful if `helpful_votes / total_votes >= 0.5`

4. **Modeling**:
   - Balanced dataset using SMOTE
   - Classifier: `RandomForestClassifier`
   - Evaluation via accuracy, confusion matrix, classification report

5. **Persistence**:
   - Model saved with `joblib` for reuse

## 📊 Evaluation Metrics

- Accuracy Score
- Confusion Matrix
- Precision, Recall, F1-score

## 📦 Requirements

```bash
pip install pandas numpy scikit-learn spacy textblob imbalanced-learn matplotlib
python -m spacy download en_core_web_sm
```

## 🚀 Run the Project

Open the `Final_Reviews.ipynb` notebook and run each cell in order. Make sure the dataset is located at:

```
/content/drive/MyDrive/customer_reviews/amazon_reviews_us_Major_Appliances_v1_00.tsv
```

## 📌 Notes

- The project is designed to run in Google Colab.
- Assumes access to Google Drive for reading data.
- Basic error handling is included for data loading.
