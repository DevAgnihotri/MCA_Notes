# Syllabus

**Unit 1 Syllabus: Artificial Intelligence**

- Introduction to Artificial Intelligence (AI):
  - Definition, history, and evolution of AI
  - Foundation areas and branches of AI
  - Key tasks and application domains
- Intelligent Agents:
  - Types and structure of agents
  - Elements and functions of agents
  - PEAS (Performance measure, Environment, Actuators, Sensors) description
  - Rationality and agent design
- Natural Language Processing (NLP):
  - Overview and approaches
  - Steps involved in NLP
- Computer Vision:
  - Basic concepts and applications

---

# Previous Year Questions (PYQs)

## Grouped Questions by Topic

### Artificial Intelligence: Definition & Comparison

- What do you mean by AI? (2023–24, 2017–18, A)
- What do you mean by the term AI? How is it different from Natural intelligence? (2017–18, A)
- Differentiate between human intelligence and machine intelligence. (2023–24, B)

### Intelligent Agents & Types

- What is an intelligent agent? (2022–23, 2017–18, A, B)
- Name the elements of an agent. (2018–19, A)
- Discuss historical development of agent. (2017–18, C)
- Discuss its two types. (2017–18, B)
- Describe intelligent agents in terms of Percepts, Actions, Goals and Environment with suitable block diagram and example. (2021–22, C)
- Differentiate between goal-based agent and utility-based intelligent agents with the help of block diagram. (2021–22, C)
- Discuss possible agent designs for the cases in which clean squares can become dirty and the geography of the environment is unknown. Does it make sense for the agent to learn? (2018–19, C)

### Agent Functions & Rationality

- Summarize the factors that make up rationality. (2018–19, A)
- Describe a rational agent function for a modified performance measure. Does the corresponding agent program require internal state? (2018–19, C)

### PEAS Description

- What is PEAS description of the task environment for ‘Internet shopping agent’. (2021–22, B)
- Discuss and give examples of agent related PEAS description of the task environment. (2017–18, C)

### AI Tasks & Applications

- State any two foundation areas of artificial intelligence. (2022–23, A)
- Discuss various categories of AI tasks. (2022–23, B)
- Describe the applications of artificial intelligence. (2023–24, B)

### Natural Language Processing (NLP)

- Explain various approaches in NLP. (2023–24, C)
- What is natural language processing? (2021–22, A)
- Explain various steps involved in natural language processing. (2022–23, C)

### Model-Based Agents

- Discuss functioning of model-based intelligent agent with the help of a diagram. (2022–23, C)

### Weak AI vs Strong AI

- Define the terms – weak AI and strong AI. (2021–22, A)

---

## Detailed Explanation: Introduction to Artificial Intelligence (AI)

### Definition of Artificial Intelligence

**What do you mean by AI? (2023–24, 2017–18, A)**

Artificial Intelligence (AI) is a field of computer science focused on building programs and machines that can perform tasks such as learning, reasoning, recognizing patterns, understanding language, and making decisions—tasks that usually need human intelligence. AI systems use algorithms and data to solve problems, automate processes, and interact with their environment.

### History and Evolution of AI

The concept of AI dates back to ancient myths and stories of artificial beings. However, modern AI began in the 1950s:

- **1950s:** Alan Turing proposed the question "Can machines think?" and introduced the Turing Test.
- **1956:** The term "Artificial Intelligence" was coined at the Dartmouth Conference, marking the birth of AI as a field.
- **1960s–70s:** Early AI programs could solve algebra problems and play games like chess.
- **1980s:** Introduction of expert systems that mimicked human decision-making.
- **1990s–2000s:** AI systems became better at learning from data (machine learning) and handling complex tasks.
- **2010s–present:** Deep learning and neural networks led to breakthroughs in image recognition, natural language processing, and autonomous vehicles.

### Foundation Areas and Branches of AI

**State any two foundation areas of artificial intelligence. (2022–23, A)**

AI is built on several foundation areas:
- **Mathematics:** This is about using numbers, logic, and probability to help computers solve problems and make decisions. For example, AI uses math to figure out the best move in a game or to predict what might happen next.  
  - *Why important?* Math helps AI understand patterns, handle uncertainty, and make smart choices.
  - *Examples:* Using statistics to find trends in data, using logic to solve puzzles.

- **Computer Science:** This is about writing instructions (programs) for computers and organizing information. AI uses computer science to create algorithms (step-by-step solutions) and manage data.  
  - *Why important?* Computer science gives AI the tools to process information quickly and solve complex problems.
  - *Examples:* Sorting data, searching for answers, building smart apps.

