# Employee Performance Analysis – INX Future Inc.

## Project Overview

This project focuses on analyzing employee performance data for INX Future Inc., an organization facing declining employee performance, service delivery escalations, and a reduction in client satisfaction.

The objective is to identify factors influencing employee performance, understand department-wise performance, and develop a machine learning model that predicts employee performance ratings.

The project uses Exploratory Data Analysis (EDA), data preprocessing, Logistic Regression, model evaluation, and feature importance techniques to generate insights and provide actionable business recommendations.

---

## Business Problem

INX Future Inc. has experienced challenges related to employee performance and service delivery, resulting in a decline in client satisfaction of approximately 8 percentage points.

The organization wants to understand:

- Why employee performance is declining.
- Which departments are performing better or worse.
- Which factors are most strongly associated with employee performance.
- How machine learning can help predict employee performance ratings.

---

## Project Objectives

- Analyze employee performance across different departments.
- Identify the top three factors influencing employee performance ratings.
- Perform Exploratory Data Analysis (EDA) to understand employee characteristics and performance patterns.
- Prepare and preprocess the data for machine learning.
- Build a classification model using Logistic Regression.
- Evaluate model performance using appropriate classification metrics.
- Generate business insights and recommendations to improve employee performance.

---

## Dataset Description

The dataset contains employee-related information, including demographic details, job information, satisfaction levels, experience, salary increments, training, attrition, and performance ratings.

| Attribute | Description |
|---|---|
| Total Records | 1,200 employees |
| Total Columns | 28 |
| Target Variable | PerformanceRating |
| Machine Learning Type | Supervised Learning |
| Problem Type | Multi-class Classification |

### Target Variable – PerformanceRating

| Rating | Description |
|---|---|
| 1 | Low |
| 2 | Good |
| 3 | Excellent |
| 4 | Outstanding |

The dataset contains ratings 2, 3, and 4. Rating 1 is not present.

---

## Tools & Technologies Used

- **Python** – Programming language
- **Jupyter Notebook** – Development environment
- **Pandas** – Data manipulation and analysis
- **NumPy** – Numerical operations
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical visualization
- **Scikit-learn** – Machine learning and model evaluation
- **Joblib** – Saving and loading trained models

---

## Project Workflow

1. Data Loading
2. Data Understanding
3. Data Cleaning and Validation
4. Exploratory Data Analysis (EDA)
5. Data Preprocessing
6. Feature Encoding
7. Feature Scaling
8. Train-Test Split
9. Logistic Regression Model Development
10. Model Evaluation
11. Feature Importance Analysis
12. Cross-Validation
13. Employee Performance Prediction
14. Business Recommendations

---

## Exploratory Data Analysis (EDA)

EDA was performed to understand employee characteristics, department-wise performance, and relationships between features and performance ratings.

The analysis included:

- Dataset structure and data types.
- Missing value analysis.
- Duplicate record checking.
- Categorical variable distribution.
- Numerical variable distribution.
- Outlier identification using the IQR method.
- Correlation analysis using Spearman correlation.
- Department-wise performance analysis.
- Employee satisfaction analysis.
- Salary hike and experience analysis.

---

## Data Preprocessing

The following preprocessing techniques were applied:

- Excluded `EmpNumber` because it is an employee identifier and not a meaningful predictive feature.
- Separated the target variable `PerformanceRating` from the input features.
- Converted the `OverTime` variable into numerical format.
- Applied One-Hot Encoding to categorical variables.
- Applied StandardScaler to selected continuous numerical variables.
- Split the data into training and testing sets using stratified sampling.
- Used an 80:20 train-test split.

### Dataset Split

| Dataset | Records |
|---|---:|
| Training Data | 960 |
| Testing Data | 240 |

---

## Machine Learning Model

### Logistic Regression

Logistic Regression was selected as the classification algorithm to predict employee performance ratings.

Two model configurations were evaluated:

