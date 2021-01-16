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

- Approaches
    1. Quick checkup of the data:
        - Dataset size 30000 rows * 25 columns (attributes)
        - Column name revised to corresponding month/year
        - Check data type and missing values
        - Check mean, standard deviation and distribution of values of each attribute
    2. Create a training set for data exploration
        - Check correlation between each pair of attribute
        - Check if distribution of attribute categories changes between the default and non-default group
        
        