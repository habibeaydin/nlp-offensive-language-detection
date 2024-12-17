# **Offensive Language Detection in Turkish Social Media**

## **Project Overview**  
This project focuses on detecting **offensive language** in Turkish social media comments using natural language processing (NLP) techniques. The goal is to classify text data into two categories:  
- **Offensive**  
- **Not Offensive**  

The project implements different **feature extraction techniques** (Bag-of-Words, TF-IDF) and evaluates the performance of multiple machine learning models, including Naive Bayes, Logistic Regression, and Neural Networks.

---

## **Dataset**  
The dataset consists of Turkish social media comments and is divided into three parts:  
- **Train Set**: 28,000 samples (for training the model)  
- **Validation Set**: 3,277 samples (for model tuning)  
- **Test Set**: 3,515 samples (for final evaluation)  

Each text entry is labeled as:  
- `offensive`: Harmful or inappropriate content  
- `not-offensive`: Harmless content  

Dataset Source: [Dataset Link](https://doi.org/10.57672/me60-ab73)

---

## **Technical Approach**  

### **1. Preprocessing**  
The following preprocessing steps were applied to clean the text data:  
- Converting text to **lowercase**.  
- Removing **user mentions** (e.g., `@USER`).  
- Removing **URLs**, numbers, and punctuation.  
- Removing Turkish **stopwords** (using NLTK's Turkish stopword list).  

**Example**:  
Original: `@USER Trezeguet yerine El Sharawy daha iyi olmaz mı?`  
Cleaned: `trezeguet yerine el sharawy daha iyi olmaz mı`

---

### **2. Feature Extraction**  
Two feature extraction techniques were used:  
1. **Bag-of-Words (BoW)**: Converts text into word frequency vectors.  
2. **TF-IDF**: Assigns importance to words based on their frequency and relevance.  

---

### **3. Models**  
The project evaluates the following machine learning models:  
- **Naive Bayes**: Effective and fast for text classification.  
- **Logistic Regression**: A linear classifier suitable for binary classification.  
- **Neural Network (MLPClassifier)**: A simple multi-layer perceptron model.  

---

## **Results**  

The models were evaluated based on the **F1 Score** on the test set. The results are as follows:

| **Vectorizer**   | **Model**             | **Test Accuracy** | **Test Precision** | **Test Recall** | **Test F1 Score** |
|------------------|-----------------------|------------------:|-------------------:|----------------:|-----------------:|
| **Bag-of-Words** | **Naive Bayes**       | 0.831            | 0.618             | 0.440           | 0.514           |
| **Bag-of-Words** | **Logistic Regression**| 0.837            | 0.690             | 0.354           | 0.468           |
| **TF-IDF**       | **Naive Bayes**       | 0.829            | 0.895             | 0.180           | 0.299           |
| **TF-IDF**       | **Logistic Regression**| 0.839            | 0.842             | 0.255           | 0.392           |

**Conclusion**:  
- The **Bag-of-Words + Naive Bayes** combination achieved the best balance of precision and recall with the highest F1 Score (0.514).  
- TF-IDF performed well in precision but suffered from lower recall.

---

## **Technologies Used**  
- **Python**  
- **Libraries**:  
   - `scikit-learn` (for machine learning models)  
   - `pandas` (data processing)  
   - `nltk` (text preprocessing and stopwords)  
   - `matplotlib` and `seaborn` (visualization)  

---
