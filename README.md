# Student Performance Classification – CMP6202 D2

## Project Overview

This project was developed for the CMP6202 Artificial Intelligence and Machine Learning coursework.

The project investigates whether supervised machine learning algorithms can classify student pass/fail outcomes, with particular attention to identifying students at risk of failing.

## Dataset

The Student Performance Dataset was obtained from Kaggle:

https://www.kaggle.com/datasets/suvidyasonawane/student-performance-dataset

The dataset contains 5,000 records and 16 columns, including demographic information, study habits, attendance, previous academic performance, subject scores and outcome variables.

The target variable is `Pass_Fail`. The dataset contains 4,735 passing students (94.7%) and 265 failing students (5.3%).

The dataset is published under the CC0 Public Domain licence.

## Classification Models

The project compares five approaches:

- Dummy Classifier (majority-class baseline)
- Logistic Regression
- Decision Tree
- Random Forest
- Tuned Random Forest

Two classification scenarios are investigated:

1. **Early-warning:** Uses demographic, study-behaviour and historical features without final subject marks.
2. **Exam-score:** Includes Mathematics, Science and English marks to examine how these variables affect classification performance.

## Data Preparation and Evaluation

The analysis uses an 80/20 stratified training and testing split, with five-fold stratified cross-validation for hyperparameter tuning.

Preprocessing includes numerical transformations and categorical encoding within machine learning pipelines.

Model performance is evaluated using accuracy, balanced accuracy, precision, recall, F1-score, ROC-AUC and confusion matrices.

The notebook also includes exploratory visualisations, training-versus-testing comparisons and feature-importance analysis.

## Key Findings

The early-warning models performed poorly at identifying failing students despite relatively high accuracy for some models.

The tuned exam-score Random Forest achieved 98.4% test accuracy and 94.3% recall for failing students.

However, the exam-score results benefit from subject marks that are closely related to the definition of the target outcome. Therefore, these results should not be interpreted as evidence of reliable early-warning prediction.

The project highlights the importance of recognising class imbalance, target leakage and overfitting when evaluating classification models.

## Repository Files

| File | Description |
|---|---|
| `classification.ipynb` | Jupyter notebook containing Python code, exploratory data analysis, model training, evaluation and saved outputs. |
| `Student_Performance_Dataset.csv` | Dataset used for classification. |
| `CMP6202_D2_Report.docx` | Coursework report covering the methodology, results, interpretation, limitations and reflection. |
| `README.md` | Project documentation and instructions. |

## How to Run

1. Download the repository files.
2. Open `classification.ipynb` using Jupyter Notebook, JupyterLab or Google Colab.
3. Ensure `Student_Performance_Dataset.csv` is in the same working directory.
4. Install the required Python libraries: pandas, NumPy, matplotlib, seaborn and scikit-learn.
5. Run the notebook cells in order to reproduce the analysis.

## Limitations

The dataset's provenance and applicability to real educational settings are uncertain.

The substantial class imbalance limits the usefulness of accuracy alone, while the exam-score scenario includes features closely related to the target definition.

The models should not be used for real student-support decisions without additional validation.

## Coursework Information

**Module:** CMP6202 – Artificial Intelligence and Machine Learning

**Assessment:** D2 – Classification Coursework

**Project:** Predicting Student Academic Performance Using Supervised Machine Learning
