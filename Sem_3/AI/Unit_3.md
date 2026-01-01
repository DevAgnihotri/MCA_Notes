# 🤖 **Artificial Intelligence — Logic & Knowledge Representation**

## 🧠 **1️⃣ Knowledge Representation (KR)**

---

Knowledge Representation
- What do you mean by knowledge representation? Describe the techniques of knowledge representation. [2024 – SECTION C Q5(a)]
- Represent the following in partitioned semantic networks: (i) Every player kicked a ball. (ii) All players like the referee. (iii) Andrew believes that there is a fish with lungs. [2019 – SECTION C Q5(a)]



### 🔹 **Definition:**

**Knowledge Representation** is the **way in which intelligent systems store and organize knowledge** about the world so they can use it for reasoning and decision-making.

> In simple words — it’s _how a computer “knows” and “understands” facts, objects, and relationships._

---

### 💡 **Purpose of KR:**

- To **store information** in a computer-understandable form.
- To **make reasoning possible** (draw conclusions).
- To **model real-world situations** logically.
- To **enable AI systems** (like chatbots or expert systems) to act intelligently.

---

### ⚙️ **Desirable Properties of a Good KR System:**

1. **Representational Adequacy:** Can express all types of required knowledge.
2. **Inferential Adequacy:** Can derive new knowledge from stored facts.
3. **Inferential Efficiency:** Can reason quickly and effectively.
4. **Acquisitional Efficiency:** Easy to acquire new knowledge.

---

### 🔸 **Techniques of Knowledge Representation:**

| **Technique**                     | **Explanation**                                                                                        | **Example**                                          |
| :-------------------------------- | :----------------------------------------------------------------------------------------------------- | :--------------------------------------------------- |
| **1. Logical Representation**     | Uses formal logic (propositional/predicate) to express knowledge in statements that are true or false. | “All humans are mortal.” = ∀x (Human(x) → Mortal(x)) |
| **2. Semantic Networks**          | Knowledge is represented as a **graph** — nodes = objects/concepts, edges = relationships.             | “Dog is an Animal” → Dog → is-a → Animal             |
| **3. Frame-based Representation** | Similar to object-oriented model — uses “frames” (data structures) that store attributes and values.   | Frame: Car {Wheels:4, Engine:Yes}                    |
| **4. Production Rules**           | Uses **IF–THEN** rules to represent actions or decisions.                                              | IF temperature > 38°C THEN fever = True              |
| **5. Ontologies**                 | Hierarchical structure defining categories, properties, and relationships between concepts.            | Ontology of Animals: Mammals → Humans, Dogs, etc.    |

---

### 🧩 **Partitioned Semantic Networks Examples**

> 2019 Q: Represent in partitioned semantic networks:
> 1️⃣ Every player kicked a ball.
> 2️⃣ All players like the referee.
> 3️⃣ Andrew believes that there is a fish with lungs.

---

#### (i) Every player kicked a ball

- Nodes: Player, Ball, Kicked
- Links: _Agent → Player_, _Object → Ball_
  **Structure:**

```
Event: Kick
 → Agent: Player
 → Object: Ball
```

#### (ii) All players like the referee

```
Player → likes → Referee
```

#### (iii) Andrew believes that there is a fish with lungs

```
Andrew → believes → [Fish → has → Lungs]
```

Each “partition” (bracket) represents a **different belief context**, showing Andrew’s belief without asserting it as fact in the real world.

---

## ⚙️ **2️⃣ Propositional Logic**

---

Propositional logic / Predicate logic
- Compare propositional logic and predicate logic. [2019 – SECTION A Q1(d)]
- Compare propositional logic and predicate logic. [2022 – SECTION A Q1(f)]
- Justify the usage of universal and existential quantifier with an example. [2019 – SECTION A Q1(e)]
- Justify the usage of universal and existential quantifier with an example. [2022 – SECTION A Q1(e)]

### 🔹 **Definition:**

Propositional logic is a **simple form of logic** where knowledge is represented using **propositions** — statements that are **either true or false**.

> It deals with combining and modifying whole statements using **logical connectives** (AND, OR, NOT, →, ↔).

---

### 🔸 **Examples:**

| English                              | Propositional Form |
| :----------------------------------- | :----------------- |
| It is raining.                       | P                  |
| It is cold.                          | Q                  |
| It is raining AND cold.              | P ∧ Q              |
| If it rains, then the ground is wet. | P → Q              |

---

### ⚙️ **Limitations:**

