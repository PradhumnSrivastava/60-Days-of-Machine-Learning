# Machine Learning Foundations

## 1. AI vs ML vs Deep Learning

### Artificial Intelligence (AI)

Artificial Intelligence (AI) is the broad field of building machines that can perform tasks that normally require human intelligence.

**Examples:**
- Reasoning
- Problem solving
- Decision making
- Understanding language
- Image recognition
- Planning
- Learning

### Machine Learning (ML)

Machine Learning is a subfield of AI in which computers learn patterns from data and use those patterns to make predictions or decisions.

Instead of explicitly programming every rule, we provide data and a learning algorithm, and the algorithm learns useful patterns from the data.

### Deep Learning (DL)

Deep Learning is a subfield of Machine Learning that uses neural networks with multiple layers to learn complex patterns from data.

### Relationship

Artificial Intelligence (AI)  
└── Machine Learning (ML)  
&emsp;└── Deep Learning (DL)

### Simple Memory Trick

> AI is the broad field, ML is a way of achieving AI, and DL is a powerful ML approach based on neural networks.

---

## 2. Traditional Programming vs Machine Learning

### Traditional Programming

In traditional programming, the programmer explicitly writes the rules.

**Data + Rules → Program → Output**

Example:

`if marks >= 40: result = "Pass"`

The programmer explicitly defines the logic.

### Machine Learning

In Machine Learning, the algorithm learns useful patterns from examples.

**Data + Expected Outputs → ML Algorithm → Model**

Then:

**New Data + Trained Model → Prediction**

### Example

Suppose we have:

| Hours Studied | Result |
|---:|---|
| 1 | Fail |
| 2 | Fail |
| 3 | Fail |
| 5 | Pass |
| 7 | Pass |
| 9 | Pass |

Instead of explicitly writing:

**IF hours > 4 → Pass**

we provide examples to the ML algorithm.

The algorithm learns a useful relationship from the data.

### Key Difference

**Traditional Programming:**

**Data + Rules → Output**

**Machine Learning:**

**Data + Examples → Model**

Then:

**New Data + Model → Prediction**

---

## 3. What Exactly Does a Model Learn?

A model does not simply memorize answers.

Ideally, a model learns a useful **mathematical relationship or pattern** between inputs and outputs.

### Example: Linear Regression

Suppose:

- X = Hours Studied
- Y = Exam Score

A simple model can be represented as:

$$
y = wx + b
$$

Where:

- $x$ = input
- $y$ = prediction
- $w$ = weight
- $b$ = bias

During training, the model learns suitable values for $w$ and $b$.

For example:

$$
y = 8x + 30
$$

Here:

- $w = 8$
- $b = 30$

For 5 hours of study:

$$
y = 8(5) + 30
$$

$$
y = 70
$$

The model has learned a relationship between:

**Hours Studied → Exam Score**

---

## 4. What Does "Learning" Mean Mathematically?

At its core:

> Learning means finding parameter values that make the model's predictions sufficiently accurate according to a chosen objective.

For example:

$$
\hat{y} = wx + b
$$

The model produces a prediction:

$$
\hat{y}
$$

We compare it with the actual value:

$$
y
$$

The difference is measured using a **loss function**.

For Mean Squared Error:

$$
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2
$$

The training algorithm tries to find parameter values that reduce the loss.

### Learning Loop

Initial Parameters  
↓  
Prediction  
↓  
Calculate Loss  
↓  
Adjust Parameters  
↓  
Prediction  
↓  
Calculate Loss  
↓  
Repeat  
↓  
Better Parameters

---

## 5. What Can a Model Learn?

Depending on the algorithm, a model can learn different things.

### 1. Weights

Example:

$$
y = w_1x_1 + w_2x_2 + b
$$

The model learns:

$$
w_1,\; w_2,\; b
$$

### 2. Relationships

Example:

**Advertising Spend → Sales**

The model learns a mathematical relationship between the variables.

### 3. Decision Boundaries

In classification, the model can learn a boundary that separates different classes.

**Class A**

● ● ● ● ●

**Decision Boundary**

-------------------------

**Class B**

■ ■ ■ ■ ■

### 4. Representations

Deep Learning models can learn increasingly complex representations.

