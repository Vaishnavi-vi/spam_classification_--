# 📧 Spam Classifier with BOW, TF-IDF, and Word2Vec

This project aims to classify messages as **Spam** or **Ham (Not Spam)** using different text vectorization techniques:  
- **Bag of Words (BOW)**
- **TF-IDF (Term Frequency–Inverse Document Frequency)**
- **Word2Vec (Averaged Embeddings)**

We compare the performance of these vectorization techniques using classical machine learning models and evaluate them using the **AUC-ROC score**.

---

## 🧠 Dataset

We use the **SMS Spam Collection Dataset** from the UCI repository.

- Total Samples: ~5,500
- Labels: `ham`, `spam`
- Text column: `message`
---

## 📊 Preprocessing Steps

1. Lowercasing
2. Removing punctuation and stopwords
3. Tokenization
4. Lemmatization
5. Train-test split (80-20)

---

## 🔧 Vectorization Techniques

### ✅ Bag of Words (CountVectorizer)
- Converts text to word frequency vectors.
- Sparse and high-dimensional.
- Works well with Naive Bayes and Logistic Regression.

### ✅ TF-IDF (TfidfVectorizer)
- Weights rare but informative words higher.
- Similar to BOW but more refined.
- Useful for downplaying common words.

### ✅ Word2Vec (Averaged)
- Self-trained word embeddings.
- Sentence represented as the average of word vectors.
- Dense, low-dimensional vectors,vector_size=100
- Loses context (e.g., "not good" = "good").

---

## 🚀 Models Used

- **Logistic Regression**
- All models trained separately on each vectorization output.

---

## 📈 Evaluation Metric

We used **AUC-ROC (Area Under the Curve – Receiver Operating Characteristic)** to evaluate model performance.

---

## 📊 Results

| Vectorization | AUC-ROC Score |
|---------------|---------------|
| Bag of Words  | **0.98**      |
| TF-IDF        | **0.98**      |
| Word2Vec (avg)| **0.78**      |

> Note: Word2Vec gives lower performance in this context due to loss of semantic structure when averaging and lack of context-awareness.

---


