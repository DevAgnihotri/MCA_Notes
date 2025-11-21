# Unit 5 AI

## **1️⃣ Pattern Recognition — Introduction and Design Principles**

- 2023 — Section A (Q1(i)): Define the term pattern with example.  
- 2024 — Section B (Q2(e)): Define pattern recognition. What are the components of pattern recognition?  
- 2023 — Section C (Q7(a)): Explain design cycle of a pattern recognition system with diagram.  
- 2022 — Section B (Q2(e)): Design principles of pattern recognition system. (Also covers PCA & LDA)

### 🔹 Definition

**Pattern Recognition (PR)** is the process of automatically identifying and classifying patterns or regularities in data using computational methods.
A **pattern** is an *object, signal, or data structure* that can be represented by a set of features.
➡️ **Example:** In handwriting recognition, the shape of a letter (e.g., ‘A’ or ‘B’) is the pattern.

---

### 🔹 Components of a Pattern Recognition System

1. **Sensing / Data Acquisition:** Collecting raw data (e.g., image, sound, text).
2. **Preprocessing:** Cleaning or normalizing data (e.g., noise removal).
3. **Feature Extraction:** Selecting the most relevant features that represent data efficiently.
4. **Classification / Decision Making:** Assigning patterns to specific categories using algorithms (like decision trees, SVMs, neural networks).
5. **Post-processing / Evaluation:** Assessing performance, accuracy, and refinement.

---

### 🔹 Design Principles of a PR System

1. **Representation of Patterns:** Properly defining feature sets that best describe the patterns.
2. **Feature Selection:** Reducing dimensionality by keeping only useful features.
3. **Model Selection:** Choosing appropriate classification models (statistical, neural, fuzzy).
4. **Training and Learning:** Adjusting parameters based on training data.
5. **Evaluation:** Using metrics such as accuracy, precision, recall, and confusion matrices.

---

### 🔹 Design Cycle of Pattern Recognition System

A **pattern recognition design cycle** includes:

1. **Data Collection** →
2. **Preprocessing** →
3. **Feature Extraction** →
4. **Model Design** →
5. **Training / Learning** →
6. **Testing & Validation** →
7. **Performance Evaluation**

**Diagram (text-form):**

```
Raw Data → Preprocessing → Feature Extraction → Classification → Output Decision
```

---

## **2️⃣ Statistical Pattern Recognition**

- 2024 — Section A (Q1(i)): What is Statistical PR?


### 🔹 Definition

**Statistical Pattern Recognition (SPR)** uses **probability and statistics** to model the patterns and their variations mathematically.
It assumes each pattern class has a **probability distribution**, and the classifier assigns an unknown sample to the class with the **highest probability (Bayes decision rule).**

➡️ Example: In speech recognition, words are represented as probabilistic models, and the word with the highest likelihood is recognized.

---

### 🔹 Key Idea

* Each pattern belongs to a class with probability ( P(C_i|x) )
* Decision is made by maximizing this probability:
  [
  \text{Classify } x \text{ to } C_i \text{ if } P(C_i|x) = \max_j P(C_j|x)
  ]
* Models used: Gaussian distribution, Naïve Bayes, Hidden Markov Models.

---

## **3️⃣ Parameter Estimation Methods — PCA & LDA**

- 2022 — Section B (Q2(e)): Explain Principal Component Analysis (PCA) and Linear Discriminant Analysis (LDA).  
- 2023 — Section C (Q7(b)): Explain need and concept of principal component analysis in pattern recognition process.  
- 2024 — Section C (Q7(a)): Define Principal Component Analysis (PCA). Write steps involved in making principal components to do a classification of given data.


### 🔸 (A) Principal Component Analysis (PCA)

**Concept:**
PCA is a *dimensionality reduction* technique that transforms data into a new coordinate system such that:

* The first principal component captures the maximum variance.
* Subsequent components capture remaining variance, orthogonal to previous ones.

**Steps to Compute PCA:**