Raw Input  
↓  
Low-Level Patterns  
↓  
Higher-Level Patterns  
↓  
Complex Representation  
↓  
Prediction

For an image:

Pixels  
↓  
Edges  
↓  
Textures  
↓  
Shapes  
↓  
Object Parts  
↓  
Object

---

## 6. What a Model Does NOT Automatically Learn

A model does not automatically learn:

- Human understanding
- Common sense
- Truth
- Causality
- Human intentions
- Human meaning

A model learns patterns according to its:

- Training data
- Model architecture
- Objective/loss function
- Optimization process

---

## 7. Parameters vs Hyperparameters

### Parameters

Parameters are values **learned during training**.

Example:

$$
y = wx + b
$$

Here:

- $w$ → Parameter
- $b$ → Parameter

The training algorithm adjusts these values.

### Hyperparameters

Hyperparameters are values configured by the practitioner before or during the training process.

Examples:

- Learning rate
- Number of trees
- Maximum tree depth
- Number of hidden layers
- Batch size
- Number of epochs

### Important Rule

> **Parameters are learned; hyperparameters are configured.**

---

## 8. Core Machine Learning Learning Loop

**DATA**  
↓  
**ML Algorithm**  
↓  
**MODEL**  
↓  
**Prediction**  
↓  
**Compare with Actual**  
↓  
**Loss**  
↓  
**Update Parameters**  
↓  
**Repeat**

---

## 9. General Machine Learning Pipeline

Problem Definition  
↓  
Data Collection  
↓  
Data Cleaning  
↓  
Exploratory Data Analysis  
↓  
Feature Engineering  
↓  
Data Preprocessing  
↓  
Train Model  
↓  
Evaluate Model  
↓  
Hyperparameter Tuning  
↓  
Final Model  
↓  
Deployment  
↓  
Prediction  
↓  
Monitoring

---

## 10. Important ML Terminology

### Data

Information provided to the ML system.

**Example:**

- Age = 25
- Salary = ₹50,000
- Experience = 2 years

### Feature

An input variable used by the model.

**Examples:**

- Age
- Salary
- Experience

### Target / Label

The variable we want to predict.

**Examples:**

- Salary
- House Price
- Loan Approved / Rejected
- Disease / No Disease

### Model

A mathematical structure that has learned patterns or relationships from data.

### Training

The process of adjusting model parameters using data to improve predictions.

### Prediction

The output produced by a trained model for new input.

---

## 11. Most Important Mental Model

DATA  
↓  
Learning Algorithm  
↓  
MODEL  
↓  
New / Unseen Data  
↓  
PREDICTION

Mathematically:

$$
\text{Input} \xrightarrow{\text{Model}} \text{Prediction}
$$

A model can be viewed as a learned function:

$$
f(x) \approx y
$$

For multiple features:

$$
f(x_1,x_2,\ldots,x_n) \approx y
$$

---

## 12. Three Questions to Ask for Every ML Algorithm

### Question 1 — What is the Input?

What information is given to the model?

**X = ?**

### Question 2 — What Does the Model Learn?

What parameters, patterns, relationships, or representations are learned?

**Parameters = ?**

### Question 3 — How Does the Model Know It Is Improving?

What loss, error, objective, or evaluation metric is being optimized?

**Objective = ?**

If you can answer these three questions, you understand the core mechanism of the algorithm rather than simply memorizing its syntax.

---

# Quick Revision

**AI**  
→ Broad field of intelligent machines

**ML**  
→ AI systems that learn patterns from data

**Deep Learning**  
→ ML using multi-layer neural networks

**Traditional Programming**  
→ Rules + Data → Output

**Machine Learning**  
→ Data + Examples → Model

**Model**  
→ Learned mathematical relationship/pattern

**Training**  
→ Finding useful parameter values

**Parameter**  
→ Learned during training

**Hyperparameter**  
→ Configured by the practitioner

**Loss Function**  
→ Measures how wrong the model's prediction is

**Learning**  
→ Adjusting parameters to improve the objective

---

## Core Formulas

$$
\boxed{\text{Data} + \text{Learning Algorithm} \rightarrow \text{Model}}
$$

$$
\boxed{\text{New Data} + \text{Model} \rightarrow \text{Prediction}}
$$

$$
\boxed{f(x) \approx y}
$$