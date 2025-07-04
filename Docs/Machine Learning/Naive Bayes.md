### 📘 What is **Naive Bayes Theorem**?

**Naive Bayes** is a **supervised machine learning algorithm** based on **Bayes’ Theorem** — used primarily for **classification** tasks. It is called "naive" because it **assumes that features are independent** of each other, which is rarely true in real life, but still works surprisingly well.

---

### 🧠 **Bayes’ Theorem Formula**

$$
P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}
$$

Where:

* $P(A|B)$: Posterior probability (probability of A given B)
* $P(B|A)$: Likelihood (probability of B given A)
* $P(A)$: Prior probability of A
* $P(B)$: Marginal probability of B

---

### 🎯 In Terms of Naive Bayes:

$$
P(Class|Features) = \frac{P(Features|Class) \cdot P(Class)}{P(Features)}
$$

Naive Bayes classifies the input as the class that has the **highest posterior probability**.

---

## 📌 Why "Naive"?

It assumes:

* All features (inputs) are **independent** given the class label
* Example: It assumes that age and income are independent when predicting loan default — which is rarely true

But even with this **naive assumption**, it performs **very well** for many tasks, especially with **text data**.

---

## 💼 Real-Life Use Cases

| Use Case                   | Description                                  |
| -------------------------- | -------------------------------------------- |
| 📧 Spam Detection          | Classify emails as spam or not spam          |
| 🎭 Sentiment Analysis      | Classify reviews as positive or negative     |
| 👨‍⚕️ Medical Diagnosis    | Predict disease based on symptoms            |
| 📚 Document Categorization | Classify news articles or documents by topic |

---

## 🧪 Simple Example

Imagine you want to classify whether a person will buy a product (Yes/No) based on **Age** and **Income**.

### Step-by-step:

1. Calculate **P(Yes)** and **P(No)** from training data
2. For each feature (Age=Young, Income=High):

   * Compute **P(Age=Young | Yes)** and **P(Income=High | Yes)**
3. Apply Bayes' formula:

$$
P(Yes | Age, Income) \propto P(Yes) \cdot P(Age | Yes) \cdot P(Income | Yes)
$$

Do this for both Yes and No, and choose the class with **higher probability**.

---

## ⚙️ Python Code Example (Text Classification)

```python
from sklearn.naive_bayes import MultinomialNB
from sklearn.feature_extraction.text import CountVectorizer

# Sample data
texts = ["Free money now", "Hey, how are you?", "Win a lottery", "Meeting at 5"]
labels = [1, 0, 1, 0]  # 1 = Spam, 0 = Not spam

# Convert text to features
vectorizer = CountVectorizer()
X = vectorizer.fit_transform(texts)

# Train Naive Bayes classifier
model = MultinomialNB()
model.fit(X, labels)

# Predict
test = vectorizer.transform(["Win cash now"])
print(model.predict(test))  # Output: [1] (Spam)
```

---

## ✅ Summary

| Feature           | Description                                        |
| ----------------- | -------------------------------------------------- |
| **Type**          | Probabilistic classifier                           |
| **Assumption**    | Features are independent                           |
| **Advantages**    | Fast, works well with text, needs less data        |
| **Disadvantages** | Assumption of independence may not hold            |
| **Use Cases**     | Spam detection, sentiment analysis, classification |
