Before studying individual Machine Learning algorithms, it is important to understand some fundamental terms used throughout ML.

The most important concepts are:

1. Features
2. Target
3. Samples
4. Parameters
5. Hyperparameters
6. Training vs Inference
7. General ML Pipeline

---

# 1. Features

## Definition

**Features** are the input variables or measurable properties that are used by a Machine Learning model to make predictions.

Features are usually represented by:

$$
X
$$

For multiple features:

$$
X = [x_1, x_2, x_3, \ldots, x_n]
$$

where each $x_i$ represents one feature.

---

## Example

Suppose we want to predict house prices.

| Area | Bedrooms | Age | Price |
|---:|---:|---:|---:|
| 1000 | 2 | 10 | ₹40 Lakh |
| 1500 | 3 | 5 | ₹60 Lakh |
| 2000 | 4 | 3 | ₹80 Lakh |

Features are:

- Area
- Bedrooms
- Age

So:

$$
X = [Area,\ Bedrooms,\ Age]
$$

The model uses these features to predict the house price.

---

## Feature Matrix

Suppose we have 3 samples and 2 features:

| Sample | Area | Bedrooms |
|---|---:|---:|
| 1 | 1000 | 2 |
| 2 | 1500 | 3 |
| 3 | 2000 | 4 |

The feature matrix can be represented as:

$$
X =
\begin{bmatrix}
1000 & 2 \\
1500 & 3 \\
2000 & 4
\end{bmatrix}
$$

Shape:

$$
X \in \mathbb{R}^{3 \times 2}
$$

where:

- 3 = number of samples
- 2 = number of features

---

## Types of Features

### Numerical Features

Features represented by numbers.

Examples:

- Age
- Salary
- Height
- Temperature
- Income

### Categorical Features

Features representing categories.

Examples:

- Gender
- City
- Product Type
- Department

Example:

$$
City \in \{Delhi,\ Mumbai,\ Chennai,\ Kolkata\}
$$

### Binary Features

Features with two possible values.

Examples:

- Yes / No
- True / False
- 0 / 1

### Ordinal Features

Categorical values with a meaningful order.

Example:

$$
Low < Medium < High
$$

---

## Important Point

> A feature is an input variable that provides information to the model for making a prediction.

---

# 2. Target

## Definition

The **Target** is the variable that the Machine Learning model is trained to predict.

It is also called:

- Label
- Output
- Dependent Variable
- Response Variable

The target is commonly represented by:

$$
Y
$$

---

## Example

Suppose we want to predict house prices.

| Area | Bedrooms | Age | Price |
|---:|---:|---:|---:|
| 1000 | 2 | 10 | ₹40 Lakh |
| 1500 | 3 | 5 | ₹60 Lakh |
| 2000 | 4 | 3 | ₹80 Lakh |

Features:

$$
X = [Area,\ Bedrooms,\ Age]
$$

Target:

$$
Y = Price
$$

The model learns:

$$
X \rightarrow Y
$$

---

## Classification Example

Suppose we want to predict whether an email is spam.

| Word Count | Links | Sender Reputation | Spam |
|---:|---:|---:|---|
| 100 | 5 | Low | Yes |
| 50 | 0 | High | No |
| 80 | 3 | Low | Yes |

Features:

- Word Count
- Number of Links
- Sender Reputation

Target:

**Spam**

The target may be:

$$
Y \in \{0,1\}
$$

---

## Regression vs Classification Target

### Regression

Target is generally a continuous numerical value.

Example:

$$
Y = House\ Price
$$

### Classification

Target represents a class/category.

Example:

$$
Y \in \{Spam,\ Not\ Spam\}
$$

---

## Important Point

> The target is what the model is trying to predict.

---

# 3. Samples

## Definition

A **sample** is one individual observation, record, or example in a dataset.

A sample usually contains:

- Feature values
- Target value (when available)

---

## Example

Consider:

