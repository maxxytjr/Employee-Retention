# Employee-Retention

## Description
A Supervised Learning classifier to anticipate which employees are likely to leave based on features like job satisfaction, salary, performance, etc.

## Workflow

### Data Exploration

1. Exploring categorical features using Seaborn's `countplot()` function
2. Comparing numerical and categorical features using Seaborn's `violinplot()` function
3. Attempted *bivariate segmentations* using Seaborn's `lmplot()` function, where we compared 2 numeric features against one categorical feature
4. Some ad-hoc data cleaning (removing NaNs, duplicates)
5. Ad-hoc feature engineering (replacing strings with integers, one-hot encoding of categorical features, creating new features based on segmentation analysis)
6. More exploration of numeric features using a correlation matrix `df.corr()`
7. Plotting histograms using the `hist()` function to check for any outliers in the numeric data

### Creating an Analytical Base Table
1. Removal of duplicated observations
2. Fixing of structural errors (removing NaNs, filling in missing values, rectifying typos and mislabeling of classes)
3. Handling of mising categorical data
4. Handling of missing numerical data using a **flag-and-fill** method, thereby allowing the algorithm to **estimate the optimal constant for missingness**, instead of just filling it in with the mean
5. Feature engineering (creating new categories for employee types, one-hot-encoding)

### Model Evaluation
1. Compared performance of classification algorithms (L1, L2, random forest, boosted trees)
2. Evaluation of performance was based on metrics such as 
  * **True Positive Rate (TPR)**
  * **False Positive Rate (FPR)**
  * **Area under ROC curve (AUROC)**
  
  ..which are more reliable for imbalanced datasets of classification tasks, compared to mere accuracy scores.
  
3. Standardized features into the same scale
4. Built model pipelines, ran a 10-fold cross-validation for each model to determine best performing model and hyperparameter combination
5. Saved the winning pipeline into a pickle file

### Project Delivery
1. Confirmed performance of chosen model by evaluating AUROC score using test data
2. Created a custom model class that processes unseen data in the raw format (before cleaning, feature engineering, etc) into the desired format for the model to perform predictions on

## Dataset
The dataset has **14249** observations for past/present employees, spanning over 12 different departments. Each observation includes the employee's current employment status.

### Target variable
  * `status` - Current employment status (Employed/Left)

### Features
  * `department` - Department employees belong(ed) to
  * `salary` - Salary level relative to rest of their department
  * `tenure` - Number of years at the company
  * `recently_promoted` - If the employee has been promoted within the last 3 years
  * `n_projects` - Number of projects an employee is/was involved in
  * ` avg_monthly_hours` - average number of hours worked per month
  * `satisfaction` - Score for employee's satisfaction with the company (higher the better)
  * `last_evaluation` - Score for the most recent evaluation of employee (higher the better)
  * `filed_complaint` - If the employee has filed a formal complaint within the last 3 years
