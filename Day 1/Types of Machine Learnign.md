Machine Learning can be broadly categorized based on **how the model receives and learns from data**.

The major types are:

1. Supervised Learning
2. Unsupervised Learning
3. Semi-Supervised Learning
4. Self-Supervised Learning
5. Reinforcement Learning

---

# 1. Supervised Learning

## Definition

**Supervised Learning** is a type of Machine Learning where the model learns from **labeled data**.

Each training example contains:

- Input features ($X$)
- Correct output/target ($Y$)

The model learns a mapping:

$$
f(X) \approx Y
$$

The goal is to learn a function that can predict the correct output for **new, unseen data**.

## Basic Structure

**Input + Correct Output → Learning Algorithm → Model**

Then:

**New Input → Trained Model → Prediction**

## Example

Suppose we want to predict house prices.

| Area | Bedrooms | Price |
|---:|---:|---:|
| 1000 sq ft | 2 | ₹40 Lakh |
| 1500 sq ft | 3 | ₹60 Lakh |
| 2000 sq ft | 4 | ₹80 Lakh |

Here:

**Features ($X$):**
- Area
- Number of bedrooms

**Target ($Y$):**
- House Price

The model learns the relationship:

$$
\text{House Features} \rightarrow \text{House Price}
$$

Then it can predict the price of a new house.

---

## Main Types of Supervised Learning

### 1. Regression

Used when the target is a **continuous numerical value**.

Examples:

- House price prediction
- Salary prediction
- Temperature prediction
- Sales forecasting

Example:

$$
\hat{y} = wx+b
$$

Output:

**₹65.5 Lakh**

---

### 2. Classification

Used when the target belongs to a **class/category**.

Examples:

- Spam / Not Spam
- Pass / Fail
- Disease / No Disease
- Fraud / Not Fraud
- Cat / Dog

Example:

**Email → Spam**

The output may be:

$$
P(\text{Spam}) = 0.94
$$

---

## Common Supervised Learning Algorithms

### Regression

- Linear Regression
- Polynomial Regression
- Decision Tree Regression
- Random Forest Regression
- Gradient Boosting
- XGBoost
- Support Vector Regression
- Neural Networks

### Classification

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
- Random Forest
- Support Vector Machine (SVM)
- Naive Bayes
- Gradient Boosting
- XGBoost
- Neural Networks

---

## Key Idea

> **Supervised Learning learns from examples where the correct answer is already known.**

---

# 2. Unsupervised Learning

## Definition

**Unsupervised Learning** is a type of Machine Learning where the model learns from **unlabeled data**.

There is no predefined target variable provided to the model.

The model tries to discover:

- Patterns
- Groups
- Structures
- Relationships
- Anomalies

in the data.

## Basic Structure

**Input Data → Learning Algorithm → Discovered Structure**

There is no known $Y$ during training.

Instead of:

$$
X \rightarrow Y
$$

we primarily analyze:

$$
X \rightarrow \text{Structure/Pattern}
$$

---

## Example: Customer Segmentation

Suppose a company has customer data:

| Customer | Age | Income | Spending |
|---|---:|---:|---:|
| A | 22 | 30k | 25k |
| B | 24 | 32k | 27k |
| C | 45 | 90k | 20k |
| D | 48 | 95k | 18k |

There are no labels such as:

- Student
- Premium Customer
- Low Spender

The algorithm may automatically discover groups.

For example:

**Group 1**
→ Young, lower income, high spending

**Group 2**
→ Older, high income, lower spending

This is called **clustering**.

---

## Major Tasks in Unsupervised Learning

### 1. Clustering

Groups similar data points together.

Examples:

- Customer segmentation
- Document grouping
- Image grouping

Algorithms:

- K-Means
- Hierarchical Clustering
- DBSCAN
- Gaussian Mixture Models

---

### 2. Dimensionality Reduction

Reduces the number of features while trying to preserve important information.

Example:

100 features

↓

10 important dimensions

Common algorithms:

- PCA
- t-SNE
- UMAP

Applications:

- Visualization
- Noise reduction
- Feature compression
- Preprocessing

---

### 3. Anomaly Detection

Identifies unusual or suspicious observations.

Examples:

- Fraud detection
- Network intrusion detection
- Machine failure detection
- Unusual transactions

---

### 4. Association Rule Learning

Discovers relationships between items or events.

Example:

Customers who buy:

**Bread + Butter**

may frequently also buy:

**Jam**

Common algorithm:

- Apriori
- FP-Growth

---

## Key Idea

> **Unsupervised Learning discovers hidden structure in data without predefined labels.**

---

# 3. Semi-Supervised Learning

## Definition

**Semi-Supervised Learning** uses a combination of:

