# Evaluating Traditional Machine Learning Models and Nepali-Aware Text Preprocessing for Nepali News Classification

## Overview

This project investigates the classification of Nepali news articles into different categories using traditional machine learning techniques.

The project compares multiple text classification models and evaluates whether a simple Nepali-aware preprocessing approach can improve classification performance.

The main goal is to explore how text preprocessing affects machine learning models when working with Nepali-language news articles.

## Research Questions

This project investigates the following questions:

1. How do traditional machine learning models perform on Nepali news classification?
2. Which of the tested models achieves the best performance?
3. Can Nepali-aware tokenization and basic punctuation cleaning improve classification performance?
4. Which news categories are most frequently confused by the model?

## Dataset

The dataset contains Nepali news articles with the following categories:

- Entertainment
- Feature
- Opinion
- Sports

The original dataset contained an unequal number of articles across categories. To create a balanced experiment, 2,000 articles were selected from each of the four categories.

This resulted in:

- Total articles: 8,000
- Training set: 6,400 articles
- Test set: 1,600 articles

Each category contains 400 articles in the test set.

## Methodology

The project followed the following workflow:

News Articles
↓
Data Cleaning and Exploration
↓
Dataset Balancing
↓
Train/Test Split
↓
TF-IDF Vectorization
↓
Machine Learning Models
↓
Model Evaluation
↓
Error Analysis
↓
Nepali-Aware Preprocessing Experiment
↓
Final Evaluation

## Models Evaluated

The following models were tested:

1. Logistic Regression
2. Multinomial Naive Bayes
3. Linear Support Vector Machine (Linear SVM)

## Baseline Results

| Model | Accuracy |
|---|---:|
| Multinomial Naive Bayes | 84.44% |
| Logistic Regression | 91.44% |
| Linear SVM | 92.31% |

Linear SVM achieved the best performance among the initial baseline models.

## Nepali-Aware Preprocessing

Initial feature inspection revealed that some Nepali words were represented as fragmented or noisy tokens.

For example:

- Fragmented features: `चलच`, `टबल`
- Punctuation-attached features: `!'उनले`

To address this issue, a custom tokenizer was created.

The tokenizer:

1. Splits text using whitespace.
2. Preserves complete Nepali words.
3. Removes punctuation from the beginning and end of tokens.

Example:

```python
def nepali_tokenizer(text):
    tokens = text.split()

    cleaned_tokens = []

    for token in tokens:
        cleaned = token.strip(string.punctuation + "।“”‘’—–…")

        if cleaned:
            cleaned_tokens.append(cleaned)

    return cleaned_tokens