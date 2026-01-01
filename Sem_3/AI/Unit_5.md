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
2. **Preprocessing / Segemtation:** Cleaning or normalizing data (e.g., noise removal).
3. **Feature Extraction:** Selecting the most relevant features that represent data efficiently.
4. **Classification / Decision Making:** Assigning patterns to specific categories using algorithms (like decision trees, SVMs, neural networks).
5. **Post-processing / Evaluation:** Assessing performance, accuracy, and refinement.

---
![Image](https://d3lkc3n5th01x7.cloudfront.net/wp-content/uploads/2023/06/30020419/Pattern-recognition-in-ML-banner.png)

### 🔹 Design Principles of a PR System

1. **Representation of Patterns:** Properly defining feature sets that best describe the patterns.
2. **Feature Selection:** Reducing dimensionality by keeping only useful features.
3. **Model Selection:** Choosing appropriate classification models (statistical, neural, fuzzy).
4. **Training and Learning:** Adjusting parameters based on training data.
5. **Evaluation:** Using metrics such as accuracy, precision, recall, and confusion matrices.

---
![Image](https://image.slidesharecdn.com/designcyclesofpatternrecognition-171214082049/75/Design-cycles-of-pattern-recognition-3-2048.jpg)

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

**SPR** is a method where a computer **recognizes patterns using statistics and probability**.

👉 It looks at data, finds patterns using **math**, and then **classifies** or **predicts** something.

**SPR = Learn patterns from data using probability**

---

### How SPR works (easy)

1. Data is collected (images, sounds, numbers, etc.)
2. Important features are extracted
3. Statistical methods are applied
4. Probability is calculated
5. Pattern is classified or recognized

---

### Simple example 🎤

**Speech Recognition**

* Input: voice
* Features: sound frequencies
* Statistics: probability of sounds
* Output: recognized word

---

### Where SPR is used

* Speech recognition
* Face recognition
* Handwritten character recognition
* Medical diagnosis

# **3️⃣ Parameter Estimation Methods — PCA & LDA**

- 2022 — Section B (Q2(e)): Explain Principal Component Analysis (PCA) and Linear Discriminant Analysis (LDA).  
- 2023 — Section C (Q7(b)): Explain need and concept of principal component analysis in pattern recognition process.  
- 2024 — Section C (Q7(a)): Define Principal Component Analysis (PCA). Write steps involved in making principal components to do a classification of given data.

Below is a **proper, detailed explanation of PCA (Principal Component Analysis)** in **simple English**, written so you can **understand + write in exams easily**.

---

### PCA (Principal Component Analysis)

**Principal Component Analysis (PCA)** is a **statistical technique** used to **reduce the number of features (dimensions)** in a dataset **without losing important information**.

👉 It changes many related variables into **fewer new variables** called **principal components**.

---

#### 2️⃣ Why PCA is Used

PCA is used because:

* Datasets may have **too many features**
* Some features are **correlated**
* High-dimensional data is **hard to process and visualize**
* Models become **slow and overfit**

👉 PCA makes data **simpler, faster, and cleaner**.

---

#### 4️⃣ Principal Components (Easy Meaning)

* A **principal component** is a **new feature**
* It is a **combination of original features**
* All components are:

  * **Uncorrelated**
  * **Ordered by importance**

Example:

```
PC1 → most information  
PC2 → second most information
```

---

#### 5️⃣ How PCA Works (Step-by-Step)

1. **Collect the data**
2. **Standardize the data** (mean = 0, variance = 1)
3. **Calculate covariance matrix**
4. **Find eigenvalues and eigenvectors**
5. **Choose top principal components**
6. **Transform original data into new space**

---

#### 6️⃣ Simple Example

Suppose we have:

* Height
* Weight

These are related (tall people usually weigh more).

👉 PCA combines them into:

* **PC1** → body size
* **PC2** → small variation

So we keep **PC1** and remove **PC2**.

**Principal Component Analysis (PCA) is a dimensionality reduction technique used to convert a large set of correlated variables into a smaller set of uncorrelated variables called principal components. It preserves maximum variance from the original data and helps reduce complexity, noise, and computation time in machine learning tasks.**

Below is a **clear, simple, exam-ready explanation of LDA**, followed by a **PCA vs LDA difference table**, all in **easy English** 👍

---
![PCA](https://www.simplilearn.com/ice9/free_resources_article_thumb/PrincipalComponents.PNG)

## What is LDA? (Linear Discriminant Analysis)

**Linear Discriminant Analysis (LDA)** is a **supervised machine learning technique** used for **feature reduction and classification**.

👉 LDA tries to **separate different classes as clearly as possible** by finding new features.

**Simple idea of LDA**

* Data has **labels (classes)**
* LDA finds directions where:

  * Distance **between classes is maximum**
  * Distance **within the same class is minimum**

So, classes become **well separated**.

**How LDA Works (Simple Steps)**

1. Take labeled data
2. Compute class means
3. Measure within-class scatter
4. Measure between-class scatter
5. Find directions that maximize separation
6. Project data into new space

**LDA is a supervised dimensionality reduction technique that maximizes class separation.**

---

### PCA vs LDA (Difference Table)

| Feature           | **PCA**                      | **LDA**                      |
| ----------------- | ---------------------------- | ---------------------------- |
| Full form         | Principal Component Analysis | Linear Discriminant Analysis |
| Learning type     | Unsupervised                 | Supervised                   |
| Uses class labels | ❌ No                        | ✅ Yes                      |
| Main goal         | Maximize variance            | Maximize class separation    |
| Focus             | Data spread                  | Class discrimination         |
| Components        | Principal components         | Linear discriminants         |
| Best for          | Data compression             | Classification               |
| Class information | Ignored                      | Used                         |
| Output dimensions | ≤ number of features         | ≤ number of classes − 1      |
| Example use       | Image compression            | Face recognition             |

# **1️⃣ Classification Techniques — Nearest Neighbor Rule and Bayes Classifier**

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

![Image](https://media.licdn.com/dms/image/v2/D4D12AQEaIeOIleYxQw/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1711781577058?e=2147483647&v=beta&t=F4KOa5-9KrMTNzkxJ9FIRxNFHdvn3nd_Xu00CI4I1Lo)


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

![Image](https://cdn.analyticsvidhya.com/wp-content/uploads/2020/10/56854k-means-clustering.webp)
![Image](https://media2.dev.to/dynamic/image/width=1000,height=420,fit=cover,gravity=auto,format=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fsi47k1tq6ool8g1qnsg1.png)

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

#### 1️⃣ Category of Clustering Scheme of K-Means

The **k-means algorithm** belongs to the **partition-based (partitional) clustering** category.

👉 It divides the dataset into **k non-overlapping clusters**, where each data point belongs to **only one cluster**.

---

#### 2️⃣ Major Advantage of K-Means

The **major advantage of k-means** is that it is:

✔ **Simple and fast**
✔ **Easy to understand and implement**
✔ **Efficient for large datasets**

Because of its simplicity, k-means is widely used in real-world clustering problems.

---

#### 3️⃣ Factors Influencing Computation Duration of K-Means

The time taken by the k-means algorithm mainly depends on the following factors:

1. **Number of Data Points (n)**
   More data points → more distance calculations → more time.

2. **Number of Clusters (k)**
   Higher value of k increases computation.

3. **Number of Dimensions (d)**
   More features per data point increase distance calculation time.

4. **Number of Iterations (i)**
   More iterations needed for convergence increase execution time.

5. **Initialization of Centroids**
   Poor initial centroids may lead to more iterations.

## ⭐ **4. Support Vector Machine (SVM)**

![Image](https://miro.medium.com/v2/resize:fit:1400/1*qGl9Os6nA82aQrDUhZ7zOQ.png)

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