# Sentiment Analysis Using Machine Learning

## Project Overview

This project focuses on **sentiment analysis of Twitter data** using Natural Language Processing (NLP) and Machine Learning techniques.

The objective is to classify tweets into three sentiment categories:

* **Positive**
* **Negative**
* **Neutral**

The project includes text preprocessing, exploratory analysis, TF-IDF feature extraction, machine learning classification, model comparison, confusion matrix analysis, word clouds, and error analysis.

---

## Dataset

The project uses a Twitter sentiment dataset containing **27,481 tweets**.

### Dataset Columns

| Column          | Description                      |
| --------------- | -------------------------------- |
| `textID`        | Unique identifier for each tweet |
| `text`          | Original tweet text              |
| `selected_text` | Text selected from the tweet     |
| `sentiment`     | Sentiment label of the tweet     |

After preprocessing, the project uses the following columns:

* `text`
* `sentiment`

### Sentiment Distribution

| Sentiment |  Count |
| --------- | -----: |
| Neutral   | 11,117 |
| Positive  |  8,582 |
| Negative  |  7,781 |

---

## Technologies and Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Regular Expressions (`re`)
* WordCloud

---

## Project Workflow

### 1. Data Loading

The Twitter dataset is loaded using Pandas and its structure, columns, data types, missing values, and duplicate records are examined.

### 2. Data Cleaning

The dataset is cleaned by:

* Selecting the required `text` and `sentiment` columns
* Removing rows with missing tweet text
* Checking for duplicate records
* Converting text to lowercase
* Removing URLs
* Removing mentions
* Removing punctuation
* Removing stopwords
* Tokenizing the text

### 3. Exploratory Data Analysis

The sentiment distribution is analyzed using visualizations.

Word clouds are also generated to identify frequently occurring words in:

* Positive tweets
* Negative tweets
* Neutral tweets

### 4. TF-IDF Feature Extraction

**TF-IDF (Term Frequency-Inverse Document Frequency)** is used to convert the cleaned text into numerical features that can be used by machine learning models.

### 5. Train-Test Split

The dataset is divided into:

* **80% training data**
* **20% testing data**

### 6. Machine Learning Models

Two classification algorithms are implemented:

1. **Multinomial Naive Bayes**
2. **Logistic Regression**

Both models are trained using the TF-IDF features.

---

## Model Performance

The models are evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score

### Results

| Model               |   Accuracy |  Precision |     Recall |   F1 Score |
| ------------------- | ---------: | ---------: | ---------: | ---------: |
| Naive Bayes         |     64.16% |     67.11% |     64.16% |     63.90% |
| Logistic Regression | **68.82%** | **69.77%** | **68.82%** | **68.81%** |

### Best Model

**Logistic Regression** performed better than Multinomial Naive Bayes across all evaluated metrics.

Therefore, Logistic Regression was selected as the better-performing model for this sentiment classification task.

---

## Confusion Matrix

A confusion matrix is generated for the Logistic Regression model to analyze the classification of:

* Negative tweets
* Neutral tweets
* Positive tweets

This helps identify which sentiment classes are being confused by the model.

---

## Error Analysis

Incorrectly classified tweets were examined to understand the limitations of the model.

Some classification errors occurred because tweets may contain:

* Mixed sentiment
* Sarcasm
* Informal language
* Spelling mistakes
* Abbreviations
* Insufficient context

Since TF-IDF mainly relies on word and phrase patterns, it can have difficulty understanding the complete meaning of short or context-dependent tweets.

---

## Key Findings

* The dataset contains **27,481 tweets** across three sentiment classes.
* Neutral tweets are the largest sentiment category.
* TF-IDF provides numerical text features for machine learning.
* Logistic Regression performed better than Multinomial Naive Bayes.
* Logistic Regression achieved approximately **68.82% accuracy** and **68.81% F1 score**.
* Some sentiment classification errors are caused by sarcasm, mixed emotions, informal language, spelling variations, and lack of context.

---

## Applications

Sentiment analysis can be applied to:

* Customer feedback analysis
* Social media monitoring
* Product review analysis
* Brand perception analysis
* Public opinion analysis

---

## Project Structure

```text
Sentiment-Analysis/
│
├── Sentiment_Analysis.ipynb
└── README.md
```

---

## Conclusion

This project demonstrates a complete machine learning-based sentiment analysis workflow, starting from Twitter text preprocessing and exploratory analysis to TF-IDF feature extraction, model training, evaluation, and error analysis.

Among the two models tested, **Logistic Regression achieved the best performance**, making it the preferred model for this sentiment classification task.