| Age | Salary | Experience | Purchased |
|---:|---:|---:|---|
| 25 | 40k | 2 | Yes |
| 30 | 60k | 5 | Yes |
| 22 | 25k | 1 | No |

Each row represents one sample.

### Sample 1

$$
X_1 = [25,\ 40k,\ 2]
$$

$$
Y_1 = Yes
$$

### Sample 2

$$
X_2 = [30,\ 60k,\ 5]
$$

$$
Y_2 = Yes
$$

### Sample 3

$$
X_3 = [22,\ 25k,\ 1]
$$

$$
Y_3 = No
$$

---

## Dataset Dimensions

Suppose:

- 1000 samples
- 5 features

Then:

$$
X \in \mathbb{R}^{1000 \times 5}
$$

Therefore:

$$
\text{Rows} = \text{Samples}
$$

$$
\text{Columns} = \text{Features}
$$

---

## Sample vs Feature

Consider:

| Age | Salary | Experience |
|---:|---:|---:|
| 25 | 40k | 2 |
| 30 | 60k | 5 |
| 22 | 25k | 1 |

There are:

**3 samples**

and:

**3 features**

So:

$$
X.shape = (3,3)
$$

---

## Important Point

> A sample is one individual data point or observation used by the model.

---

# 4. Parameters

## Definition

**Parameters** are values that a Machine Learning model **learns automatically from training data**.

They are adjusted during training to improve the model's predictions.

---

## Example: Linear Regression

Consider:

$$
\hat{y} = wx+b
$$

Here:

- $w$ = weight
- $b$ = bias
- $\hat{y}$ = prediction

The model learns:

$$
w
$$

and

$$
b
$$

Therefore:

**$w$ and $b$ are parameters.**

---

## Example

Suppose the model learns:

$$
\hat{y} = 8x + 30
$$

Then:

$$
w = 8
$$

and:

$$
b = 30
$$

These values were learned from the training data.

---

## Parameters in Different Models

### Linear Regression

Parameters:

- Weights
- Bias

### Logistic Regression

Parameters:

- Weights
- Bias

### Neural Networks

Parameters include:

- Weights
- Biases

A large neural network may contain millions or billions of parameters.

### Decision Trees

Parameters can include:

- Split points
- Tree structure

---

## Key Idea

> Parameters are learned from the data during training.

---

# 5. Hyperparameters

## Definition

**Hyperparameters** are configuration values that are set by the practitioner before or during training.

Unlike parameters, they are **not directly learned from the training data in the normal training process**.

---

## Examples

### Linear Regression

Depending on the implementation:

- Regularization strength
- Optimization settings

### Decision Tree

- Maximum depth
- Minimum samples for splitting
- Minimum samples per leaf

### Random Forest

- Number of trees
- Maximum depth
- Maximum features

### Neural Network

- Learning rate
- Batch size
- Number of epochs
- Number of hidden layers
- Number of neurons

---

## Parameter vs Hyperparameter

| Parameters | Hyperparameters |
|---|---|
| Learned from data | Configured by practitioner |
| Updated during training | Set before/during training |
| Part of the model | Control the training/model configuration |
| Example: weights | Example: learning rate |

---

## Example

Suppose we train a neural network.

### Hyperparameters

We choose:

$$
Learning\ Rate = 0.001
$$

$$
Batch\ Size = 32
$$

$$
Epochs = 50
$$

The model then learns parameters such as:

$$
Weights,\ Biases
$$

So:

**Hyperparameters → Configure learning**

**Parameters → Are learned during learning**

---

## Important Rule

> **Parameters are learned; hyperparameters are configured.**

---

# 6. Training vs Inference

Machine Learning systems generally have two major phases:

1. Training
2. Inference

---

# Training

## Definition

**Training** is the process in which the model learns parameters from data.

The model receives training data and repeatedly adjusts its parameters to reduce the training objective/loss.

---

## Training Flow

**Training Data**

↓

**Model**

↓

**Prediction**

↓

**Calculate Loss**

↓

**Optimize Parameters**

↓

**Updated Model**