1. Baseline Logistic Regression
2. Balanced Logistic Regression using `class_weight='balanced'`

The balanced model was tested to address class imbalance in the target variable.

---

## Model Performance

### Model Comparison

| Metric | Baseline Model | Balanced Model |
|---|---:|---:|
| Accuracy | 82.50% | 75.83% |
| Macro F1 Score | 71.57% | 68.69% |
| Balanced Accuracy | 67.80% | 75.76% |

### Interpretation

- The baseline model achieved higher overall accuracy and Macro F1 Score.
- The balanced model achieved better Balanced Accuracy and improved recognition of minority rating classes.
- Model selection depends on whether the business prioritizes overall prediction accuracy or fairer class-wise recognition.

### Cross-Validation Results

5-fold Stratified Cross-Validation was performed.

| Metric | Mean Score |
|---|---:|---:|
| Accuracy | 82.17% | 
| Macro F1 Score | 72.17%| 
| Balanced Accuracy | 69.63% |

Cross-validation results indicate that the model performance is reasonably consistent across different data folds.

### Top 3 Factors Influencing Employee Performance

Permutation Feature Importance was used to identify the most influential features in model performance.

| Rank | Feature | Importance|
|---|---:|---:|
| 1 | EmpEnvironmentSatisfaction|20.78%|
|2 | EmpLastSalaryHikePercent |20.61 |
| 3 | EmpDepartment_Development |3.94% |

Key Insights

-Employee Environment Satisfaction is the strongest predictor among the analyzed features.
-Last Salary Hike Percentage is another important predictive factor.
-Department membership, particularly Development, contributes to prediction performance.
-Employee satisfaction and compensation-related factors deserve attention in performance improvement initiatives.

Feature importance indicates predictive contribution, not proof of causation.

### Department-Wise Performance Analysis

Average performance ratings were compared across departments.

| Department |Average Performance Rating |
|---|---:|---:|
| Development |3.086 | 
|Data Science | 3.050| 
| Human Resources |2.926 |
|Research & Development| 2.921| 
|Sales |2.861| 
|Finance | 2.776| 

### Observations

-Development has the highest average performance rating.
-Data Science has the second-highest average rating, but its sample size is relatively small.
-Finance has the lowest average performance rating.
-Finance also has a relatively high proportion of employees with Rating 2.

### Business Recommendations

Based on the analysis, the following recommendations are proposed:

-Improve Employee Environment Satisfaction
Identify workplace issues affecting employee satisfaction and improve management support, team collaboration, and the working environment.

-Review Salary Increment Policies
Evaluate compensation and salary hike practices to support employee motivation and perceived fairness.

-Focus on Department-Level Improvement
Conduct targeted performance improvement initiatives in departments such as Finance and Sales.

-Strengthen Training and Development
Provide role-specific training, skill development, and career growth opportunities.

-Monitor Employee Performance Regularly
Use performance metrics and employee feedback to identify issues early.

-Use Predictions as Decision Support
Use model predictions to support analysis and planning, not as a replacement for human judgment.

### Project Limitations
-The dataset contains only 1,200 employee records.
-Performance ratings are imbalanced.
-Rating 1 is absent from the dataset.
-The model is trained on existing employee data and has not been validated for predicting performance of new hires.
-Feature importance represents predictive association and does not establish causality.
-Model predictions should not be used as the sole basis for employee hiring, promotion, appraisal, or termination decisions.

### Conclusion

The project demonstrates how data analysis and machine learning can be used to understand employee performance and identify areas for organizational improvement.
Employee Environment Satisfaction and Last Salary Hike Percentage emerged as the two strongest predictive factors. Department-level analysis also highlighted differences in average performance across the organization.
The developed Logistic Regression model achieved 82.50% test accuracy, while cross-validation achieved a mean accuracy of 82.17%.
The findings can help INX Future Inc. focus on workplace satisfaction, compensation practices, employee development, and department-specific improvement strategies.
