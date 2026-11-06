# Diabetes Prediction Using Random Forest

A Machine Learning project that predicts diabetes outcomes using the Random Forest Classifier and the Pima Indians Diabetes Dataset.

## Project Overview

This project aims to predict whether a person belongs to the diabetic or non-diabetic class based on medical measurements.

The project uses Python and Scikit-learn to perform data cleaning, exploratory data analysis, model training, evaluation, and prediction.

**Algorithm:** Random Forest Classifier

**Project Type:** Supervised Machine Learning – Binary Classification

**Note:** This project is intended for educational purposes only. It is not a medical diagnostic tool.

## Project Objectives

- Analyze the diabetes dataset.
- Perform data cleaning and preprocessing.
- Handle missing values using median imputation.
- Perform Exploratory Data Analysis (EDA).
- Train a Random Forest classification model.
- Evaluate model performance using multiple metrics.
- Visualize model predictions and feature importance.
- Save and load the trained model.

## Dataset Information

**Dataset:** Pima Indians Diabetes Dataset

**Original Dataset Size:** 768 records

**Number of Features:** 8

**Target Column:** Outcome

### Input Features

| Feature | Description |
|---|---|
| Pregnancies | Number of times pregnant |
| Glucose | Plasma glucose concentration |
| BloodPressure | Diastolic blood pressure |
| SkinThickness | Triceps skin fold thickness |
| Insulin | 2-Hour serum insulin |
| BMI | Body Mass Index |
| DiabetesPedigreeFunction | Diabetes pedigree function |
| Age | Age of the person |

### Target Variable

- `0` = No Diabetes
- `1` = Diabetes

**Dataset Source:** [Pima Indians Diabetes Dataset](https://github.com/Zue77/Pima-Indians-Diabetes-Dataset)

## Technologies and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- Joblib

## Project Workflow

### 1. Data Loading and Understanding

- Loaded the diabetes dataset using Pandas.
- Examined dataset dimensions, columns, data types, and statistical information.
- Checked missing values and duplicate records.

### 2. Data Cleaning and Preprocessing

- Removed duplicate records.
- Treated zero values in Glucose, BloodPressure, SkinThickness, Insulin, and BMI as missing values.
- Used median imputation through a Scikit-learn Pipeline.
- Kept imputation within the training process to avoid data leakage.

### 3. Exploratory Data Analysis (EDA)

Performed visual analysis using:

- Diabetes outcome distribution.
- Age distribution.
- Glucose distribution.
- BMI vs Diabetes Outcome.
- Feature correlation heatmap.

### 4. Train-Test Split

The dataset was divided into:

- 80% Training Data
- 20% Testing Data

The split used `random_state=42` and stratification to maintain the class distribution.

| Dataset | Records |
|---|---:|
| Training | 614 |
| Testing | 154 |

### 5. Random Forest Model

The project uses the Random Forest Classifier with the following configuration:

| Parameter | Value |
|---|---|
| Algorithm | Random Forest |
| Number of Trees | 300 |
| Random State | 42 |
| Class Weight | Balanced |
| Missing Value Handling | Median Imputation |

The trained model uses multiple decision trees to make binary classification predictions.

## Model Evaluation

The model was evaluated using the testing dataset.

### Actual Model Results

| Evaluation Metric | Score |
|---|---:|
| Accuracy | 74.03% |
| Precision | 61.67% |
| Recall | 68.52% |
| F1-score | 64.91% |
| ROC-AUC | 82.94% |

### Classification Report

| Class | Precision | Recall | F1-score | Support |
|---|---:|---:|---:|---:|
| No Diabetes | 0.82 | 0.77 | 0.79 | 100 |
| Diabetes | 0.62 | 0.69 | 0.65 | 54 |

### Cross-Validation Results

5-fold cross-validation was performed using ROC-AUC on the training dataset.

- Average ROC-AUC: **82.17%**
- Standard Deviation: **2.16%**

This provides an additional assessment of model performance across different training folds.

## Visualizations

The project generates the following visualizations:

1. Diabetes Outcome Distribution
2. Age Distribution
3. Glucose Distribution
4. BMI vs Diabetes Outcome
5. Feature Correlation Heatmap
6. Random Forest Confusion Matrix
7. Random Forest ROC Curve
8. Random Forest Feature Importance

## Sample Prediction

A sample patient was provided to test the trained model.

**Sample input:**

- Pregnancies: 2
- Glucose: 120
- BloodPressure: 70
- SkinThickness: 25
- Insulin: 80
- BMI: 28.5
- DiabetesPedigreeFunction: 0.45
- Age: 30

**Model Output:**

- Predicted Outcome: No Diabetes
- Estimated Diabetes Probability: 22.33%

This is an example prediction from the trained model, not a clinical assessment.

## Model Saving and Loading

The trained Random Forest Pipeline was saved using Joblib.

**Saved model path:**

`models/diabetes_random_forest.joblib`

The saved model was successfully loaded and tested again. Its prediction matched the original model's prediction.

## Project Structure

```text
Diabetes-Prediction-ML/
│
├── data/
│   └── README.md
│
├── images/
│   ├── diabetes_distribution.png
│   ├── age_distribution.png
│   ├── glucose_distribution.png
│   ├── bmi_vs_outcome.png
│   ├── correlation_heatmap.png
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   └── feature_importance.png
│
├── models/
│   └── diabetes_random_forest.joblib
│
├── Diabetes_Prediction.ipynb
├── requirements.txt
├── README.md
└── .gitignore
```

## How to Run the Project

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Navigate to the Project Folder

```bash
cd Diabetes-Prediction-ML
```

### 3. Create a Virtual Environment

```bash
python -m venv .venv
```

### 4. Activate the Environment

For Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

### 5. Install Dependencies

```bash
pip install -r requirements.txt
```

### 6. Download the Dataset

Download `diabetes.csv` from the dataset source and place it inside the `data` folder.

### 7. Run Jupyter Notebook

```bash
jupyter notebook
```

Open `Diabetes_Prediction.ipynb` and execute the cells in order.

## Skills Demonstrated

- Python Programming
- Machine Learning
- Random Forest Classification
- Data Cleaning
- Data Preprocessing
- Exploratory Data Analysis
- Pandas and NumPy
- Scikit-learn
- Model Evaluation
- Cross-Validation
- Data Visualization
- Model Saving and Loading

## Future Improvements

- Develop an interactive Streamlit application.
- Perform careful hyperparameter tuning.
- Evaluate model calibration and classification thresholds.
- Test performance on additional datasets.
- Further investigate recall for the diabetes class.

## Disclaimer

This project is for educational and learning purposes only. Predictions generated by this model should not be used for medical diagnosis, treatment decisions, or replacing professional medical advice.