# IMDB Sentiment Analysis: Traditional ML Comparative Study

This repository contains a comprehensive sentiment analysis project focused on the **IMDB Movie Reviews Dataset**. The objective is to evaluate how different text representation techniques impact the performance of traditional Machine Learning models (specifically **Logistic Regression**) in a binary classification task.

## 📋 Project Overview
The project follows a standard NLP pipeline to process 50,000 movie reviews and classify them as either **Positive** or **Negative**. This study compares frequency-based, statistical, and semantic vectorization methods.

### Key Features
* **Preprocessing:** HTML tag removal, case normalization, stop-word filtering, and **Lemmatization**.
* **Class Balance:** The dataset is perfectly balanced (25k positive / 25k negative), ensuring accuracy is a reliable metric.
* **Model:** All techniques were evaluated using **Logistic Regression** to ensure a fair "apples-to-apples" comparison.

---

## 🛠️ Text Representations Evaluated

1. **One-Hot Encoding:** Binary representation of word presence.
2. **Bag of Words (BoW):** Frequency-based count of term occurrences.
3. **TF-IDF:** Statistical weighting that penalizes common noise words and highlights distinctive sentiment terms.
4. **Word2Vec (Skip-gram):** Learned semantic embeddings transformed into document vectors via mean pooling.



---

## 📊 Final Performance Results

The models were evaluated using an 80/20 train-test split. **TF-IDF** emerged as the superior representation method.

| Representation | Accuracy | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| **TF-IDF** | **89.35%** | **0.8938** | **0.8935** | **0.8934** |
| Bag of Words | 87.43% | 0.8743 | 0.8743 | 0.8743 |
| Word2Vec (Averaged) | 87.29% | 0.8729 | 0.8729 | 0.8728 |
| One-Hot Encoding | 87.02% | 0.8702 | 0.8702 | 0.8701 |

---

## 🔍 Key Insights

* **Noise Filtering:** TF-IDF performed best because it successfully down-weighted generic terms like "movie" and "film," allowing high-impact sentiment adjectives to drive the classification.
* **Semantic Generalization:** While Word2Vec didn't outperform TF-IDF, it successfully clustered synonyms (e.g., mapping "excellent" near "superb"), demonstrating its ability to generalize linguistic meaning.
* **Intensity vs. Presence:** Bag of Words slightly outperformed One-Hot Encoding, proving that the frequency of sentiment words (intensity) provides a more useful signal than simple existence.



---

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/IMDB-Sentiment-Analysis-Traditional-ML.git](https://github.com/your-username/IMDB-Sentiment-Analysis-Traditional-ML.git)

2. Ensure you have the dataset IMDB Dataset.csv in the root directory.

3. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn nltk gensim matplotlib seaborn
4. Run the Jupyter Notebook: IMDB.ipynb.