- Cannot express relationships between objects (like “All humans are mortal”).
- Cannot use quantifiers (“every”, “some”).

---

## 🧩 **3️⃣ Predicate Logic (First-Order Logic)**

---

### 🔹 **Definition:**

**Predicate Logic (FOL or FOPL)** extends propositional logic by allowing **variables, quantifiers, and relationships** among objects.

> It represents facts like “All humans are mortal” instead of just “It is raining.”

---

### 🔸 **Components of Predicate Logic:**

| **Component**   | **Meaning**                                          |
| :-------------- | :--------------------------------------------------- |
| **Constants**   | Specific objects (e.g., Socrates, India)             |
| **Variables**   | x, y, z — represent objects                          |
| **Predicates**  | Properties or relations (e.g., Human(x), Loves(x,y)) |
| **Quantifiers** | Universal (∀) and Existential (∃)                    |
| **Connectives** | AND (∧), OR (∨), NOT (¬), IMPLIES (→)                |

---

### 💡 **Quantifiers (with examples):**

| **Quantifier**             | **Symbol** | **Meaning**              | **Example**                                                    |
| :------------------------- | :--------- | :----------------------- | :------------------------------------------------------------- |
| **Universal Quantifier**   | ∀          | “For all” or “Every”     | ∀x (Human(x) → Mortal(x)) → “All humans are mortal.”           |
| **Existential Quantifier** | ∃          | “There exists” or “Some” | ∃x (Bird(x) ∧ CanFly(x)) → “There exists a bird that can fly.” |

_(Asked in 2019 & 2022: “Justify usage of quantifiers with examples.”)_

---

### ⚖️ **Propositional Logic vs Predicate Logic**

| **Basis**          | **Propositional Logic**               | **Predicate Logic**                         |
| :----------------- | :------------------------------------ | :------------------------------------------ |
| **Structure**      | Uses simple propositions (true/false) | Uses objects, variables, and relations      |
| **Expressiveness** | Limited                               | More powerful                               |
| **Quantifiers**    | Not used                              | Uses ∀ and ∃                                |
| **Example**        | “It is raining.”                      | “For all clouds, if it is heavy, it rains.” |
| **Use Case**       | Simple reasoning                      | Complex knowledge reasoning                 |

---

## 🧩 **4️⃣ First Order Predicate Logic (FOPL)**

---

First Order Logic (FOPL)
- Write the steps for converting FOPL into CNF. [2022 – SECTION B Q2(c)]
- Explain concept and use of clause form conversion algorithm. [2023 – SECTION C Q5(a)]

Inference in First Order Logic / Resolution
- Give the completeness proof of resolution. [2019 – SECTION B Q2(e)]
- Convert the following sentence into predicate logic and then prove “Was Marcus loyal to Caesar?” using resolution (full 8‑statement problem). [2022 – SECTION C Q5(a)]

### 🔹 **Definition:**

**First Order Predicate Logic** is the formal system that combines **predicate logic and quantifiers** to describe **objects, their properties, and relationships**.

It forms the **foundation for AI reasoning**, allowing systems to deduce new facts.

---

### ⚙️ **Conversion of FOPL into CNF (Conjunctive Normal Form)**

_(Asked in 2022 B Q2(c) and 2023 C Q5(a))_

---

### 🔸 **Steps for Conversion:**

1. **Eliminate implications (→):**
   Replace (P → Q) with (¬P ∨ Q)
   p <-> Q then (P->Q) ulta V (Q -> P)

2. **Move NOT (¬) inward:**

   Apply De Morgan’s Laws and remove double negations.

3. **Standardize variables:**
   Rename variables so each quantifier has a unique variable.

4. **Move quantifiers to front:**
   Make explicit scope of ∀ and ∃.

5. **Skolemization:**
   Remove ∃ quantifiers by introducing constants/functions.

6. **Drop universal quantifiers:**
   All remaining variables are considered universally quantified.

7. **Distribute ∨ over ∧:**
   Get the final **CNF** (conjunction of disjunctions).

---

### 🧠 **Example:**

```
∀x (Man(x) → Mortal(x))
```

→ Eliminate → : ¬Man(x) ∨ Mortal(x)
→ CNF: (¬Man(x) ∨ Mortal(x))

---

# 🧩 **5️⃣ Inference in First Order Logic**

---

### 🔹 **Definition:**

**Inference** is the process of **deriving new facts or conclusions** from existing knowledge using rules of logic.

> In AI, inference enables machines to think and reason logically like humans.

