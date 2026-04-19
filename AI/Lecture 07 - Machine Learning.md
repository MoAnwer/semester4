---
tags:
  - ai
  - sheets
---
# Artificial Intelligence Systems: Machine Learning

## What is Machine Learning?

Machine learning is the science and art of programming computers to learn from data, optimizing a performance criterion using example data or past experience.

- **Arthur Samuel (1959):** A field of study that gives computers the ability to learn without being explicitly programmed.
- **Tom Mitchell (1997):** A computer program is said to learn from experience EE with respect to some task TT and some performance measure PP, if its performance on TT, as measured by PP, improves with experience EE.

Machine learning is a component within the broader fields of Data Science and Data Mining, distinct from classical programming. It involves algorithms that learn from data, using features extracted from that data.

## Types of Machine Learning

Machine learning systems can be classified based on several criteria:

- **Training Supervision:**
    - Supervised Learning
    - Unsupervised Learning
    - Reinforcement Learning
    - Semi-supervised Learning
- **Learning Incrementalism:**
    - Online Learning
    - Batch Learning
- **Learning Mechanism:**
    - Instance-based Learning (comparing new data to known data)
    - Model-based Learning (detecting patterns and building a predictive model)

A more specific category, Deep Learning, combines elements of both supervised and unsupervised learning.

### Supervised Learning

- **Definition:** Maps an input to an output based on example input-output pairs. It infers a function from labeled training data consisting of input objects (vectors) and desired output values (labels or supervisory signals).
- **Goal:** To analyze training data and produce an inferred function that can map new examples.
- **Where to Use:** When you have labeled data and want to predict outcomes. Ideal for classification and regression tasks. Best used when historical data with outcomes is available.
- **Applications:**
    - Image, speech, and text processing (classification, recognition, sentiment analysis).
    - Predictive analytics (forecasting sales, churn, stock prices, weather).
    - Recommendation and personalization systems.
    - Healthcare and finance (medical diagnosis, fraud detection, credit scoring).
    - Automation and control (autonomous vehicles, manufacturing checks, gaming AI).

#### Classification

- **Definition:** Predicts categorical outputs by assigning data into predefined classes (e.g., spam/non-spam, disease risk categories). Algorithms learn to map input features to discrete labels.
- **Example Algorithms:** Logistic Regression, Decision Tree, Random Forest, K-Nearest Neighbors (KNN), Naive Bayes, Support Vector Machine.
- **Process:**
    1. **Input Raw Data:** Labeled training data.
    2. **Algorithm Processing:** Model training.
    3. **Output:** A trained model that can classify unseen, unlabeled data.

#### Regression

- **Definition:** Predicts continuous values (e.g., house prices, product sales). Learns the relationship between input features and a numerical target variable.
- **Example Algorithms:** Linear Regression, Polynomial Regression, Ridge Regression, Lasso Regression, Decision Tree, Random Forest.
- **Example Calculation (Linear Regression):**
    - The goal is to find the best-fit line of the form y=mx+by=mx+b.
    - Given data points, the algorithm aims to minimize the error between the predicted yy values and the actual yy values.
    - For instance, if you have data points like (0.2, 1), (0.4, 2), (0.6, 3), (0.8, 4), a regression model would attempt to find mm and bb to approximate the relationship. A perfect fit would yield y=5xy=5x, so m=5m=5 and b=0b=0.

### Unsupervised Learning

- **Definition:** Learns from test data that has not been labeled, classified, or categorized. The algorithm finds hidden patterns, groups, or relationships within the data on its own.
- **Goal:** To discover structure in unlabeled data.
- **Where to Use:** When data is unlabeled or unstructured. Useful for exploratory analysis, clustering, or feature extraction. Common in marketing, recommendation systems, and fraud detection where patterns are more important than labels.
- **Applications:**
    - Clustering and segmentation (grouping similar data points, customers, or images).
    - Anomaly detection (spotting unusual patterns or outliers).
    - Dimensionality reduction (simplifying datasets while retaining key information).
    - Recommendation and marketing (identifying user preferences).
    - Data preprocessing and analysis (cleaning data, detecting patterns).

#### Clustering

- **Definition:** The process of grouping data points into clusters based on their similarity. Useful for identifying patterns and relationships without labeled examples.
- **Example Techniques:** K-Means, DBSCAN, Mean-shift.
- **Process:**
    1. **Input Raw Data:** Unlabeled data.
    2. **Algorithm Processing:** Model training.
    3. **Output:** Clusters or groups representing inherent structures in the data, requiring interpretation.

