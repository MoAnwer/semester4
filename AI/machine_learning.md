---
tags:
  - ai
  - sheets
---



Reinforcement Learning

    Definition: A type of machine learning technique where an agent learns in an interactive environment by trial and error, using feedback (rewards or penalties) from its own actions and experiences.
    Goal: To train an agent to make a sequence of decisions that maximize a cumulative reward over time.
    Comparison:
        Unlike supervised learning, feedback is in the form of rewards/penalties, not correct actions.
        Unlike unsupervised learning, the goal is to find an action model that maximizes cumulative reward, not just discover patterns.
    Components: Agent, Environment, State, Actions, Reward.
    Where to Use: When an agent needs to learn by interacting with an environment. Best for decision-making or optimization tasks with feedback loops. Used when long-term performance or adaptive behavior is crucial.
    Applications:
        Gaming and simulation (teaching agents to play and adapt).
        Robotics and automation (enabling autonomous tasks).
        Autonomous vehicles (real-time decision making).
        Healthcare and finance (optimizing treatment plans, trading).
        Recommendation and personalization (adaptive suggestions).
        Industrial and energy management (optimizing control systems).

Semi-Supervised Learning

    Definition: Utilizes a small amount of labeled data along with a large amount of unlabeled data for training. It combines aspects of both unsupervised and supervised learning.
    Goal: To improve learning performance when labeling data is costly or time-consuming.
    Where to Use: When labeled data is limited, but unlabeled data is abundant. Useful in domains with high labeling costs (medical, NLP, image datasets). Ideal when unlabeled data holds valuable information.
    Applications:
        Image Classification (improving accuracy with mixed datasets).
        Natural Language Processing (enhancing language models).
        Speech Recognition (boosting accuracy).
        Recommendation Systems (improving suggestions).
        Healthcare & Medical Imaging (enhancing analysis).

Self-Supervised Learning

    Definition: A modern approach where models generate their own labels from raw data. Instead of manual annotation, the model learns by predicting parts of the data from other parts.
    Goal: To learn representations from data without manual labels.
    Where to Use: When manual labeling is impossible or expensive. Suitable for large-scale datasets (text, audio, images). Best for pre-training models that can be fine-tuned for specific supervised tasks.
    Applications:
        Natural Language Processing.
        Computer Vision and Speech Recognition.
        Video understanding.
        Pre-training for large AI models.

Machine Learning Approach

A typical machine learning workflow involves the following steps:

    Load Data: Obtain the raw dataset.
    Prepare Your Data:
        Extract Features: Identify and select relevant features from the data.
    Build & Train Model:
        Train Model: Use the prepared data to train a machine learning model.
    Evaluate Model: Assess the performance of the trained model.
    Run Model: Deploy the model for consumption on new data.

What is a Model?

A model is a representation of some phenomenon. It can be:

    Non-Mathematical/Statistical Model: A conceptual representation.
    Mathematical/Statistical Model: Often describes relationships between variables.

Types of Models
Deterministic Models

    Hypothesis: Hypothesize exact relationships between variables.
    Suitability: Used when prediction error is negligible.
    Example Calculation (Body Mass Index - BMI):
        Metric Formula:
        BMI=Weight in Kilograms(Height in Meters)2
        BMI=(Height in Meters)2Weight in Kilograms​
        Non-Metric Formula:
        BMI=Weight (Pounds)×703(Height in inches)2
        BMI=(Height in inches)2Weight (Pounds)×703​

Probabilistic Models

    Hypothesis: Hypothesize two components: a deterministic part and a random error component.
    Formula Structure: Observed Value=Deterministic Component+Random ErrorObserved Value=Deterministic Component+Random Error
    Example: Systolic Blood Pressure (SBP) of a newborn.
    SBP=6×age (d)+E
    SBP=6×age (d)+E Where EE represents random error due to factors other than age, such as birth weight.

Deep Learning

    Definition: An artificial intelligence model that imitates the workings of the human brain in processing data and creating patterns for decision-making.
    Mechanism: Uses multiple layers to progressively extract higher-level features from raw input. Lower layers might identify simple features (like edges in an image), while higher layers identify more complex concepts (like digits or faces).
    Also Known As: Deep neural learning or deep neural network.
    Structure: Consists of an input layer, multiple hidden layers (which makes it "deep"), and an output layer. This differs from a simple neural network, which typically has only one hidden layer.