---

### ⚙️ **Main Inference Techniques:**

| **Technique**         | **Description**                                                                     |
| :-------------------- | :---------------------------------------------------------------------------------- |
| **Forward Chaining**  | Start from known facts and apply inference rules to reach new facts.                |
| **Backward Chaining** | Start from the goal and find supporting facts backward.                             |
| **Resolution**        | A powerful single inference rule that refutes contradictions to prove a conclusion. |

| Feature        | **Forward Chaining**                                | **Backward Chaining**                           |
| -------------- | --------------------------------------------------- | ----------------------------------------------- |
| Meaning        | Starts from **facts** and moves forward             | Starts from a **goal** and moves backward       |
| Direction      | **Data → Conclusion**                               | **Goal → Data**                                 |
| Starts with    | Known **facts / data**                              | Desired **goal / result**                       |
| Main question  | *“What can I conclude from this data?”*             | *“Is this goal true?”*                          |
| How it works   | Applies rules again and again to get new facts      | Checks rules that can prove the goal            |
| Stops when     | No new facts are found                              | Goal is proved or fails                         |
| Best used when | You have **lots of data**                           | You have a **clear goal**                       |
| Speed          | Can be slow (checks many rules)                     | Faster (checks only needed rules)               |
| Example system | Expert systems, monitoring systems                  | Diagnostic systems                              |
| Simple example | If **rain → wet road**, rain is known → road is wet | Want to know **road wet?** → check if it rained |


## **QUESTION** Given Knowledge Base (KB)

Facts and rules:

1. **P** → (Fact)
2. **P → Q** → (Rule)
3. **Q → R** → (Rule)

**Goal:** Infer **R**

---

### 1️⃣ Forward Chaining (Data-Driven Reasoning)

### Meaning

Forward chaining starts with **known facts** and moves **forward** by applying rules until the goal is reached.

---

### Step-by-Step Inference

**Step 1:**
Known fact:

* **P** is true

**Step 2:**
Rule: **P → Q**
Since **P** is true, we can infer:

* **Q** is true

**Step 3:**
Rule: **Q → R**
Since **Q** is true, we can infer:

* **R** is true

---

### ✅ Final Conclusion (Forward Chaining)

**R is inferred successfully.**

---

### Flow (easy to remember)

```
P  →  Q  →  R
```

---

### 2️⃣ Backward Chaining (Goal-Driven Reasoning)

### Meaning

Backward chaining starts with the **goal** and works **backward** to see if known facts can support it.

---

### Step-by-Step Inference

**Step 1:**
Goal:

* Prove **R**

**Step 2:**
Look for a rule that concludes **R**:

* Rule found: **Q → R**

So now, we must prove:

* **Q**

**Step 3:**
Look for a rule that concludes **Q**:

* Rule found: **P → Q**

So now, we must prove:

* **P**

**Step 4:**
Check the knowledge base:

* **P** is already given as a fact

So **P is true**, hence **Q is true**, hence **R is true**.

---

### ✅ Final Conclusion (Backward Chaining)

**R is inferred successfully.**

---

### Flow (easy to remember)

```
R ← Q ← P
```

---
### **Resolution in Inference Technique (AI)** – *Simple English*

**Resolution** is a **rule used in Artificial Intelligence** to **prove a statement is true or false** by **logic**.

### Simple definition 👇

👉 **Resolution is a method of reasoning that proves conclusions by removing contradictions from logical statements.**

---

### How it works (easy steps) 🧩

1. All statements are converted into **clauses** (simple logical sentences).
2. Opposite literals are matched (like **A** and **¬A**).
3. They are **removed (resolved)**.
4. A new clause is formed.
5. Process repeats until:

   * **Empty clause** is found → statement is **TRUE**
   * No more resolution possible → statement is **FALSE**

---

### One-line definition (exam-ready) 📝

**Resolution is an inference technique that derives new clauses by eliminating opposite literals to prove logical statements.**

---

### Simple example 💡

Statements:

* `A OR B`
* `¬A OR C`

Resolve on **A**:
➡ Result: `B OR C`

---

### Memory trick 🔑

**Resolution = Remove Opposites**

---

### 🧠 **Example (2019 & 2022 Long Problem)**

Prove: “Was Marcus loyal to Caesar?”

_(You’d be given 8 statements like “Marcus is a man”, “All men are mortal”, “Loyal people obey their masters”, etc.)_
You:

1. Convert each statement into predicate logic.
2. Negate the goal (“Marcus was not loyal to Caesar”).
3. Use resolution steps until contradiction arises.
4. Hence prove **Marcus was loyal**.

---

### ⚖️ **Completeness Proof of Resolution (2019 B Q2(e))**

Resolution is **complete** because:

- If a conclusion is logically entailed by premises,
  the resolution procedure will eventually find the contradiction (empty clause).
- This ensures that **resolution can derive any valid conclusion**.

---

perfect dear 💖 — here’s your **next AI section** fully written in clean exam-style format:
it covers **Clause Form Conversion, Resolution, and Chaining (Forward & Backward)** with proper *theory, logic flow, and question-based structure* — based on your **2019–2024 AKTU pattern**.

---

## 🧩 **1️⃣ Clause Form Conversion**

- Write the steps for converting FOPL into CNF. [2022 – SECTION B Q2(c)]
- Explain concept and use of clause form conversion algorithm. [2023 – SECTION C Q5(a)]

---

### 🔹 **Meaning:**

Clause Form Conversion is the **process of transforming First-Order Predicate Logic (FOPL)** statements into a **standardized form** suitable for *automated reasoning* — especially for **Resolution**.

> In simple terms → converting logical sentences into **a set of clauses**, each a **disjunction (OR) of literals**, that computers can easily process.

---

### 🧭 **Why Conversion Is Needed**

* Computers perform reasoning using *resolution*, and resolution works only on **clause form (CNF)**.
* Hence, to use automated theorem proving, we first convert all logical sentences into **Conjunctive Normal Form (CNF)**.

---

### ⚙️ **Steps for Converting FOPL into CNF**

*(2022 – SECTION B Q2(c))*

1️⃣ **Eliminate implications (→)**
Replace ( P → Q ) with ( ¬P ∨ Q )

2️⃣ **Move negation (¬) inward**
Use **De Morgan’s Laws** and **double negation elimination** to push NOT inwards to atomic level.

* ¬(P ∧ Q) = ¬P ∨ ¬Q
* ¬(P ∨ Q) = ¬P ∧ ¬Q

3️⃣ **Standardize variables**
Rename variables so each quantifier has a unique variable (to avoid confusion).

4️⃣ **Move quantifiers to the left (Prenex form)**
Bring all quantifiers (∀, ∃) to the front of the expression.

5️⃣ **Skolemization**
Eliminate existential quantifiers (∃) by introducing **constants** or **functions** (called *Skolem functions*).
Example:
∃x P(x) → Replace x by a Skolem constant “a”: P(a)

6️⃣ **Drop universal quantifiers (∀)**
All remaining variables are assumed to be universally quantified.

7️⃣ **Distribute OR (∨) over AND (∧)**
Use distributive laws to make the expression a conjunction of disjunctions.

8️⃣ **Split into separate clauses**
Each conjunct (AND part) becomes one **clause**, which is a disjunction (OR) of literals.

---

### 🧠 **Example**

Convert ∀x (Man(x) → Mortal(x)) into CNF.

**Step 1:** Eliminate →
¬Man(x) ∨ Mortal(x)

**Step 2–8:** Already in simplest CNF form.
✅ **Clause Form:** {¬Man(x), Mortal(x)}

---

### 📘 **Clause Form Conversion Algorithm (2023 – SECTION C Q5(a))**

---

**Algorithm Steps:**

```
Input: A set of FOPL sentences.
Output: Set of clauses in CNF.

1. Eliminate → and ↔ connectives.
2. Move ¬ inwards (apply De Morgan’s laws).
3. Standardize variables.
4. Move all quantifiers to the left (Prenex form).
5. Eliminate existential quantifiers using Skolemization.
6. Drop all universal quantifiers.
7. Distribute ∨ over ∧ to form conjunction of disjunctions.
8. Break the conjunction into individual clauses.
9. Return the resulting set of clauses.
```

---

**Use:**
The clause form is **essential** for inference engines, resolution-based proof systems, and theorem provers.
It provides a **uniform structure** for logical comparison and unification.

---

## 🧩 **1️⃣ Utility Theory and Probabilistic Reasoning**

---

### 🔹 **Utility Theory – Meaning**

**Utility theory** deals with **decision-making under uncertainty**.
It helps an intelligent agent choose the **best possible action** when there are multiple options and outcomes are uncertain.

> 🧠 In simple words → utility means *usefulness or happiness*.
> An AI agent chooses the action that gives it **maximum expected utility**.

---

### ⚙️ **Key Concepts**

