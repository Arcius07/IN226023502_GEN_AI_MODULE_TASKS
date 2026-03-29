# Amazon Reviews Sentiment Analysis using NLP Pipeline & ML Models

This project implements a comprehensive Natural Language Processing (NLP) pipeline to classify the sentiment of Amazon product reviews. It covers everything from raw data preprocessing and feature engineering to training and evaluating multiple Machine Learning models.

---

## 📋 Project Overview

The primary goal is to categorize user reviews into three sentiments:

- **Positive (1)**
- **Neutral (0)**
- **Negative (-1)**

The project compares two different text vectorization techniques (**Bag of Words** and **TF-IDF**) across various classification algorithms to identify the most effective combination.

---

## 🛠️ Tech Stack & Libraries

- **Language:** Python  
- **Data Manipulation:** Pandas, NumPy  
- **Visualization:** Matplotlib, Seaborn  
- **NLP Toolkit:** NLTK (Tokenization, Stopwords, Stemming)  
- **Machine Learning:** Scikit-Learn  

---

## ⚙️ NLP Pipeline Workflow

### 1. Data Preprocessing

Raw text is inherently noisy. The following steps were applied to the `review_body` column:

- **Lowercasing:** Converting all text to lowercase  
- **Cleaning:** Removing HTML tags, URLs, and non-alphabetic characters using Regex  
- **Tokenization:** Breaking sentences into individual words  
- **Stopword Removal:** Filtering out common words (e.g., *"the"*, *"is"*)  
- **Stemming:** Using the PorterStemmer to reduce words to their root form  
  - Example: *"sweating" → "sweat"*

---

### 2. Feature Engineering

Text data was converted into numerical format using two methods:

#### 📌 Bag of Words (CountVectorizer)
- Creates a frequency count of words  
- Ignores word order  
- Simple but effective baseline  

#### 📌 TF-IDF (TfidfVectorizer)
- Assigns weights to words based on importance  
- Reduces impact of common words  
- Improves model performance  

---

### 3. Model Training

We trained and compared three classifiers:

- **Logistic Regression**
- **Multinomial Naive Bayes**
- **Decision Tree Classifier**

---

## 📊 Evaluation & Results

The models were evaluated using:

- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**

Visual insights were generated using **Confusion Matrices**.

---

### 🔍 Key Findings

- **🏆 Best Performer:**  
  Logistic Regression with TF-IDF achieved the highest performance.

- **TF-IDF vs. BoW:**  
  TF-IDF outperformed Bag of Words by reducing the impact of high-frequency but low-meaning words.

- **Model Comparison:**

  - **Logistic Regression:**  
    Provided a balanced Precision and Recall  

  - **Naive Bayes:**  
    Computationally efficient and robust, but slightly less accurate  

  - **Decision Tree:**  
    Showed overfitting and lower accuracy on high-dimensional text data  

---

## 🚀 Conclusion

This project demonstrates that a structured NLP pipeline combined with **TF-IDF vectorization** and **Logistic Regression** provides a robust solution for sentiment classification.

This approach can be effectively used by businesses to:
- Analyze customer feedback at scale  
- Improve products and services  
- Gain actionable insights from reviews  

---

## 📁 File

`Task_2_NLP_Sentiment_Analysis_using_NLP_Pipeline_&_ML_Models.ipynb`