1. Standardize the data.
2. Compute covariance matrix of features.
3. Find eigenvalues and eigenvectors.
4. Sort eigenvectors by decreasing eigenvalues.
5. Form principal components by projecting data on top *k* eigenvectors.

**Use in Pattern Recognition:**

* Reduces dimensionality while retaining key features.
* Simplifies classification (e.g., face recognition, image compression).

---

### 🔸 (B) Linear Discriminant Analysis (LDA)

**Concept:**
LDA finds a **linear combination of features** that best separates two or more classes.
Unlike PCA (which focuses on variance), LDA focuses on **class separability**.

**Steps:**

1. Compute within-class and between-class scatter matrices.
2. Find the transformation that maximizes between-class scatter and minimizes within-class scatter.
3. Project data on the new axis for better classification.

**Mathematical Objective:**
[
W = \arg \max \frac{|S_B|}{|S_W|}
]
where (S_B) = between-class scatter, (S_W) = within-class scatter.

**Use in PR:**

* Enhances class discrimination in recognition tasks like face or object identification.

---

### 🔹 Difference between PCA and LDA

| Feature                  | PCA                        | LDA                         |
| ------------------------ | -------------------------- | --------------------------- |
| Basis                    | Unsupervised               | Supervised                  |
| Goal                     | Maximize variance          | Maximize class separability |
| Depends on class labels? | No                         | Yes                         |
| Applications             | Compression, visualization | Classification, recognition |

---

### 🔹 Relationship to Pattern Recognition

Both **PCA and LDA** serve as **feature extraction / dimensionality reduction tools** in the **design cycle** of a PR system before classification.

Perfect — you’ve reached the **final section** of your AI theory unit 👏
Here’s a **complete, exam-ready explanation** of the topics:
**Classification Techniques, K-Means Clustering, and Support Vector Machine (SVM)** — with theory depth and direct alignment to the given questions.

---

## **1️⃣ Classification Techniques — Nearest Neighbor Rule and Bayes Classifier**

- 2023 — Section A (Q1(j)): State nearest neighbor rule.  
- 2022 — Section C (Q7(b)): Show how classification is done by k‑nearest neighbors. Construct KNN on given dataset and predict class for X (p1=4, p2=6), k=3.  
- 2024 — Section C (Q7(b)): Explain Nearest Neighbor (NN) rule in detail.  
- Bayes classifier: No matching questions found in the provided selection.

### 🔹 What is Classification?

Classification is the process of assigning a data sample (unknown pattern) to one of the predefined classes based on features.
It is a **supervised learning** method because the model is trained with labeled data.

## ⭐ **1. Nearest Neighbor Rule (K-NN)**

### ✅ **Definition**

K-Nearest Neighbor is a **classification technique** where you classify a new data point by looking at the **closest (nearest) existing points**.

### ⚙️ **How it works**

1. Take the new point.
2. Find its **K nearest neighbors** from the dataset.
3. Whichever class appears the most, that becomes the new point’s class.

---

### 📈 **ASCII Diagram**

```
Class A (●)          Class B (▲)

●       ●
   ●      
             ▲     ▲
                  ▲

New Point (X)

           X
```

X will be classified depending on whether more **●** or **▲** are close to it.

---

### 🧪 **Simple Working Example**

Dataset:

| Point | X | Y | Class |
| ----- | - | - | ----- |
| P1    | 1 | 1 | A     |
| P2    | 2 | 1 | A     |
| P3    | 8 | 8 | B     |
| P4    | 9 | 8 | B     |

Predict for: **(3,2)**
Choose **K = 3**

Distances:

* To P1 → close
* To P2 → very close
* To P3 → far
* To P4 → far

Nearest neighbors = **A, A, B → majority A**

➡️ **Final Class = A**

---

## ⭐ **2. Bayes Classifier (Naïve Bayes)**

### ✅ **Definition**

Bayes classifier predicts class based on **probability**.

Formula used:

[
P(Class | Data) = \frac{P(Data | Class) \cdot P(Class)}{P(Data)}
]

We choose the class with the **highest probability**.

---