↓

**Repeat**

---

## Mathematical View

Suppose:

$$
\hat{y} = f(X;\theta)
$$

where:

- $X$ = input
- $\theta$ = model parameters
- $\hat{y}$ = prediction

The training process tries to find parameters:

$$
\theta^*
$$

that minimize the objective:

$$
\theta^* = \arg\min_{\theta} L(\theta)
$$

where:

- $L$ = loss/objective function
- $\theta$ = model parameters

---

# Inference

## Definition

**Inference** is the process of using a trained model to make predictions on new data.

During inference, the model uses its learned parameters to produce an output.

---

## Inference Flow

**New Input**

↓

**Trained Model**

↓

**Prediction**

---

## Example

Suppose a model has been trained to predict house prices.

Training:

**100,000 historical houses**

↓

**Model learns parameters**

↓

**Trained Model**

During inference:

**New House**

↓

**Trained Model**

↓

**₹75 Lakh Prediction**

---

## Training vs Inference

| Training | Inference |
|---|---|
| Model learns | Model predicts |
| Uses training data | Uses new/unseen input |
| Parameters are updated | Parameters are normally fixed |
| Loss is used for optimization | Prediction is generated |
| Computationally expensive | Usually optimized for speed |
| Happens during model development | Happens after deployment or during evaluation |

---

## Important Point

> **Training teaches the model; inference uses what the model has learned.**

---

# 7. General ML Pipeline

A Machine Learning project is not just about choosing an algorithm.

A complete ML workflow generally looks like:

$$
\boxed{
Problem
\rightarrow
Data
\rightarrow
Preparation
\rightarrow
Training
\rightarrow
Evaluation
\rightarrow
Deployment
\rightarrow
Monitoring
}
$$

---

## Step 1: Problem Definition

First, clearly define the business or real-world problem.

Questions:

- What are we trying to predict?
- What is the target?
- What type of ML problem is this?
- What metric defines success?

Example:

> Predict whether a customer will churn.

Target:

$$
Y = Churn
$$

Problem type:

**Binary Classification**

---

# Step 2: Data Collection

Collect relevant data from sources such as:

- Databases
- APIs
- CSV files
- Sensors
- Applications
- Web data
- Business systems

Example:

Customer information:

- Age
- Tenure
- Monthly charges
- Contract type
- Payment method

---

# Step 3: Data Understanding

Understand the dataset before training.

Check:

- Number of samples
- Number of features
- Data types
- Missing values
- Duplicate records
- Outliers
- Class distribution
- Feature distributions

Example:

$$
X.shape = (10000, 20)
$$

This means:

- 10,000 samples
- 20 features

---

# Step 4: Data Cleaning

Fix problems in the dataset.

Common tasks:

- Handle missing values
- Remove duplicates
- Correct invalid values
- Handle inconsistent formats
- Investigate outliers

Example:

Missing Age values

↓

Median imputation

↓

Clean dataset

---

# Step 5: Exploratory Data Analysis (EDA)

EDA is used to understand patterns and relationships in the data.

Common techniques:

- Summary statistics
- Histograms
- Box plots
- Scatter plots
- Correlation analysis
- Distribution analysis

Questions:

- Which features are important?
- Are there outliers?
- Are variables correlated?
- Is the target imbalanced?

---

# Step 6: Feature Engineering

Create or transform features to improve model performance.

Examples:

### Create New Feature

Suppose:

$$
Income
$$

and:

$$
Age
$$

We may create:

$$
IncomePerAge = \frac{Income}{Age}
$$

### Transform Features

Examples:

- Log transformation
- Scaling
- Encoding
- Binning

---

# Step 7: Data Preprocessing

Prepare data in a format suitable for the model.

Common preprocessing techniques:

- Missing value treatment
- Encoding categorical variables
- Feature scaling
- Feature selection
- Text preprocessing
- Image preprocessing

Example:

**City**

Delhi

Mumbai

Chennai

↓

One-Hot Encoding

