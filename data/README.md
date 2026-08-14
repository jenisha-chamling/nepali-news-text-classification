# Dataset

This folder contains the dataset used for the Nepali News Classification project.

## Dataset Description

The dataset contains Nepali news articles collected across multiple news categories.

The dataset includes the following columns:

| Column | Description |
|---|---|
| `title` | Title of the news article |
| `text` | Main content of the news article |
| `category` | Category or label assigned to the news article |

The `text` column was used as the main input for the machine learning models, while the `category` column was used as the target label.

---

## Dataset Source

The dataset used in this project was obtained from Kaggle.

**Source:** [Nepali News Dataset by dhakal2444 on Kaggle](https://www.kaggle.com/datasets/dhakal2444/nepali-news-dataset)

Please refer to the original dataset page for information regarding data collection, licensing, attribution, and redistribution permissions.

---

## Categories Used in This Project

The original dataset contains multiple news categories with an unequal number of articles.

For this experiment, the following four categories were selected:

- Entertainment
- Feature
- Opinion
- Sports

These categories were used for the news classification experiments.

---

## Dataset Balancing

The original category distribution was imbalanced. To create a controlled and balanced experiment, **2,000 articles** were selected from each of the four categories.

The resulting dataset used for the experiments contained:

| Category | Number of Articles |
|---|---:|
| Entertainment | 2,000 |
| Feature | 2,000 |
| Opinion | 2,000 |
| Sports | 2,000 |
| **Total** | **8,000** |

---

## Train-Test Split

The balanced dataset was divided into training and testing sets.

| Dataset | Number of Articles |
|---|---:|
| Training Set | 6,400 |
| Testing Set | 1,600 |
| **Total** | **8,000** |

The test set contained **400 articles from each category**.

The training data was used to train the machine learning models, while the test data was kept separate and used for evaluation.

---

## Dataset Usage

The dataset was used for the following stages of the project:

1. Data exploration
2. Missing value checking
3. Category distribution analysis
4. Category selection and dataset balancing
5. Train-test splitting
6. TF-IDF text vectorization
7. Training machine learning models
8. Model evaluation
9. Error analysis
10. Text preprocessing experiments

The following machine learning models were evaluated:

- Logistic Regression
- Multinomial Naive Bayes
- Linear Support Vector Machine (Linear SVM)

---

## Preprocessing Experiment

During feature analysis, the initial TF-IDF representation contained fragmented and noisy Nepali tokens.

A custom tokenizer was developed to improve the representation of Nepali text by:

1. Splitting text based on whitespace.
2. Preserving complete Nepali words.
3. Removing punctuation attached to the beginning or end of tokens.
4. Removing empty tokens.

The custom tokenizer was then used with TF-IDF vectorization and evaluated using Linear SVM.

### Results

| Experiment | Accuracy |
|---|---:|
| Original TF-IDF + Linear SVM | 92.31% |
| **Cleaned TF-IDF + Linear SVM** | **94.19%** |

The improved preprocessing increased the accuracy by approximately **1.88 percentage points** and reduced the number of incorrect predictions from **123 to 93**.

---

## Important Note

This dataset is used for educational and research purposes as part of the Nepali News Classification project.

The dataset was obtained from :contentReference[oaicite:1]{index=1}. Please refer to the original dataset page for the applicable license, attribution requirements, and redistribution permissions.