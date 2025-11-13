# Day 18: SMS Spam Filter

## Dataset

- Source: [SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset)
- Features: Text messages labeled as 'ham' or 'spam'

## Project Summary

This project builds a simple SMS spam filter using Naive Bayes classifier with TF-IDF vectorization. The pipeline includes data loading, preprocessing, model training, evaluation, and model persistence for inference.

## Model and Performance

- **Algorithm**: Multinomial Naive Bayes
- **Vectorization**: TF-IDF with English stop words
- **Evaluation**: Classification report and confusion matrix
- **Performance**: High accuracy on test set, with strong precision and recall for spam detection

## Key Findings

- Text length distributions differ between ham and spam messages.
- The model effectively classifies spam with minimal false positives.

## Visualizations

- Label distribution histogram.
- Text length distribution by label.
- Confusion matrix heatmap.
- Prediction probabilities histogram.

## Files

- `notebooks/filter.ipynb` — Complete notebook with training and visualizations.
- `data/spam.csv` — Raw dataset.
- `models/spam_classifier_model.joblib` — Trained model.
- `models/tfidf_vectorizer.joblib` — TF-IDF vectorizer.

## How to run

1. Open `notebooks/filter.ipynb` and execute cells.
2. For inference, load the model and vectorizer, transform new text, and predict.

## Potential Improvements

This project can be significantly enhanced with more diverse text samples. Currently limited to SMS data, expanding to emails, social media posts, or multilingual texts would improve generalization. Larger datasets would allow for more robust training, reducing overfitting and improving performance on varied spam patterns. Incorporating advanced NLP techniques like BERT embeddings or ensemble methods could further boost accuracy, especially with richer, more varied text corpora.