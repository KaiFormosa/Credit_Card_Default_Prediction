# Credit Card Default Prediction 

- Data Source: University of California Irvine Machine Learning Repository (https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients)

- The goal of this project is to develop a model that can predict whether a client would default his/her credit line in the following month. A binary variable, default payment (Yes = 1, No = 0), is used as the response variable and the following 23 variables as explanatory variables:

    - X1: Amount of the given credit (NT dollar): it includes both the individual consumer credit and his/her family (supplementary) credit.
    - X2: Gender (1 = male; 2 = female).
    - X3: Education (1 = graduate school; 2 = university; 3 = high school; 4 = others).
    - X4: Marital status (1 = married; 2 = single; 3 = others).
    - X5: Age (year).
    - X6 - X11: History of past payment. We tracked the past monthly payment records (from April to September, 2005) as follows: X6 = the repayment status in September, 2005; X7 = the repayment status in August, 2005; . . .; X11 = the repayment status in April, 2005. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; . . .; 8 = payment delay for eight months; 9 = payment delay for nine months and above.
    - X12-X17: Amount of bill statement (NT dollar). X12 = amount of bill statement in September, 2005; X13 = amount of bill statement in August, 2005; . . .; X17 = amount of bill statement in April, 2005.
    - X18-X23: Amount of previous payment (NT dollar). X18 = amount paid in September, 2005; X19 = amount paid in August, 2005; . . .;X23 = amount paid in April, 2005. 

- Issues and Approaches
    - Certain values in attributes are unclear. For example, in past payment history attributes, -1 means pay duly and 1 means payment delay for one month. However, there are 0 and -2 in the dataset.
    - New attributes created, such as percentage of credit line used, total number of months with delayed payment, payment delay.
    - The data is imbalanced. Rows with positive label account for only 22% of the dataset. ADASYN oversampling technique was applied.
    - Dummy variables were created for nominal attributes, such as "Education" and "Marriage"
    - Standard scaler applied
    
- Model Training and Results
    - Three Models were selected for training:
        - Logistic Regression
        - Random Forest
        - Support Vector Machine
    - Random Forest has the best accuracy and recall score using 5-fold cross validation on the training set
        |  | Logistic Regression | Random Forest | Support Vector Machine |
        | :---: | :---: | :---: |:---: |
        | Accuracy Mean | 0.659 | 0.759 |0.676|
        | Recall        | 0.547 | 0.706 |0.571|
        | ROC-AUC       | 0.718 | 0.836 |0.755|
    - Evaluation metrics on testing data
        |  | Random Forest |
        | :---: | :---: |
        | Accuracy | 0.766 |
        | Recall        | 0.665 |
        | Precision       | 0.732 |