- A small amount of labeled data
- A large amount of unlabeled data

This is useful when obtaining labels is expensive or time-consuming.

## Basic Structure

**Small Labeled Dataset + Large Unlabeled Dataset**

↓

**Learning Algorithm**

↓

**Model**

---

## Example

Suppose we have:

**10,000 images**

But only:

**500 images are labeled**

For example:

- 300 → Cat
- 200 → Dog

The remaining:

**9,500 images are unlabeled.**

Instead of ignoring those 9,500 images, semi-supervised learning tries to use them to improve the model.

---

## Why Use Semi-Supervised Learning?

Creating labels can be expensive.

For example, medical images may require experts to label them.

Instead of manually labeling:

**100,000 images**

we may label:

**5,000 images**

and use the remaining:

**95,000 unlabeled images**

to help train the model.

---

## Common Approaches

### 1. Pseudo-Labeling

The model predicts labels for unlabeled data.

Example:

Unlabeled image

↓

Model predicts:

**Cat — 98% confidence**

↓

Use this prediction as a temporary label.

---

### 2. Consistency Regularization

The model is encouraged to produce similar predictions when the same input is slightly modified.

Example:

Original image → Cat

Augmented image → Cat

The model should remain consistent.

---

## Applications

- Medical imaging
- Speech recognition
- Image classification
- Text classification
- Web content classification

---

## Key Idea

> **Semi-Supervised Learning combines a small amount of labeled data with a large amount of unlabeled data.**

---

# 4. Self-Supervised Learning

## Definition

**Self-Supervised Learning** is a learning approach where the model creates a **learning signal from the data itself**.

There is usually no need for humans to manually label every example.

The model creates a task where part of the data is used to predict another part.

## Core Idea

**Raw Data**

↓

**Automatically Create Training Task**

↓

**Predict Missing/Hidden Information**

↓

**Learn Representations**

---

## Example: Language Models

Consider the sentence:

> "The capital of France is ____."

The model is asked to predict:

**Paris**

The text itself provides the training signal.

No human needs to manually label:

**France → Paris**

for every example.

---

## Another Example: Masked Word Prediction

Original sentence:

> "Machine learning is very powerful."

Hide a word:

> "Machine learning is very ____."

The model predicts:

**powerful**

The original text acts as its own source of supervision.

---

## Image Example

Suppose an image is partially hidden.

**Visible Image → Predict Missing Region**

The model learns useful visual representations while solving the task.

---

## Self-Supervised Learning in Modern AI

Self-supervised learning is extremely important in:

- Large Language Models (LLMs)
- Computer Vision
- Speech Models
- Multimodal AI

Examples of models trained using self-supervised objectives include:

- BERT
- GPT-style language models
- Vision Transformers
- Contrastive learning models

---

## Important Distinction

Self-supervised learning is sometimes discussed separately from supervised and unsupervised learning, but conceptually it is closely related to **learning from unlabeled data**.

The important distinction is:

**Unsupervised Learning**

→ Discover structure without explicit labels.

**Self-Supervised Learning**

→ Creates supervision automatically from the data itself.

---

## Key Idea

> **Self-Supervised Learning creates its own training signal from the input data.**

---

# 5. Reinforcement Learning

## Definition

**Reinforcement Learning (RL)** is a type of Machine Learning where an **agent learns by interacting with an environment**.

The agent performs actions and receives:

- Rewards
- Penalties

The goal is to learn a strategy that maximizes **long-term cumulative reward**.

---

## Core Components

### 1. Agent

The learner or decision-making system.

Examples:

- Robot
- Game-playing AI
- Autonomous vehicle

### 2. Environment

The world in which the agent operates.

Examples:

- Chess board
- Video game
- Physical environment

### 3. State

The current situation of the environment.

Example:

In chess:

**Current board position**

### 4. Action

What the agent can do.

Example:

**Move a chess piece**

### 5. Reward

Feedback received after taking an action.

Example:

**+10 → Good action**

**-10 → Bad action**

### 6. Policy

A strategy that determines which action the agent should take in a given state.

$$
\pi(a|s)
$$

where:

- $s$ = state
- $a$ = action
- $\pi$ = policy

---

## Reinforcement Learning Loop

**State**

↓

**Agent chooses Action**

↓

**Environment**

↓

**Reward + New State**

↓

**Agent learns**

↓

**Better Action Selection**

↓

**Repeat**

---

## Example: Robot Learning to Walk

Initially:

Robot takes an action

↓

Falls

↓

Negative reward

↓

Learns that the action was not useful

Another attempt:

Robot maintains balance

↓

Positive reward

↓

Learns that the action was useful

Over many interactions:

**Trial → Feedback → Learning → Better Decisions**

---

