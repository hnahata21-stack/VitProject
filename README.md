# Employee Performance Prediction System

A machine learning project that predicts whether an employee is likely to be a **high** or **low** performer, built entirely from scratch in Python with no external libraries.

**Author:** Harsh Nahata (ID: 26MEI10027)
**Course:** Python Essentials
**Teacher:** Vaishnavi S

## Overview

Given five measurable attributes of an employee (experience, training hours, projects completed, peer rating and attendance), the program predicts the probability that the employee is a high performer. It implements the whole machine learning pipeline by hand: data generation, train/test split, feature scaling, logistic regression trained with gradient descent, and evaluation metrics. An interactive command-line interface then lets you enter a new employee's details and get a prediction.

See [statement.md](statement.md) for the problem statement and scope, and [docs/Employee_Performance_Prediction_Report.pdf](docs/Employee_Performance_Prediction_Report.pdf) for the full project report with design diagrams.

## Features

- Synthetic employee dataset generation (300 records, reproducible with a fixed seed)
- 75/25 train/test split and z-score feature standardization
- Logistic regression implemented from scratch using gradient descent
- Evaluation with accuracy, precision, recall, F1 score and a confusion matrix
- Feature weight report showing which factors influence the prediction most
- Interactive prediction loop with input validation (rejects text and out-of-range values)
- Unit tests using Python's built-in `unittest`

## Technologies / Tools Used

- **Python 3.8+**
- Standard library only: `math`, `random`, `unittest`
- No scikit-learn, numpy or any other third-party package

## Project Structure

```
employee-performance-prediction/
├── employee_performance.py        # main program (model + interactive CLI)
├── test_employee_performance.py   # unit tests
├── README.md
├── statement.md
└── docs/
    ├── Employee_Performance_Prediction_Report.pdf
    └── screenshots/
```

## Steps to Install and Run

1. Make sure Python 3.8 or newer is installed:
   ```
   python --version
   ```
2. Clone the repository (replace the URL with your own):
   ```
   git clone https://github.com/<your-username>/employee-performance-prediction.git
   cd employee-performance-prediction
   ```
3. There is nothing else to install because the project uses only the standard library.
4. Run the program:
   ```
   python employee_performance.py
   ```
5. The program trains the model, prints the evaluation results, and then asks for an employee's details:

   | Prompt | Valid range |
   |---|---|
   | Experience (years) | 0 - 40 |
   | Training hours | 0 - 200 |
   | Projects completed | 0 - 100 |
   | Peer rating | 1 - 5 |
   | Attendance % | 0 - 100 |

   It then prints the predicted class and the probability of being a high performer.

### Example output

```
Accuracy : 0.83
Precision: 0.84
Recall   : 0.86
F1 score : 0.85
Confusion matrix [[TN, FP], [FN, TP]]: [[24, 7], [6, 38]]

Feature weights (larger magnitude = more influence):
  experience_yrs   +2.383
  peer_rating      +2.317
  projects_done    +1.913
  training_hours   +1.646
  attendance_pct   +1.051
```

## Instructions for Testing

Run all unit tests from the project folder:

```
python -m unittest -v
```

The tests cover:

- the sigmoid function (midpoint and overflow safety)
- train/test split sizes
- feature scaling (mean 0, standard deviation 1)
- the evaluation metrics on a hand-made example
- model accuracy on unseen data (must beat 0.75)
- a strong employee profile scoring far above a weak one

All 9 tests should pass.

You can also test input validation manually by running the program and entering letters or out-of-range numbers; the program should ask again instead of crashing.

## Screenshots

Add screenshots of your own runs to `docs/screenshots/` and link them here, for example:

```
![Evaluation output](docs/screenshots/evaluation.png)
![Sample prediction](docs/screenshots/prediction.png)
```

## Notes

Predictions from models trained on historical HR data can reflect past bias. This project is an educational demonstration, and any real use should keep human judgment in the loop.
