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

---

### 🔸 (A) Nearest Neighbor (NN) Rule

#### ➤ Definition

The **Nearest Neighbor Rule** states that an unknown sample is assigned to the **class of its closest training sample** in the feature space.

**Formula:**
[
\text{Class}(x) = \text{Class of } \min_i |x - x_i|
]
where

* (x_i) = training sample
* (|x - x_i|) = Euclidean distance

---

#### ➤ Working (Example)

Suppose two classes:

* Class A → (1,1), (2,2)
* Class B → (5,5), (6,6)

Unknown point → (3,3)

Nearest neighbor to (3,3) is (2,2) from Class A → So, **(3,3) belongs to Class A**.

---

### 🔸 (B) K-Nearest Neighbor (KNN)

#### ➤ Concept

Instead of just one neighbor, **KNN** considers the *K closest samples*.
The class with the majority among those K neighbors is assigned.

**Steps of KNN Algorithm:**

1. Choose K (odd number preferred to avoid ties).
2. Compute the distance between the unknown sample and all training samples.
3. Select the K samples with the smallest distances.
4. Assign the class that occurs most frequently among them.

---

#### ➤ Example (Exam-style)

Dataset →

| Point | p1 | p2 | Class |
| ----- | -- | -- | ----- |
| A     | 2  | 4  | +     |
| B     | 4  | 2  | +     |
| C     | 4  | 4  | –     |
| D     | 6  | 2  | –     |

Predict class for **X(4,6)** with **K = 3**.

Compute distances →

* A: √[(4–2)²+(6–4)²] = √8 = 2.82
* B: √[(4–4)²+(6–2)²] = 4
* C: √[(4–4)²+(6–4)²] = 2
* D: √[(6–4)²+(2–6)²] = √20 = 4.47

→ Closest 3: C(–), A(+), B(+) → 2 positives, 1 negative → Class = **Positive (+)**.

---

#### ➤ Advantages

* Simple and effective.
* No training phase (lazy learner).
* Works well for low-dimensional data.

#### ➤ Limitations

* Slow for large datasets.
* Sensitive to noise and irrelevant features.
* Needs proper feature scaling.

---

### 🔸 (C) Bayes Classifier

#### ➤ Concept

Bayes Classifier is based on **Bayes’ Theorem**:
[
P(C_i|x) = \frac{P(x|C_i)P(C_i)}{P(x)}
]
where

* (P(C_i|x)): posterior probability (class given data)
* (P(x|C_i)): likelihood
* (P(C_i)): prior probability

The classifier assigns (x) to the class with the **highest posterior probability**.

---

#### ➤ Naïve Bayes Classifier

Assumes features are **conditionally independent** given the class.
This simplifies computation for multidimensional data.

**Decision Rule:**
[
C = \arg \max_{C_i} P(C_i) \prod_{j} P(x_j|C_i)
]

**Use:** Spam detection, text classification, sentiment analysis.

---

## **2️⃣ K-Means Clustering**

- 2023 — Section B (Q2(e)): Define clustering. Discuss k‑means clustering algorithm.  
- 2024 — Section A (Q1(j)): Explain K‑means clustering.  
- 2022 — Section C (Q7(a)): To which category of clustering schemes does the k‑means algorithm belong? What is its major advantage? Which factors influence computation duration?

### 🔹 Definition

K-Means is an **unsupervised learning** algorithm used for **clustering**, where data is grouped into *K clusters* based on similarity.

---

### 🔹 Steps of the Algorithm

1. Choose number of clusters (K).
2. Initialize (K) centroids randomly.
3. Assign each data point to the nearest centroid.
4. Recalculate centroids as the mean of all assigned points.
5. Repeat steps 3–4 until centroids no longer move (convergence).

---

### 🔹 Example

Data points: (2,3), (3,3), (6,6), (7,7), (8,8)
Let (K=2).
Initial centroids → (2,3), (7,7)

Iteration 1:

* Cluster 1 → (2,3), (3,3) → mean = (2.5,3)
* Cluster 2 → (6,6), (7,7), (8,8) → mean = (7,7)

New centroids → (2.5,3), (7,7) → stable → final clusters formed.

---

### 🔹 Category and Characteristics

* **Category:** Partitional clustering method.
* **Type:** Iterative refinement algorithm.
* **Major Advantage:** Simple, fast, and efficient for large datasets.
* **Factors Influencing Time:**

  * Number of clusters (K).
  * Number of data points (N).
  * Number of iterations for convergence.
  * Dimensionality of data.

---

### 🔹 Limitations

* Must specify K beforehand.
* Sensitive to initial centroid selection.
* Works only for spherical clusters (not irregular shapes).

---

## **3️⃣ Support Vector Machine (SVM)**

- 2022 — Section A (Q1(i)): Write short note on Support Vector Machine (SVM).


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