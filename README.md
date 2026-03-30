# Sensorless Drive Diagnosis using Artificial Neural Networks

## Overview
This project was completed for the **6009CMD Neural Networks coursework**. The aim of the project is to build and evaluate Artificial Neural Network (ANN) models for a **multiclass classification** problem using the **Sensorless Drive Diagnosis** dataset.

The case study focuses on predicting the correct drive-condition class from numerical input features. In addition to standard classification, the project also examines **prediction confidence**, **ambiguity detection**, and **class confusion analysis** to identify uncertain or potentially misclassified samples.

The work is divided into:

- **Part A** – independently designed ANN models
- **Part B** – GenAI-guided ANN development, tuning, and comparison
- **Part C** – critical comparison and reflection

---

## Project Objectives
The main objectives of this coursework are:

- prepare and analyse a large tabular dataset
- design and implement ANN models for multiclass classification
- compare multiple architectures fairly
- evaluate model performance using accuracy, macro F1-score, and confusion matrices
- identify uncertain or ambiguous predictions using confidence-based analysis
- compare independent modelling decisions against GenAI-assisted modelling

---

## Dataset
The dataset used in this project is the **Sensorless Drive Diagnosis Dataset**.

This is a tabular multiclass dataset where each sample contains **48 numerical input features** and belongs to **one of 11 output classes**. The task is to classify the correct class label based on the feature values.

---

## Repository Structure
```text
.
├── README.md
├── data/
│   └── sensorless_drive_diagnosis_verified.csv
├── notebooks/
│   ├── part_a/
│   │   └── ANN_PART_A.ipynb
│   └── part_b/
│       └── ANN_PART_B.ipynb
├── outputs/
│   ├── part_a/
│   └── part_b/
└── video/
```

> Update file and folder names if your final repository structure is slightly different.

---

## Part A Summary
Part A was completed using independent design choices and research.

Main steps included:

- data loading and quality checks
- exploratory data analysis (EDA)
- preprocessing and scaling
- train / validation / test split
- baseline **Single Layer Perceptron (SLP)**
- improved **Basic MLP**
- focused tuning of the stronger model
- confidence and ambiguity analysis
- confusion matrix and class-level performance analysis

### Part A Models
1. **SLP (Baseline)**
2. **Basic MLP**

### Part A Key Results
| Model | Validation Accuracy | Validation Macro F1 | Test Accuracy | Test Macro F1 |
|---|---:|---:|---:|---:|
| SLP | 0.9013 | 0.9006 | 0.8960 | 0.8950 |
| Basic MLP | 0.9877 | 0.9877 | 0.9867 | 0.9867 |

---

## Part B Summary
Part B extends the project using **Generative AI guidance** for architecture design, regularisation, hyperparameter tuning, and evaluation.

The same dataset, preprocessing pipeline, and evaluation procedure from Part A were retained to ensure a fair comparison.

### GenAI-Guided Additions
The Advanced MLP introduced:

- multiple hidden layers
- Batch Normalization
- Dropout
- L2 regularisation
- EarlyStopping
- ReduceLROnPlateau
- focused hyperparameter tuning

### Part B Models
1. **Advanced MLP – Untuned**
2. **Advanced MLP – Tuned**

### Part B Key Results
| Model | Validation Accuracy | Validation Macro F1 | Test Accuracy | Test Macro F1 |
|---|---:|---:|---:|---:|
| Advanced MLP - Untuned | 0.9968 | 0.9968 | 0.9972 | 0.9972 |
| Advanced MLP - Tuned | 0.9974 | 0.9974 | 0.9967 | 0.9967 |

### Part B Key Finding
The **tuned Advanced MLP** achieved the strongest **validation** performance, while the **untuned Advanced MLP** achieved the best **test** performance, suggesting slightly better generalisation on unseen data.

---

## Final Model Comparison
| Model | Type | Validation Accuracy | Validation Macro F1 | Test Accuracy | Test Macro F1 |
|---|---|---:|---:|---:|---:|
| SLP (Part A) | Baseline ANN | 0.9013 | 0.9006 | 0.8960 | 0.8950 |
| Basic MLP (Part A) | Improved ANN | 0.9877 | 0.9877 | 0.9867 | 0.9867 |
| Advanced MLP - Untuned (Part B) | GenAI-guided ANN | 0.9968 | 0.9968 | 0.9972 | 0.9972 |
| Advanced MLP - Tuned (Part B) | GenAI-guided ANN | 0.9974 | 0.9974 | 0.9967 | 0.9967 |

---

## Confidence and Ambiguity Analysis
A key part of this project was going beyond simple classification.

Confidence-based analysis was used to:
- identify low-confidence predictions
- estimate ambiguity in the model outputs
- examine whether incorrect predictions had lower confidence than correct predictions
- evaluate how well low-confidence flags captured errors

For the final tuned Advanced MLP:
- low-confidence threshold: **0.90**
- low-confidence samples: **92 / 8777 (1.05%)**
- total incorrect predictions: **29**
- errors flagged by low confidence: **24**
- error capture rate: **82.76%**

This shows that the model was not only highly accurate, but also effective at identifying many of its own uncertain predictions.

---

## Class-Level Findings
For the final tuned Advanced MLP:

- **Hardest class by F1-score:** Class 5
- **Easiest class by F1-score:** Class 10

Top confusion pairs included:
- **5 → 8**
- **1 → 9**
- **5 → 0**
- **9 → 1**

This class-level analysis helped identify where the model was most likely to struggle.

---

## How to Run the Project

### Option 1: Google Colab
1. Upload the notebook and dataset to Google Drive.
2. Open the notebook in Colab.
3. Mount Google Drive if required.
4. Update dataset file paths if needed.
5. Run all cells in order.

### Option 2: Local Jupyter / VS Code
1. Clone the repository.
2. Create a Python environment.
3. Install the required packages.
4. Open the notebook in Jupyter or VS Code.
5. Update file paths if needed.
6. Run cells in order.

---

## Main Requirements
Recommended Python version:
- Python 3.10+

Main libraries used:
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- tensorflow / keras
- joblib

Example installation:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow joblib
```

---

## Outputs
The project saves outputs such as:

- trained model files
- tuning result tables
- confusion matrices
- class-wise performance tables
- confidence analysis tables
- final model comparison tables and plots

---

## GenAI Usage Statement
Part B of this coursework used Generative AI to suggest:

- Advanced MLP architecture ideas
- regularisation methods
- hyperparameter tuning strategy
- evaluation improvements

These suggestions were **critically reviewed**, not applied blindly. Some suggestions were adopted, while others were rejected where they were unnecessary, overly complex, or unsuitable for a balanced tabular dataset.

---

## Author
**Harshpreet Singh**  
Coventry University  
Computer Science

---