### Reinforcement Learning

- **Definition:** A type of machine learning technique where an agent learns in an interactive environment by trial and error, using feedback (rewards or penalties) from its own actions and experiences.
- **Goal:** To train an agent to make a sequence of decisions that maximize a cumulative reward over time.
- **Comparison:**
    - Unlike supervised learning, feedback is in the form of rewards/penalties, not correct actions.
    - Unlike unsupervised learning, the goal is to find an action model that maximizes cumulative reward, not just discover patterns.
- **Components:** Agent, Environment, State, Actions, Reward.
- **Where to Use:** When an agent needs to learn by interacting with an environment. Best for decision-making or optimization tasks with feedback loops. Used when long-term performance or adaptive behavior is crucial.
- **Applications:**
    - Gaming and simulation (teaching agents to play and adapt).
    - Robotics and automation (enabling autonomous tasks).
    - Autonomous vehicles (real-time decision making).
    - Healthcare and finance (optimizing treatment plans, trading).
    - Recommendation and personalization (adaptive suggestions).
    - Industrial and energy management (optimizing control systems).

### Semi-Supervised Learning

- **Definition:** Utilizes a small amount of labeled data along with a large amount of unlabeled data for training. It combines aspects of both unsupervised and supervised learning.
- **Goal:** To improve learning performance when labeling data is costly or time-consuming.
- **Where to Use:** When labeled data is limited, but unlabeled data is abundant. Useful in domains with high labeling costs (medical, NLP, image datasets). Ideal when unlabeled data holds valuable information.
- **Applications:**
    - Image Classification (improving accuracy with mixed datasets).
    - Natural Language Processing (enhancing language models).
    - Speech Recognition (boosting accuracy).
    - Recommendation Systems (improving suggestions).
    - Healthcare & Medical Imaging (enhancing analysis).

### Self-Supervised Learning

- **Definition:** A modern approach where models generate their own labels from raw data. Instead of manual annotation, the model learns by predicting parts of the data from other parts.
- **Goal:** To learn representations from data without manual labels.
- **Where to Use:** When manual labeling is impossible or expensive. Suitable for large-scale datasets (text, audio, images). Best for pre-training models that can be fine-tuned for specific supervised tasks.
- **Applications:**
    - Natural Language Processing.
    - Computer Vision and Speech Recognition.
    - Video understanding.
    - Pre-training for large AI models.

## Machine Learning Approach

A typical machine learning workflow involves the following steps:

1. **Load Data:** Obtain the raw dataset.
2. **Prepare Your Data:**
    - **Extract Features:** Identify and select relevant features from the data.
3. **Build & Train Model:**
    - **Train Model:** Use the prepared data to train a machine learning model.
4. **Evaluate Model:** Assess the performance of the trained model.
5. **Run Model:** Deploy the model for consumption on new data.

## What is a Model?

A model is a representation of some phenomenon. It can be:

- **Non-Mathematical/Statistical Model:** A conceptual representation.
- **Mathematical/Statistical Model:** Often describes relationships between variables.

### Types of Models

#### Deterministic Models

- **Hypothesis:** Hypothesize exact relationships between variables.
- **Suitability:** Used when prediction error is negligible.
- **Example Calculation (Body Mass Index - BMI):**
    - **Metric Formula:** BMI=Weight in Kilograms(Height in Meters)2BMI=(Height in Meters)2Weight in Kilograms​
    - **Non-Metric Formula:** BMI=Weight (Pounds)×703(Height in inches)2BMI=(Height in inches)2Weight (Pounds)×703​

#### Probabilistic Models

- **Hypothesis:** Hypothesize two components: a deterministic part and a random error component.
- **Formula Structure:** Observed Value=Deterministic Component+Random ErrorObserved Value=Deterministic Component+Random Error
- **Example:** Systolic Blood Pressure (SBP) of a newborn. SBP=6×age (d)+ESBP=6×age (d)+E Where EE represents random error due to factors other than age, such as birth weight.

## Deep Learning

- **Definition:** An artificial intelligence model that imitates the workings of the human brain in processing data and creating patterns for decision-making.
- **Mechanism:** Uses multiple layers to progressively extract higher-level features from raw input. Lower layers might identify simple features (like edges in an image), while higher layers identify more complex concepts (like digits or faces).
- **Also Known As:** Deep neural learning or deep neural network.
- **Structure:** Consists of an input layer, multiple hidden layers (which makes it "deep"), and an output layer. This differs from a simple neural network, which typically has only one hidden layer.