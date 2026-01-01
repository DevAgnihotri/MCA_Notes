# 🤖 **UNIT: MACHINE LEARNING & STATISTICAL LEARNING METHODS**

---

## 🧩 **1️⃣ Machine Learning – Introduction, Types, and Application Areas**

---
- What is machine learning? Differentiate between supervised, unsupervised and reinforcement learning. (2022 — Section B Q2(d))  
- Define the term machine learning. (2023 — Section A Q1(g))  
- Write short note on machine learning. (2024 — Section C Q6(a) ii)

### 🔹 **Definition**

*(2023 – Section A Q1(g); 2024 – Section C Q6(a)ii)*

**Machine Learning (ML)** is a field of Artificial Intelligence that enables systems to **learn from data** and **improve their performance automatically** without being explicitly programmed.

> 🧠 “ML is about teaching computers to learn patterns from experience.”

### ⚙️ **Basic Idea**

An ML model learns from **training data**, builds a pattern, and uses it to **make predictions or decisions** on new data.

### 💡 **Example**

If you feed a model with pictures of dogs and cats, it learns to **recognize differences** and can later classify a new picture as a dog or a cat.

---

### 🔹 **Types of Machine Learning**

*(2022 – Section B Q2(d))*

| Feature        | **Supervised Learning**       | **Unsupervised Learning**       | **Reinforcement Learning**      |
| -------------- | ----------------------------- | ------------------------------- | ------------------------------- |
| Meaning        | Learns using **labeled data** | Learns using **unlabeled data** | Learns by **trial and error**   |
| Data type      | Input + correct output        | Only input data                 | No dataset, learns from actions |
| Label          | labeling is present           | No labeling                     | No Labeling, only feedback      |
| Feedback       | Immediate and correct         | No feedback                     | Reward or punishment            |
| Goal           | Predict correct output        | Find hidden patterns            | Maximize total reward           |
| Learning style | Learn from examples           | Discover structure              | Learn from experience           |
| Output         | Known classes or values       | Groups or patterns              | Best action or policy           |
| Common tasks   | Classification, Regression    | Clustering, Association         | Decision making, control        |
| Algorithms     | Linear Regression, SVM        | K-Means, Apriori                | Q-Learning, SARSA               |
| Example        | Spam email detection          | Customer grouping               | Game playing, robots            |

---

### Steps in Machine Learning Process (Simple Points)

1. **Data Collection**
   Data is collected from different sources like files, databases, or sensors.

2. **Data Preparation**
   Data is cleaned by removing errors, missing values, and unwanted information.

3. **Feature Selection**
   Important data fields are selected that help in learning.

4. **Choose ML Algorithm**
   A suitable algorithm is chosen (like regression, classification, etc.).

5. **Model Training**
   The algorithm learns patterns from the training data.

6. **Model Testing**
   The trained model is tested using new or unseen data.

7. **Evaluation**
   The model’s accuracy and performance are checked.

8. **Prediction / Output**
   The model is used to make predictions or decisions.

9. **Improvement**
   More data is added to improve the model’s performance.

---

### 🧠 **Application Areas of Machine Learning**

| **Field**                       | **Example Application**          |
| :------------------------------ | :------------------------------- |
| **Healthcare**                  | Predict diseases, analyze X-rays |
| **Finance**                     | Credit scoring, fraud detection  |
| **Retail**                      | Recommendation systems           |
| **Agriculture**                 | Crop prediction, soil monitoring |
| **Autonomous Systems**          | Robotics, self-driving cars      |
| **Natural Language Processing** | Chatbots, translation            |

---

### ✅ **Short Note Summary (2024 – Section C Q6(a)ii)**

Machine learning is a **data-driven approach** that helps systems automatically **improve accuracy** with experience.
It uses algorithms like **decision trees, neural networks, SVM, clustering**, etc., across multiple domains such as **healthcare, business, and automation**.

---

## 🌳 **2️⃣ Decision Trees**

- Describe the decision tree-learning model by choosing a suitable example. Discuss issues related to the application of decision tree. (2022 — Section C Q6(a))  
- Discuss steps and algorithm to construct a decision tree. (2023 — Section C Q6(b))  
- Describe decision tree with diagram. (2024 — Section A Q1(h))

