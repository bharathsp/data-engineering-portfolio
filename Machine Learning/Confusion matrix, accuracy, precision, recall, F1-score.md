## 📊 1. **Confusion Matrix**

A **confusion matrix** is a table used to evaluate the performance of a **classification model**, especially in binary classification.

### ✅ Format:

|                     | Predicted Positive  | Predicted Negative  |
| ------------------- | ------------------- | ------------------- |
| **Actual Positive** | ✅True Positive (TP)  | ❌False Negative (FN) (Type II Error) |
| **Actual Negative** | ❌False Positive (FP) (Type I Error) | ✅True Negative (TN)  |

---

## 🧪 Example:

Suppose you build a model to predict if a patient has a disease.

### Prediction Results:

* TP = 70 (Correctly predicted as having disease)
* TN = 90 (Correctly predicted as not having disease)
* FP = 10 (Predicted disease, but no disease)
* FN = 30 (Predicted no disease, but actually had disease)

---

## 🧮 2. **Accuracy**

> Measures overall correctness.

### **Formula**:

$$
\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}
$$

### **Using Example**:

$$
\text{Accuracy} = \frac{70 + 90}{70 + 90 + 10 + 30} = \frac{160}{200} = 0.80 = 80\%
$$

✅ **Meaning**: 80% of total predictions were correct.

---

## 🎯 3. **Precision (Positive Predictive Value)**

> Of all predicted positives, how many are truly positive?

### **Formula**:

$$
\text{Precision} = \frac{TP}{TP + FP}
$$

### **Using Example**:

$$
\text{Precision} = \frac{70}{70 + 10} = \frac{70}{80} = 0.875 = 87.5\%
$$

✅ **Meaning**: Of all patients predicted to have the disease, 87.5% actually had it.

---

## 🛡️ 4. **Recall (Sensitivity or True Positive Rate)**

> Of all actual positives, how many were correctly predicted?

### **Formula**:

$$
\text{Recall} = \frac{TP}{TP + FN}
$$

### **Using Example**:

$$
\text{Recall} = \frac{70}{70 + 30} = \frac{70}{100} = 0.70 = 70\%
$$

✅ **Meaning**: The model identified 70% of actual disease cases.

---

## ⚖️ 5. **F1 Score**
> Harmonic mean of Precision and Recall. A balance between both.

### **Formula**:

$$
\text{F1 Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}
$$

### **Using Example**:

$$
\text{F1 Score} = 2 \times \frac{0.875 \times 0.70}{0.875 + 0.70} = 2 \times \frac{0.6125}{1.575} \approx 0.778
$$

✅ **Meaning**: Balance between precision and recall is \~77.8%

---

## ✅ Summary Table (from example):

| Metric    | Value | Meaning                                             |
| --------- | ----- | --------------------------------------------------- |
| Accuracy  | 80%   | Overall correctness                                 |
| Precision | 87.5% | How many predicted positives were actually positive |
| Recall    | 70%   | How many actual positives were captured             |
| F1 Score  | 77.8% | Trade-off between precision and recall              |

---

## ❗ Type I and Type II Errors

| Error Type        | Definition                                                        | Example                                         |
| ----------------- | ----------------------------------------------------------------- | ----------------------------------------------- |
| **Type I Error**  | **False Positive** – Predict positive when it's actually negative | Predicting a patient has cancer when they don’t |
| **Type II Error** | **False Negative** – Predict negative when it's actually positive | Failing to detect cancer in a sick patient      |

---

### 🔁 Analogy: Security Alarm System

* **Type I Error (False Positive)**: Alarm goes off, but no burglar.
* **Type II Error (False Negative)**: Burglar breaks in, but alarm stays silent.
