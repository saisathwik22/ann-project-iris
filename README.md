# Iris Species Classification

## Project Description
This project focuses on classifying Iris flower species using machine learning techniques. The goal is to build and evaluate models that can accurately predict the species of an Iris flower based on its sepal and petal measurements. Two models are explored: a Perceptron model and a simple Artificial Neural Network (ANN) using Keras/TensorFlow.

## Dataset
The dataset used is the famous Iris dataset, which contains 150 samples of Iris flowers, each belonging to one of three species: Iris-setosa, Iris-versicolor, and Iris-virginica. Each sample has four features:
- SepalLengthCm
- SepalWidthCm
- PetalLengthCm
- PetalWidthCm

### Data Preprocessing
- The 'Id' column was dropped as it's not relevant for classification.
- The 'Species' column (target variable) was encoded into numerical format using `LabelEncoder`.
- The dataset was split into training and testing sets (80% training, 20% testing) with stratification to maintain class distribution.
- Features were scaled using `StandardScaler` to ensure optimal performance for the models.

## Models Implemented

### 1. Perceptron Model
A single-layer Perceptron model was implemented and trained on the scaled training data. The Perceptron is a foundational algorithm for classification, performing binary classification, but can be extended for multi-class problems.

**Evaluation:**
- Accuracy: The model achieved an accuracy of 86.67% on the test set.
- Classification Report: Provides detailed metrics like precision, recall, and F1-score for each class.

### 2. Artificial Neural Network (ANN)
A simple Artificial Neural Network was constructed using TensorFlow/Keras. The network architecture consists of:
- An input layer (implicitly defined by the first `Dense` layer with `input_dim=4`).
- Two hidden `Dense` layers with ReLU activation for non-linearity.
- An output `Dense` layer with 3 neurons (for the three Iris species) and a softmax activation function to output class probabilities.

**Training and Compilation:**
- The model was compiled with the `adam` optimizer, `categorical_crossentropy` loss function (suitable for multi-class classification with one-hot encoded labels), and `accuracy` as the evaluation metric.
- The model was trained for 100 epochs with a batch size of 8, and a validation split of 20% was used during training to monitor performance.

**Evaluation:**
- Test Accuracy: The ANN achieved an accuracy of 96.67% on the test set.
- Training History: Plots showing training and validation accuracy over epochs were generated to visualize model learning and detect overfitting.