---

### 🔹 **Definition**

A **Decision Tree** is a **supervised learning model** used for both **classification and regression** tasks.
It represents decisions in the form of a **tree-like structure** — each internal node represents a **test on an attribute**, each branch represents an **outcome**, and each leaf node represents a **final decision or class**.

> 📊 It works by recursively splitting the data based on feature values.

---

### 🧱 **Structure Example (2024 – Section A Q1(h))**

```
           [Weather]
          /         \
      Sunny         Rainy
       /               \
 [Play=Yes]         [Play=No]
```

Here, the tree classifies whether to “Play” based on “Weather.”


![](https://www.techguruspeaks.com/wp-content/uploads/2020/05/dt.png)


### Simple Steps to Make a Decision Tree (DT)

1. **Collect the Data**
   Gather the data that you want to use for prediction.

2. **Choose the Target Column**
   Decide what you want to predict (output or class).

3. **Select the Best Feature**
   Choose the feature that best splits the data
   (using entropy, information gain, or Gini index).

4. **Create a Root Node**
   The best feature becomes the top (root) node of the tree.

5. **Split the Data**
   Divide the data into smaller groups based on the selected feature.

6. **Create Decision Nodes**
   Repeat the process for each group using remaining features.

7. **Create Leaf Nodes**
   Stop splitting when:

   * All data belongs to one class, or
   * No feature is left

8. **Make Prediction**
   Use the tree to predict output for new data.

---

### ⚠️ **Issues in Decision Tree Learning**

*(2022 – Section C Q6(a))*

1. **Overfitting:** Tree becomes too complex, fitting even noise.
2. **Bias toward attributes with many values.**
3. **Handling continuous data** is complex.
4. **Missing values** may reduce accuracy.
5. **Pruning** required to simplify the tree.

---

### ✅ **Advantages**

* Easy to understand and interpret.
* Works with both numerical and categorical data.
* Requires little data preparation.

---

### ❌ **Disadvantages**

* Can overfit noisy data.
* Small changes in data can cause different splits.
* Greedy algorithms (like ID3) don’t guarantee globally optimal trees.

---

## 📊 **3️⃣ Statistical Learning Methods**


- What are statistical learning models? (2022 — Section A Q1(h))  
- What is Statistical learning method? (2024 — Section A Q1(g))  
- Write short note on Support Vector Machine (SVM). (2022 — Section A Q1(i))  
---

### 🔹 **Definition**

*(2022 – Section A Q1(h); 2024 – Section A Q1(g))*

**Statistical learning methods** are **mathematical models** that use **probability and statistics** to make predictions based on data.
They find the best function that maps input variables (X) to output variables (Y).

> Example: Linear regression, Logistic regression, SVM, Clustering.

---

### 🧠 **Key Statistical Models**

1. **Regression Models:** Predict continuous values (e.g., price, temperature).
2. **Classification Models:** Predict categories (e.g., spam or not spam).
3. **Clustering Models:** Group similar data points.
4. **Support Vector Machines (SVM):** Separate classes with an optimal boundary.


# 📘 **Learning with Complete Data, Hidden Data & Reinforcement Learning**

---

## 🔹 **1️⃣ Learning with Complete Data – Concept & Naïve Bayes Model**

---

### 🧠 **Concept of Learning with Complete Data**

When **all the data and their class labels are available** to the learning algorithm, we call it **learning with complete data**.

* The dataset contains **input features (X)** and **corresponding output labels (Y)**.
* The goal is to learn a model **P(Y|X)** — the probability of each class given the data.

> 📘 Example: In spam email detection, every training email is already labeled as “spam” or “not spam”.

---

### 🔸 **Maximum Likelihood Estimation (MLE)**

*(2023 – Section C Q6(a))*

Maximum Likelihood Estimation is a technique that selects model parameters which maximize the likelihood of the observed data.

#### Formula:

[
\hat{θ} = argθmaxL(θ)
]

It means: choose parameters that make the observed data most likely.

**Example:**
If we observe 70 heads in 100 coin tosses, MLE estimates probability of head as 0.7.

If coin toss data shows many heads, MLE estimates the coin’s head probability close to that value.

---

### 🔹 **Naïve Bayes Model**

*(2023 – Section B Q2(d); 2024 – Section C Q6(b))*

# Naive Bayes Classifier

## 1️⃣ What is Naive Bayes?

**Naive Bayes** is a **simple and fast classification algorithm** based on **Bayes’ Theorem**.

👉 It predicts the **class** of data using **probability**.

---

## 2️⃣ Why is it called “Naive”?

It is called **naive** because it assumes:

* All features are **independent** of each other

👉 This assumption is usually not true in real life, but the algorithm still works well.

---

## 3️⃣ Bayes’ Theorem (Base Formula)

![Bayes Theorem](https://cdn1.byjus.com/wp-content/uploads/2020/10/Bayes-Theorem.png)

Where:

* (A) = class
* (B) = data / features

---

## 4️⃣ How Naive Bayes Works (Simple Idea)

> **Choose the class with the highest probability given the data.**

---

## 5️⃣ Step-by-Step Working

1. Identify all possible **classes**
2. Calculate **prior probability** of each class
3. Calculate **likelihood** of features for each class
4. Multiply probabilities
5. Choose class with **maximum probability**

---

## 6️⃣ Types of Naive Bayes

### 1. Gaussian Naive Bayes

* Used for **continuous data**

### 2. Multinomial Naive Bayes

* Used for **text / word counts**

### 3. Bernoulli Naive Bayes

* Used for **binary data**

---

## 7️⃣ Simple Example (Spam Email)

Features:

* Words like “free”, “offer”

Classes:

* Spam
* Not Spam

👉 Naive Bayes calculates probability and predicts **Spam** or **Not Spam**.

**Naive Bayes is a probabilistic classifier based on Bayes’ theorem that assumes independence between features. It is simple, fast, and widely used for text classification and spam detection.**


**Naive Bayes = Probability + Independence**

---

# 🔹 **2️⃣ Learning with Hidden Data – Concept & EM Algorithm**

---
- Discuss back propagation algorithm for learning in multilayer neural network. (2019 — Section C Q7(a))  
- What do you mean by statistical learning? Explain Naïve Bayes model. (2023 — Section B Q2(d))  
- Explain discrete model, Naïve Bayes Model & Continuous Model. (2024 — Section C Q6(b))  
- What do you mean by Maximum Likelihood estimation? (2023 — Section C Q6(a))

### 🧠 **Concept**

In **learning with hidden (incomplete) data**, some parts of the data are **not directly observable** — they are hidden variables.
The model must estimate both the **hidden variables** and the **parameters**.

> 💡 Example: In clustering or HMMs, the class labels or hidden states are not known in advance.

---

### 🔹 **Maximum Likelihood with Hidden Variables**

We cannot compute likelihood directly because hidden variables (Z) are missing.
So, we estimate parameters **θ** that maximize:
[
P(X|theta) = sigma(Z) P(X,Z|theta)
]

This is where the **Expectation-Maximization (EM) Algorithm** is used.

---

## ⚙️ **Expectation–Maximization (EM) Algorithm**

*(2022 – Section C Q6(b); 2023 – Section C Q6(a); 2024 – Section B Q2(d))*
- Explain the expectation and maximization (EM) algorithm for finding the maximum likelihood with hidden variables. (2022 — Section C Q6(b))  
- What do you mean by Maximum Likelihood estimation? Also explain Expectation Maximization algorithm. (2023 — Section C Q6(a))  
- Explain learning with hidden data – EM algorithm. (2024 — Section B Q2(d))  
- Describe the use of Hidden Markov models in speech recognition. (2024 — Section B Q2(c))

#### 📘 **Definition:**

The **EM Algorithm** is an **iterative optimization technique** used to estimate parameters of models that involve **hidden (latent) variables**.

It works in two steps:

**E-step (Expectation Step):** Using the current parameter estimates, the algorithm calculates the expected values of the missing or hidden variables. 

**M-step (Maximization Step):** With these updated expectations from the E-step, the algorithm then re-estimates the model parameters by maximizing the expected log-likelihood. This improves how well the model explains the observed data.

These two steps are repeated until convergence, which typically means that:

- The parameter values stop changing significantly, or
- The log-likelihood improves only by a negligible amount.

![](https://media.geeksforgeeks.org/wp-content/uploads/20250905113438630863/update.webp)

It alternates between two steps until convergence:

Key Terms in Expectation-Maximization (EM) Algorithm
Lets understand about some of the most commonly used key terms in the Expectation-Maximization (EM) Algorithm:

- **Latent Variables**: Variables that are not directly observed but are inferred from the data. 

- **Likelihood**: The probability of the observed data given a set of model parameters.

- **Log-Likelihood**: The natural logarithm of the likelihood function. It simplifies calculations (turning products into sums) and is numerically more stable when dealing with very small probabilities.

- **Posterior Probability**: In Bayesian inference, this represents the probability of parameters (or latent variables) given the observed data and prior knowledge. 

- **Convergence**: The stopping criterion for the iterative process. 
---

![](https://miro.medium.com/v2/resize:fit:1400/0*wsw3SMgEGfOUH_rU.jpg)


### 🔸 **Steps of EM Algorithm**

1. **Initialization:**
   Start with initial guess of parameters (θ₀).

2. **E-Step (Expectation):**
   Estimate the expected value of the hidden variables (Z) given the observed data (X) and current parameter estimates (θᵗ).

3. **M-Step (Maximization):**
   Find parameters that **maximize** this expectation.

4. **Repeat:**
   Until convergence (parameters stop changing).


---

### 🔹 **Applications of EM Algorithm**

* Hidden Markov Models (HMM) parameter estimation
* Clustering (Gaussian Mixture Models)
* Image segmentation
* Missing data handling

---

### ✅ **Advantages**

* Can handle missing or incomplete data.
* Guarantees convergence (though may be to local optimum).

### ❌ **Disadvantages**

* Convergence can be slow.
* May get stuck in local optima.

---

---

## 🔹 **3️⃣ Reinforcement Learning (RL)**

---
- Write a short note on reinforcement learning. (2023 — Section A Q1(h))  
- Short note on Reinforcement learning. (2024 — Section C Q6(a) i)

### 🧠 **Definition**

*(2023 – Section A Q1(h); 2024 – Section C Q6(a)i)*

**Reinforcement Learning (RL)** is a type of machine learning where an **agent learns by interacting with an environment** and receives **rewards or penalties** for its actions.

> The agent learns to choose actions that **maximize total reward** over time.

---

### ⚙️ **Key Components**

| **Component**   | **Description**                              |
| :-------------- | :------------------------------------------- |
| **Agent**       | Learner or decision maker                    |
| **Environment** | The world the agent interacts with           |
| **State (S)**   | Current situation of the agent               |
| **Action (A)**  | Choices available to the agent               |
| **Reward (R)**  | Feedback received after performing an action |

---

### 🔁 **Working Cycle**

1. Agent observes **current state**.
2. Takes an **action**.
3. Environment gives **reward** and **next state**.
4. Agent updates policy to maximize **future rewards**.

---

### 📘 **Example:**

A robot vacuum learns to clean efficiently:

* +10 reward for cleaning dust.
* -5 penalty for bumping into walls.
* Over time, it learns a path that maximizes rewards.

---

### 🔹 **Core Concepts**

| **Term**                        | **Meaning**                                              |
| :------------------------------ | :------------------------------------------------------- |
| **Policy (π)**                  | Strategy that defines which action to take in each state |
| **Value Function (V)**          | Expected reward for following a policy                   |
| **Q-Function (Q)**              | Expected reward for taking a specific action in a state  |
| **Exploration vs Exploitation** | Trying new actions vs choosing known best actions        |

---

### 🔹 **Popular Algorithms**

* **Q-Learning**
* **SARSA**
* **Deep Q-Networks (DQN)**

---

### ✅ **Applications**

* Game playing (Chess, Go, AlphaZero)
* Robotics and autonomous driving
* Recommendation systems
* Resource management in cloud computing

---