- **Psychology:** This helps AI understand how people think and learn, so computers can act more like humans.

- **Linguistics:** This helps AI understand and use human language, so computers can talk and listen to us.

- **Philosophy:** This helps AI think about what is right or wrong, and how to make fair decisions.

- **Machine Learning:** Systems that learn from data and improve their performance over time without being explicitly programmed. They use algorithms to find patterns and make predictions or decisions.  
  - *Examples:* Email spam filters, recommendation engines (Netflix, Amazon), handwriting recognition.

- **Natural Language Processing (NLP):** Enables computers to understand, interpret, and generate human language. It is used in applications like chatbots, translation, and speech recognition.  
  - *Examples:* Chatbots (ChatGPT), Google Translate, voice assistants (Siri, Alexa).

- **Computer Vision:** Allows machines to interpret and analyze visual information from the world, such as images and videos. It is used in facial recognition, medical imaging, and autonomous vehicles.  
  - *Examples:* Face detection in photos, self-driving car cameras, X-ray image analysis.

- **Robotics:** Involves designing and building intelligent machines that can perform tasks autonomously or with minimal human intervention. Robots use sensors and AI to interact with their environment.  
  - *Examples:* Industrial robots, robotic vacuum cleaners, surgical robots.

- **Expert Systems:** Computer programs that mimic the decision-making abilities of human experts. They use rules and knowledge bases to solve complex problems in specific domains.  
  - *Examples:* Medical diagnosis systems, financial advisory tools, troubleshooting guides.

AI is used in many tasks and domains:

### Categories and Applications of Artificial Intelligence

**Describe the applications of artificial intelligence. (2023–24, B)**

**Discuss various categories of AI tasks. (2022–23, B)**

#### 1. Speech Recognition
**Definition:** AI systems that can understand and process spoken language. Speech recognition enables computers to convert spoken words into text and respond to voice commands.
**Technical Tech Used:** Deep learning models (e.g., recurrent neural networks, transformers), natural language processing (NLP).
**Examples:** Virtual assistants like Siri, Alexa, and Google Assistant use speech recognition to answer questions and perform tasks.

#### 2. Image Recognition
**Definition:** AI systems that can identify and classify objects within images or videos. Image recognition helps computers "see" and interpret visual information, such as detecting faces or diagnosing medical images.
**Technical Tech Used:** Convolutional neural networks (CNNs), computer vision algorithms.
**Examples:** Medical imaging for disease detection, security systems for facial recognition, photo tagging in social media.

#### 3. Language Translation
**Definition:** AI systems that automatically translate text or speech from one language to another. Language translation allows people to communicate across different languages using computers.
**Technical Tech Used:** Neural machine translation (NMT), transformer models (e.g., Google’s BERT, OpenAI’s GPT).
**Examples:** Google Translate, Microsoft Translator, real-time translation in messaging apps.

#### 4. Autonomous Vehicles
**Definition:** AI-powered vehicles that can navigate and operate without human intervention. Autonomous vehicles use sensors, cameras, and AI to perceive their environment and make driving decisions.
**Technical Tech Used:** Computer vision, sensor fusion, reinforcement learning, deep neural networks.
**Examples:** Self-driving cars (Tesla Autopilot, Waymo), delivery robots, drones.

#### 5. Recommendation Systems
**Definition:** AI systems that suggest products, content, or services based on user preferences. Recommendation systems analyze user behavior and data to provide personalized suggestions.
**Technical Tech Used:** Collaborative filtering, content-based filtering, deep learning, matrix factorization.
**Examples:** Netflix movie recommendations, Amazon product suggestions, Spotify playlists.

#### 6. Healthcare
**Definition:** AI applications that assist in medical diagnosis, treatment planning, and drug discovery. AI helps doctors analyze medical data, predict diseases, and discover new medicines faster.
**Technical Tech Used:** Machine learning, deep learning, computer vision, natural language processing.
**Examples:** AI-based diagnostic tools (IBM Watson Health), drug discovery platforms, automated analysis of X-rays and MRIs.

#### 7. Finance
**Definition:** AI systems used for financial analysis, fraud detection, and automated trading. AI improves accuracy and speed in financial decision-making, detects suspicious activities, and optimizes trading strategies.
**Technical Tech Used:** Machine learning algorithms, anomaly detection, predictive analytics.
**Examples:** Fraud detection in banking, algorithmic trading platforms, credit scoring systems.