1. **Utility (U):**
   A measure of satisfaction or preference an agent gets from an outcome.
   Example: U(Winning a prize) = 100, U(Losing) = 0.

2. **Expected Utility (EU):**
   The **average utility** of an action, considering all possible outcomes and their probabilities.
   [
   EU(action) = \sum P(outcome) \times U(outcome)
   ]

3. **Principle of Maximum Expected Utility (MEU):**
   The rational agent should choose the action with the **highest expected utility**.

---

### 🔹 **Probabilistic Reasoning**

Probabilistic reasoning allows AI systems to **handle uncertainty** in the real world using **probability theory**.

> 💬 It’s reasoning with *incomplete, uncertain, or noisy information*.

---

### ⚙️ **Key Elements**

1. **Probability:**
   Measures likelihood of an event (0 ≤ P ≤ 1)

2. **Conditional Probability:**
   [
   P(A|B) = \frac{P(A ∧ B)}{P(B)}
   ]
   → Probability of A given B has occurred.

3. **Joint Probability:**
   P(A ∧ B) = Probability that both A and B happen.

4. **Bayes’ Theorem:**
   Used to reverse conditional probabilities.
   [
   P(H|E) = \frac{P(E|H) \times P(H)}{P(E)}
   ]
   Where H = hypothesis, E = evidence.

5. **Inference:**
   Calculating the probability of unobserved events from known data.

---

### ✅ **Example**

If 90% of students pass when they study (P(Pass|Study)=0.9),
and 0.6 of students study (P(Study)=0.6),
then probability of a student passing =
0.9 × 0.6 = **0.54 or 54%.**

---

### 🧠 **In Short**

Utility theory helps *decide* what’s best,
and probabilistic reasoning helps *estimate* what’s likely to happen.

---

## 🎯 **2️⃣ Hidden Markov Model (HMM)**

- Discuss the different design issues to be solved to use Hidden Markov Model for real world application. [2019 – SECTION B Q2(c)]
- Distinguish between Markov model and Hidden Markov Model (HMM). [2022 – SECTION C Q5(b)]
- Describe the use of Hidden Markov models in speech recognition. [2024 – SECTION B Q2(c)]
---

### 🔹 **Definition**

A **Hidden Markov Model** (HMM) is a **statistical model** that represents systems that are **partially observable** —
where you can **see the results (outputs)** but not the **internal states** that caused them.

> 🧩 It’s called “Hidden” because the true states of the system are not directly visible.

---

### 🧱 **Structure of HMM**

An HMM has three main parts:

1. **Set of States (S):**
   Possible internal states (e.g., sunny, rainy).

2. **Observations (O):**
   Visible outputs (e.g., person carries umbrella or not).

3. **Probabilities:**

   * **Transition Probability (A):** Probability of moving from one state to another.
     ( a_i{j} = P(s_j | s_i) )
   * **Emission Probability (B):** Probability of seeing an observation from a state.
     ( b_j(k) = P(o_k | s_j) )
   * **Initial Probability (π):** Probability of starting in a given state.

---

### 🔹 **Markov Model vs Hidden Markov Model**

| **Aspect**           | **Markov Model**               | **Hidden Markov Model (HMM)**           |
| :------------------- | :----------------------------- | :-------------------------------------- |
| **State Visibility** | States are visible             | States are hidden                       |
| **Observation**      | Directly observe state         | Observe outputs dependent on states     |
| **Example**          | Predicting next web page click | Speech recognition, weather forecasting |
| **Model**            | Simple Markov chain            | Probabilistic model with hidden layer   |

*(2022 – SECTION C Q5(b))*

---

### 💡 **Design Issues in Using HMM (2019 – SECTION B Q2(c))**

When applying HMMs to real-world problems, the following design questions must be solved:

1. **Evaluation Problem:**
   Given the model and a sequence of observations,
   → How likely is that sequence?
   → Solved by **Forward algorithm**.

2. **Decoding Problem:**
   Given the observations and the model,
   → What is the most likely sequence of hidden states?
   → Solved by **Viterbi algorithm**.

3. **Learning Problem:**
   How to estimate model parameters (A, B, π) from data?
   → Solved by **Baum–Welch algorithm (EM algorithm)**.

---

## HMM in Speech Recognition

A **Hidden Markov Model (HMM)** is a statistical model used in speech recognition to handle sounds that change over time. When a person speaks, the computer can hear the sound, but it cannot directly see the actual speech units (phonemes). These phonemes are called **hidden states**, while the sound signals we hear are called **observations**. HMM helps in finding the relationship between these hidden speech sounds and the observed audio signals using probability.