### 🧠 **Simple Example**

You want to classify a message as:

* Spam
* Not Spam

Training data:

* 80% emails are **not spam**
* 20% emails are **spam**
* The word “Offer” appears:

  * In **60%** spam
  * In **10%** non-spam

New email contains the word **“Offer”**.
Compare probabilities:

```
P(Spam | Offer)     = 0.6 × 0.2 = 0.12
P(NotSpam | Offer)  = 0.1 × 0.8 = 0.08
```

Since **0.12 > 0.08** → classify as **Spam**.

---

### 📈 **ASCII Diagram**

```
 ┌─────────────── Bayes Classifier ────────────────┐
 |   Input Word: "Offer"                           |
 |   Calculate:                                     |
 |     P(Spam|Offer)                                |
 |     P(NotSpam|Offer)                             |
 |   Compare and choose highest.                    |
 └──────────────────────────────────────────────────┘
```

---

## ⭐ **3. K-Means Clustering**

### ✅ **Definition**

K-means is **unsupervised**, meaning **no labels**.
It groups data into **K clusters** based on similarity.

---

### ⚙️ **How K-Means works**

1. Pick number of clusters **K**
2. Randomly place **K centroids**
3. Assign each point to nearest centroid
4. Move centroids
5. Repeat until stable

---

### 📈 **ASCII Diagram**

```
Initial (Random Centroids)

●   ●         ○
         ●
    ○

○ = centroid


After Clustering:

Cluster 1 (○1):
● ● ● ●

Cluster 2 (●2):
▲ ▲ ▲ ▲
```

---

### 🧪 **Working Example**

Points:
(1,1), (2,1), (1,2), (9,9), (10,9), (9,10)

Choose **K = 2**

Group 1 (near 1,1):
(1,1), (2,1), (1,2)

Group 2 (near 9,9):
(9,9), (10,9), (9,10)

➡️ **Clusters formed successfully**

---

## ⭐ **4. Support Vector Machine (SVM)**

### ✅ **Definition**

SVM is a classifier that finds the **best boundary (hyperplane)** between classes.
It tries to maximize the **margin** (distance) between boundary and points.

---

### 📈 **ASCII Diagram of SVM**

```
Class A (●) on left
Class B (▲) on right

●   ●   ●   |   ▲   ▲   ▲
             |
         Max Margin
             |
●   ●   ●   |   ▲   ▲   ▲
```

The **middle vertical line** is the SVM decision boundary.

---

### 🧪 **Simple Working Example**

Dataset:

| X | Y | Class |
| - | - | ----- |
| 1 | 1 | A     |
| 1 | 2 | A     |
| 2 | 1 | A     |
| 9 | 9 | B     |
| 8 | 9 | B     |
| 9 | 8 | B     |

SVM finds a “line” between the two classes (A and B).

Imagine two groups far apart → SVM draws the **best separation line** exactly in between.

➡️ New point (7,7) → on B's side → **Class B**

### 🔹 Concept

SVM is a **supervised learning algorithm** used for **classification** (and sometimes regression).
It finds the **optimal hyperplane** that separates classes with the **maximum margin**.

---

### 🔹 Key Idea

For binary classification:
[
w \cdot x + b = 0
]
is the decision boundary (hyperplane).
SVM aims to maximize the margin = distance between the hyperplane and the nearest data points (called **support vectors**).

---

### 🔹 Diagram (text form)

```
Class + : o o o | Margin |  | Margin | x x x : Class –
                <-------> max margin
```

---

### 🔹 Types

1. **Linear SVM** – when data is linearly separable.
2. **Non-linear SVM** – uses **kernel trick** to project data into higher dimensions:

   * Polynomial kernel
   * Gaussian (RBF) kernel
   * Sigmoid kernel

---

### 🔹 Advantages

* Works well in high-dimensional spaces.
* Robust to overfitting (especially with regularization).
* Effective for both linear and non-linear data.

### 🔹 Applications

* Text and image classification
* Bioinformatics (gene classification)
* Handwriting recognition