$$
Delhi = [1,0,0]
$$

$$
Mumbai = [0,1,0]
$$

$$
Chennai = [0,0,1]
$$

---

# Step 8: Train-Test Split

Split the data into separate subsets.

Common setup:

**Training Set**

→ Used to learn parameters.

**Validation Set**

→ Used for model selection and hyperparameter tuning.

**Test Set**

→ Used for final evaluation.

Example:

$$
70\% \rightarrow Training
$$

$$
15\% \rightarrow Validation
$$

$$
15\% \rightarrow Test
$$

The exact proportions depend on the problem and dataset.

---

# Step 9: Model Selection

Choose an appropriate algorithm.

Examples:

### Regression

- Linear Regression
- Random Forest
- Gradient Boosting
- XGBoost

### Classification

- Logistic Regression
- Decision Tree
- Random Forest
- SVM
- XGBoost

### Clustering

- K-Means
- DBSCAN
- Hierarchical Clustering

The algorithm should be selected based on:

- Problem type
- Data characteristics
- Dataset size
- Interpretability requirements
- Computational constraints

---

# Step 10: Model Training

Train the selected model using the training data.

Conceptually:

$$
X_{train},Y_{train}
\rightarrow
Model
\rightarrow
Learned\ Parameters
$$

The model minimizes an objective/loss function.

---

# Step 11: Hyperparameter Tuning

Choose good hyperparameter values.

Common methods:

- Grid Search
- Random Search
- Bayesian Optimization

Example:

For a Decision Tree:

$$
max\_depth \in \{3,5,10,15\}
$$

The goal is to find a configuration that gives good validation performance.

---

# Step 12: Model Evaluation

Evaluate the model using appropriate metrics.

## Regression Metrics

- MAE
- MSE
- RMSE
- $R^2$

## Classification Metrics

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- PR-AUC

The metric should match the problem.

---

# Step 13: Error Analysis

Do not only look at one final metric.

Analyze where the model fails.

Questions:

- Which samples are misclassified?
- Which classes are difficult?
- Are errors concentrated in certain groups?
- Are there systematic patterns in errors?

Error analysis can reveal problems in:

- Data
- Features
- Labels
- Model
- Preprocessing

---

# Step 14: Final Model

After model selection and evaluation, choose the final model.

Depending on the workflow, the final model may be retrained using appropriate training data before deployment.

---

# Step 15: Deployment

Make the trained model available for real-world predictions.

Common deployment methods:

- REST API
- Web application
- Cloud service
- Batch prediction system
- Edge device
- Mobile application

Example:

**User**

↓

**API**

↓

**ML Model**

↓

**Prediction**

---

# Step 16: Monitoring

Deployment is not the end of the ML lifecycle.

The model must be monitored.

Monitor:

- Prediction quality
- Data distribution
- Data drift
- Concept drift
- Latency
- Errors
- Resource usage

---

# Data Drift

Data drift occurs when the distribution of input data changes over time.

Example:

Training data:

$$
Age \approx 20-40
$$

Production data later:

$$
Age \approx 40-70
$$

The input distribution has changed.

---

# Concept Drift

Concept drift occurs when the relationship between inputs and the target changes over time.

Example:

A model predicts customer churn.

Historically:

$$
Discount \rightarrow Lower\ Churn
$$

But customer behavior changes.

Now:

$$
Discount \rightarrow Little\ Effect\ on\ Churn
$$

The relationship learned by the model may no longer be valid.

---

# Complete ML Pipeline

```text
Problem Definition
        ↓
Data Collection
        ↓
Data Understanding
        ↓
Data Cleaning
        ↓
EDA
        ↓
Feature Engineering
        ↓
Preprocessing
        ↓
Train / Validation / Test Split
        ↓
Model Selection
        ↓
Training
        ↓
Hyperparameter Tuning
        ↓
Evaluation
        ↓
Error Analysis
        ↓
Final Model
        ↓
Deployment
        ↓
Monitoring
        ↓
Retraining / Updating