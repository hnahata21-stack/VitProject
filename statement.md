# Project Statement

## Problem Statement

Organizations want an objective, data-driven way to understand which factors are linked to strong employee performance, and to estimate how a given employee is likely to perform. Manual judgments can be inconsistent, and it is hard to see how much each factor (experience, training, workload, peer feedback, attendance) really matters.

This project builds a system that, given an employee's years of experience, training hours, projects completed, peer rating and attendance percentage, predicts the probability that the employee is a **high performer** and classifies them as high or low performer.

## Scope of the Project

**In scope**

- Generating a synthetic labeled employee dataset (real HR data can replace it later)
- Splitting data into training and test sets and standardizing features
- Implementing logistic regression from scratch in pure Python (no machine learning libraries)
- Evaluating the model with accuracy, precision, recall, F1 score and a confusion matrix
- Showing feature weights to explain which factors influence the prediction most
- An interactive command-line interface with input validation
- Unit tests and project documentation

**Out of scope (in this version)**

- Real employee data, databases or CSV import
- A graphical or web interface
- Advanced models (decision trees, neural networks) and cross-validation
- Automated decision-making about hiring, promotion or pay

## Target Users

- **HR analysts and managers** who want a quick, explainable estimate of performance from key indicators
- **Students and learners** who want to understand how a machine learning model works internally without relying on libraries
- **Instructors and evaluators** reviewing a from-scratch implementation of a full ML pipeline

## High-Level Features

- Dataset generation with a reproducible random seed
- Train/test split and z-score feature scaling
- From-scratch logistic regression trained with gradient descent
- Full evaluation report (accuracy, precision, recall, F1, confusion matrix)
- Feature importance display through learned weights
- Interactive prediction with validated input and probability output
- Unit test suite using Python's built-in `unittest`
- Standard library only, so it runs anywhere Python 3 is installed
