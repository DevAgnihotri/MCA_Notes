# AI Interview Cheat-Sheet — Simple, Focused, Example-Ready

Purpose: one file to quickly prepare for interviews. Simple English, short definitions, clear differences, and small examples you can explain in an interview. Treat this as your "no-brainer" reference.

## Table of Contents

1. [Introduction](#1-introduction)

- What is AI
- History & evolution
- Branches of AI
- AI vs ML vs Deep Learning vs Data Science
- Real-world applications
- Types of AI (Narrow/General/Super; machine memory types)

2. [Natural Language Processing (NLP)](#2-natural-language-processing-nlp)

- Text preprocessing
- Word embeddings (Word2Vec, GloVe)
- Sentiment analysis
- Chatbots and LLM basics (Transformers & Attention)

3. [Search and Problem Solving](#3-search-and-problem-solving)

- State space representation
- BFS / DFS
- Heuristics and A\* search
- Constraint Satisfaction Problems

4. [Knowledge Representation](#4-knowledge-representation-logic-of-knowledge)

- Facts, rules, inference
- Propositional logic
- Predicate logic
- Semantic networks & frames

5. [Reasoning Techniques](#5-reasoning-techniques)

- Forward and backward reasoning
- Logical inference rules
- Rule-based reasoning
- Common-sense reasoning

6. [Applications of AI (Logical Understanding)](#6-applications-of-ai-logical-understanding)

- Logical automation
- Prediction systems
- Image recognition
- NLP logic

7. [Ethics and Logic in AI](#7-ethics-and-logic-in-ai)

- Logical fairness, bias, transparency
- Decision-making vs human judgment
- Explainability

---

## 1. Introduction

Quick intro (one sentence): Artificial Intelligence (AI) is the design of machines or software that can perform tasks that normally require human intelligence.

- What is AI (definition, goals, applications)

  - Simple: AI tries to make computers _think_ or _act_ like humans for specific tasks.
  - Goals: automate tasks, make predictions, understand language, see images, plan actions.
  - Example applications: chatbots that answer questions, recommendation engines that suggest products, self-driving cars.

- History & evolution of AI

  - 1950s: idea and early symbolic AI (logic-based systems).
  - 1980s: expert systems (rules and knowledge bases).
  - 1990s–2000s: statistical ML (SVMs, tree models), growth of data.
  - 2010s+: Deep learning (neural networks) and transformers; huge data and compute.

- Branches of AI: short list and what they do

  - Machine Learning (ML): learn patterns from data.
  - Expert Systems: rules-based decision systems.
  - Natural Language Processing (NLP): work with text/speech.
  - Robotics: sense and act in the physical world.
  - Computer Vision: understand images and video.

- Difference between AI, ML, Deep Learning, Data Science

  - AI (broad): any system that does intelligent tasks.
  - ML (subset of AI): algorithms that learn from data (e.g., linear regression).
  - Deep Learning (subset of ML): neural networks with many layers (e.g., CNNs, transformers).
  - Data Science: practice of extracting insights from data (may use ML, statistics, visualization).

  Interview tip: say the hierarchy clearly — AI > ML > Deep Learning; Data Science uses ML but is focused on data and business value.

- Real-world applications (short bullets you can expand in answers)

  - Chatbots and virtual assistants (customer support).
  - Recommendation engines (Netflix, Amazon).
  - Autonomous vehicles (perception + decision making).
  - Fraud detection, medical diagnosis, predictive maintenance.

- Types of AI (Simple taxonomy)

  - Narrow AI (weak): does one task (e.g., spam filter). This is what exists today.
  - General AI: theoretical — human-level multi-task intelligence.
  - Super AI: beyond human intelligence (speculative).

- Machine types by memory/ability (Minsky-style)
  - Reactive machines: no memory, respond to current input (e.g., chess engine without learning).
  - Limited memory: can use recent history (many ML systems, RL agents).
  - Theory of mind: can model others (advanced research area).
  - Self-aware AI: hypothetical, has self-model (future spec).

---

## 2. Natural Language Processing (NLP)

Short intro: NLP helps computers understand and generate human language.

- Text preprocessing (Tokenization, Stop words, Lemmatization, Stemming)

  - Tokenization: split text into words or tokens. Example: "I love AI." → ["I","love","AI","."]
  - Stop words: common words filtered out ("the", "is"). Useful to reduce noise in some tasks.
  - Stemming: chop words to a root form by simple rules ("running" → "run"). Fast but rough.
  - Lemmatization: smarter root extraction using vocabulary/grammar ("better" → "good").

  Interview tip: explain difference — stemming is crude and fast; lemmatization is slower but linguistically correct.

- Word embeddings (Word2Vec, GloVe) — concept level

  - Idea: map words to numbers (vectors) so similar words are close in vector space.
  - Word2Vec (predicts neighbors) and GloVe (uses global co-occurrence) are classical methods.
  - Example explanation: "king - man + woman ≈ queen" shows semantic meaning in vectors.

- Sentiment Analysis (intro)

  - Task: predict the emotional tone (positive, negative, neutral) of text.
  - Example: movie review → positive or negative score.
  - Simple models: bag-of-words + logistic regression; advanced: LSTM or transformers.

- Chatbots and LLM basics (Transformers & Attention)

  - Transformers: neural network architecture that uses _attention_ to weigh relationships between words.
  - Attention: lets the model focus on relevant words in a sentence when making predictions.
  - LLMs (Large Language Models): very large transformer-based models trained on lots of text; they generate fluent text and can answer questions.

  Short example phrase: "Attention helps the model ask: which input words are important to predict the next word?"

---

## 3. Search and Problem Solving

Short intro: many AI problems are searches through possibilities. We model options as states and move between them.

- State space representation (understanding problems logically)

  - State: a snapshot of the world (e.g., board positions in chess).
  - Operators: possible moves/transitions from one state to another.
  - Goal test: condition that decides if a state is a solution.

- BFS (Breadth-First Search)

  - Explore level by level; finds shortest path (fewest steps) if each move costs the same.
  - Example: finding shortest path in an unweighted maze.

- DFS (Depth-First Search)

  - Explore deep first; uses less memory, may get stuck on deep paths.
  - Useful for exploring or when solution is deep and space is limited.

- Heuristic and A\* Search

  - Heuristic: a function that estimates cost from current state to goal (must be fast to compute).
  - A\*: uses g(n) (cost so far) + h(n) (heuristic) and finds optimal path if h is admissible (never overestimates).
  - Example: navigation systems use heuristics like straight-line distance.

- Constraint Satisfaction Problems (CSP)

  - Problems where variables must satisfy constraints (e.g., Sudoku: numbers must follow rules).
  - Solve using backtracking, forward checking, and constraint propagation.

  Interview tip: mention trade-offs — search quality vs compute vs memory.

---

## 4. Knowledge Representation (Logic of Knowledge)

Short intro: how machines store facts and rules so they can reason.

- Facts, Rules, and Inference

  - Fact: a statement about the world (e.g., "Alice is a student").
  - Rule: if-then logic (e.g., IF student AND passed THEN graduate).
  - Inference: derive new facts from existing facts and rules.

- Propositional Logic (True/False statements)

  - Basic logic with variables that are true or false and operators AND, OR, NOT.
  - Example expression: (Rain AND Cold) → Bring Umbrella.

- Predicate Logic (Using variables and conditions)

  - Adds structure: predicates, variables, quantifiers (FOR ALL, EXISTS). More expressive than propositional logic.
  - Example: `forall x: Student(x) -> Mortal(x)` style.

- Semantic Networks & Frames

  - Semantic network: graph of concepts connected by relationships ("is-a", "part-of").
  - Frames: data structures for stereotyped situations with named slots (like objects with attributes).

  Interview tip: say why representation matters — affects what reasoning is possible and how easy it is to update knowledge.

---

## 5. Reasoning Techniques

Short intro: reasoning is how the system uses its knowledge to draw conclusions or make decisions.

- Forward & Backward Reasoning

  - Forward chaining: start with facts and apply rules to reach new facts (data-driven).
  - Backward chaining: start with a goal and look for rules that can produce it (goal-driven). Example: Prolog uses backward chaining.

- Logical inference rules (AND, OR, NOT)

  - Basic building blocks of logical reasoning. Use them to combine or negate facts.

- Rule-based reasoning (If-Then rules)

  - Expert systems use many rules; rules fire when their conditions match facts.

- Common-sense reasoning
  - Try to mimic everyday human reasoning (often incomplete, fuzzy, or probabilistic).
  - Hard problem: many human beliefs are unstated or context-specific.

---

## 6. Applications of AI (Logical Understanding)

Short intro: map logic and techniques to practical applications you can describe in interviews.

- Logical automation (Chatbots, Voice Assistants)

  - Use NLP + dialogue management rules to handle user requests.
  - Example: map user intent → fetch data → respond.

- Logical prediction systems (Recommendation engines)

  - Combine user history, item features, and collaborative signals to predict preferences.
  - Example algorithms: matrix factorization, nearest neighbors, deep models.

- Image recognition (how AI logically classifies)

  - Use convolutional neural networks (CNNs) and feature hierarchies to detect objects.
  - Logical view: low-level edges → patterns → object concepts.

- NLP logic (AI understanding text)
  - Combine syntax (structure) and semantics (meaning) using embeddings, attention, and symbolic rules when needed.

---

## 7. Ethics and Logic in AI

Short intro: interviews will ask about fairness, bias, and explainability — be ready with simple definitions and examples.

- Logical fairness — bias and transparency

  - Bias: models can learn biased patterns from training data (e.g., unfair loan decisions).
  - Transparency: being able to explain model decisions helps build trust.
  - Simple mitigation: balanced data, fairness-aware metrics, model auditing.

- Logical decision-making vs human judgment

  - Machines follow rules/data; humans add context, values, and ethics. Good systems combine both.

- Importance of explainability in AI models
  - Explainability helps debug, comply with regulations, and gain user trust. Example: use feature importance or simple models for critical decisions.

---

## Final interview tips (quick)

- Use short definitions first, then one short real-world example.
- When asked differences, use comparative words: "AI is X, while ML is Y; ML focuses on learning from data; Deep Learning is specialized ML with neural nets."
- For technical topics, explain the idea in one sentence, then a short example, then a sentence on trade-offs.
- Practice scenarios: "Explain how you'd build a chatbot" — outline data, model, evaluation, deployment.