## Example: Game Playing

An AI plays a game.

**Win → +100 reward**

**Lose → -100 reward**

**Good move → +10**

**Bad move → -10**

The agent learns a policy that maximizes future rewards.

---

## Important Concept: Exploration vs Exploitation

The agent must balance:

### Exploration

Try new actions to discover whether they produce better results.

### Exploitation

Use actions that are already known to work well.

Example:

A game-playing agent has two choices:

**Action A**
→ Known to give good reward

**Action B**
→ Unknown but may be even better

The agent must balance:

**Trying new things** vs **using known good strategies**

---

## Applications

- Robotics
- Game playing
- Autonomous systems
- Recommendation systems
- Resource optimization
- Industrial control
- Traffic signal optimization

---

# Comparison of ML Types

| Type | Labeled Data | Main Idea | Example |
|---|---|---|---|
| Supervised | Yes | Learn from input-output pairs | House price prediction |
| Unsupervised | No | Discover hidden structure | Customer clustering |
| Semi-Supervised | Small amount | Combine labeled + unlabeled data | Image classification |
| Self-Supervised | No manual labels required | Create supervision from data itself | Language models |
| Reinforcement | Reward-based feedback | Learn through interaction | Game-playing AI |

---

# Simple Mental Model

## Supervised Learning

**Question:**

> "Here are the examples and their correct answers. Learn to predict the answer."

$$
X \rightarrow Y
$$

---

## Unsupervised Learning

**Question:**

> "Here is the data. Find interesting patterns or structure."

$$
X \rightarrow \text{Structure}
$$

---

## Semi-Supervised Learning

**Question:**

> "Here are a few labeled examples and many unlabeled examples. Use both."

$$
\text{Small Labeled Data} + \text{Large Unlabeled Data}
$$

---

## Self-Supervised Learning

**Question:**

> "Use the data itself to create a prediction task and learn useful representations."

$$
X \rightarrow \text{Automatically Generated Target}
$$

---

## Reinforcement Learning

**Question:**

> "Take actions, observe the consequences, and learn which actions maximize reward."

$$
\text{State} \rightarrow \text{Action} \rightarrow \text{Reward}
$$

---

# One-Line Definitions

### Supervised Learning

**Learns from labeled examples.**

### Unsupervised Learning

**Discovers patterns or structure from unlabeled data.**

### Semi-Supervised Learning

**Learns using a small amount of labeled data and a large amount of unlabeled data.**

### Self-Supervised Learning

**Generates its own supervision from the data.**

### Reinforcement Learning

**Learns through actions, feedback, and rewards.**

---

# Important Conceptual Difference

The most important question to ask is:

> **Where does the learning signal come from?**

### Supervised

Learning signal comes from **human-provided labels**.

### Unsupervised

No explicit target; the algorithm searches for **structure in the data**.

### Semi-Supervised

Learning signal comes from **both labeled and unlabeled data**.

### Self-Supervised

Learning signal is **automatically generated from the data itself**.

### Reinforcement Learning

Learning signal comes from **rewards and consequences of actions**.

---

# Quick Revision

**Supervised**
→ Labeled data  
→ Prediction  
→ Regression + Classification

**Unsupervised**
→ Unlabeled data  
→ Discover structure  
→ Clustering + Dimensionality Reduction + Anomaly Detection

**Semi-Supervised**
→ Few labeled + many unlabeled  
→ Useful when labeling is expensive

**Self-Supervised**
→ Data creates its own supervision  
→ Extremely important in modern AI and foundation models

**Reinforcement Learning**
→ Agent + Environment + Actions + Rewards  
→ Learn optimal behavior through interaction

---

# Final Mental Map

Machine Learning
│
├── Supervised Learning
│   ├── Regression
│   └── Classification
│
├── Unsupervised Learning
│   ├── Clustering
│   ├── Dimensionality Reduction
│   └── Anomaly Detection
│
├── Semi-Supervised Learning
│   └── Labeled + Unlabeled Data
│
├── Self-Supervised Learning
│   └── Data → Automatically Generated Learning Signal
│
└── Reinforcement Learning
    └── Agent → Action → Reward → Learning

---

# Core Takeaway

> **The different types of Machine Learning mainly differ in how the model receives feedback or a learning signal.**

$$
\boxed{
\begin{aligned}
\text{Supervised} &\rightarrow \text{Labels} \\
\text{Unsupervised} &\rightarrow \text{Structure} \\
\text{Semi-Supervised} &\rightarrow \text{Labels + Unlabeled Data} \\
\text{Self-Supervised} &\rightarrow \text{Data-Generated Signal} \\
\text{Reinforcement} &\rightarrow \text{Rewards}
\end{aligned}
}
$$