In speech recognition, each word is represented as an HMM. The model uses probabilities to move from one sound to another and to generate the observed speech signal. This speech signal is then compared with different HMMs and selects the word whose model gives the highest probability. In this way, HMM helps the computer convert spoken language into text accurately.

### Points: How HMM is Used in Speech Recognition

1. Speech is given as input through a microphone.
2. The speech signal is converted into small sound features.
3. Phonemes are treated as **hidden states** in HMM.
4. Audio features are treated as **observations**.
5. Transition probability shows movement between speech sounds.
6. Emission probability shows how sounds produce audio features.
7. HMM calculates the probability of different word models.
8. The word with the highest probability is selected as output.

---

### ⚙️ **Advantages of HMM**

* Handles **sequential data** and **temporal uncertainty**.
* Mathematically well-defined with solid learning algorithms.
* Suitable for **speech, handwriting, gesture**, and **bioinformatics**.

---

![Image](https://nipunbatra.github.io/hmm/images/fair_biased_images/hmm.svg)

## 🔗 **3️⃣ Bayesian Networks**

---
- What does a Bayesian network represent? [2022 – SECTION A Q1(j)]
- What is Bayesian network? Explain steps to create a Bayesian network. [2023 – SECTION C Q5(b)]
- Explain Bayesian networks. [2024 – SECTION A Q1(e)]
- What is Bayesian network? Explain steps to create a Bayesian network. [2023 – SECTION C Q5(b)] (duplicate entry from above)
- What does a Bayesian network represent? [2022 – SECTION A Q1(j)] (duplicate entry from above)

### 🔹 **Definition**

A **Bayesian Network (BN)** is a **directed acyclic graph (DAG)** that represents **probabilistic relationships** among a set of variables.

> Each node = a random variable.
> Each edge = probabilistic dependency (influence).

### 💡 **What It Represents**

*(2022 – SECTION A Q1(j))*

A Bayesian network represents:

* **Causal relationships** between events.
* **Conditional dependencies** using **Bayes’ theorem**.
* The **joint probability distribution** over all variables.

### **Components of a Bayesian Network**

1. **Nodes:** Represent random variables (e.g., Rain, Traffic, LateToWork).
2. **Directed Edges:** Show dependencies (e.g., Rain → Traffic).
3. **Conditional Probability Table (CPT):**
   Each node has a table defining the probability of that node given its parents.

### **Steps to Create a Bayesian Network**

*(2023 – SECTION C Q5(b), 2024 – SECTION A Q1(e))*

1. **Identify variables** in the domain (e.g., Weather, Traffic, Accident).
2. **Determine causal relationships** between variables.
3. **Draw a Directed Acyclic Graph (DAG)** connecting related variables.
4. **Assign conditional probability tables (CPTs)** for each variable.
5. **Use Bayes’ theorem** to perform inference on unknown variables.

---

### 🧠 **Example**

Let’s say:

* **Rain** influences **Traffic**,
* **Traffic** influences **LateToWork**.

Bayesian Network:

```
Rain → Traffic → LateToWork
```

Probabilities:

* P(Rain) = 0.3
* P(Traffic|Rain) = 0.8
* P(LateToWork|Traffic) = 0.7

→ Using these, we can compute P(LateToWork|Rain).

---

### 🔹 **Advantages of Bayesian Networks**

1. Handle **uncertainty** effectively.
2. Show **causal relationships** visually and mathematically.
3. Support **learning and updating** probabilities from data.
4. Useful in **medical diagnosis**, **fault detection**, and **forecasting**.

---

### 🔹 **Applications**

* **Medical diagnosis:** Predict diseases based on symptoms.
* **Spam filtering:** Probability of an email being spam.
* **Weather prediction:** Relationship between humidity, rain, and temperature.
* **Risk assessment:** Predicting financial risks or system failures.

---

### ⚖️ **Difference Between HMM and Bayesian Network**

| **Aspect**           | **Bayesian Network**          | **Hidden Markov Model**           |
| :------------------- | :---------------------------- | :-------------------------------- |
| **Type of Model**    | Static (non-temporal)         | Dynamic (time-based)              |
| **Structure**        | DAG (no time sequence)        | Sequential chain                  |
| **State Visibility** | All variables may be observed | Hidden states                     |
| **Example Use**      | Medical diagnosis             | Speech recognition, sequence data |