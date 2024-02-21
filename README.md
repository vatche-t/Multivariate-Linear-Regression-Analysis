# Multivariate Regression Analysis on Financial Data

### Description

This project focuses on conducting multivariate regression analysis on financial data using Python. The dataset, stored in an Excel file named "Book1.xlsx," consists of two sheets: "Sheet1" with two variables and "Sheet1 (2)" with three variables. The goal is to explore the relationships between these variables, perform regression analysis, and visualize the results.

### Project Structure

1. **Data Loading and Exploration**
    - Utilize `pandas` to read all sheets from the Excel file.
    - Display the names and initial rows of each dataframe.

2. **Data Cleaning and Preparation**
    - Correct column headers for better readability.
    - Handle missing values by dropping rows with NaN values.
    - Convert columns to numeric types.

3. **Univariate Analysis**
    - Visualize distributions of variables in both sheets using histograms.

4. **Linear Regression Analysis**
    - Conduct Ordinary Least Squares (OLS) linear regression analysis on "Sheet1" and "Sheet1 (2)."
    - Output the regression summary, including coefficients, p-values, and R-squared values.
    - Plot the scatter plots and regression lines for visual representation.

5. **Polynomial Regression Analysis**
    - Apply polynomial regression of degree 2 to explore non-linear relationships.
    - Visualize the results through scatter plots and polynomial regression curves.

6. **Cross-Validation and Model Evaluation**
    - Implement 5-fold cross-validation for polynomial regression models.
    - Evaluate models using Mean Squared Error (MSE) as a performance metric.

7. **Regularized Regression (Ridge and Lasso)**
    - Apply Ridge and Lasso regression models with cross-validation to handle multicollinearity.
    - Identify the best hyperparameters (alpha values) and evaluate model performance.

8. **Residual Analysis**
    - Examine residuals of regression models to assess model goodness-of-fit.
    - Plot residuals against predicted values for insights.

9. **Q-Q Plot**
    - Create Quantile-Quantile (Q-Q) plots to assess the normality of residuals.

### Instructions

1. **Prerequisites**
    - Ensure you have Python installed.
    - Install required libraries using `pip install -r requirements.txt`.

2. **Run the Code**
    - Execute the Jupyter Notebook or Python script to run the code sequentially.
    - Observe the outputs and visualizations generated during each step.

3. **Explore Visualizations**
    - Review generated plots and visualizations in the project directory.
    - Analyze regression results, scatter plots, and Q-Q plots to gain insights.


### Files

- `Book1.xlsx`: The Excel file containing the financial dataset.

### Notes

- Make sure to adapt the file paths and names based on your project setup.
- Feel free to explore and expand the analysis based on your specific needs.

## OSL

```python
# Import necessary libraries for regression analysis
import statsmodels.api as sm
```
This line imports the `statsmodels` library, specifically the `api` module, which provides tools for statistical modeling.

```python
# Prepare the data for regression analysis on Sheet1
X1 = sm.add_constant(sheet1['price'])  # adding a constant
Y1 = sheet1['ytm']
```
In this section, a constant term is added to the independent variable 'price' for regression analysis on "Sheet1." The constant is necessary for the regression model. `X1` represents the independent variable, and `Y1` represents the dependent variable 'ytm.'

```python
# Perform the regression analysis for Sheet1
model1 = sm.OLS(Y1, X1).fit()
```
This line applies Ordinary Least Squares (OLS) regression using the `sm.OLS` method to fit a linear regression model to the data in "Sheet1." The model is then fitted using the `.fit()` method.

```python
# Prepare the data for regression analysis on Sheet1 (2)
X2 = sheet2[['inventory', 'price']]  # independent variables
X2 = sm.add_constant(X2)  # adding a constant
Y2 = sheet2['ytm']  # dependent variable
```
Similar to the first regression, this section prepares the data for regression analysis on "Sheet1 (2)." It includes two independent variables ('inventory' and 'price'). A constant term is added to the independent variables, and `Y2` represents the dependent variable 'ytm.'

```python
# Perform the regression analysis for Sheet1 (2)
model2 = sm.OLS(Y2, X2).fit()
```
This line performs OLS regression for "Sheet1 (2)" and fits the model using the `.fit()` method.

```python
# Output the summary of the regression analysis for both sheets
print('Regression analysis summary for Sheet1:')
print(model1.summary())
print('\nRegression analysis summary for Sheet1 (2):')
print(model2.summary())
```
These lines print the summary statistics of the regression analysis for both "Sheet1" and "Sheet1 (2)." The summary includes coefficients, standard errors, t-statistics, p-values, and other relevant information about the regression models.

These regression analyses aim to model the relationship between the independent variables and the dependent variable in the context of financial data. The summary provides insights into the significance and strength of these relationships.

Last updated on: 2024-02-12

Last updated on: 2024-02-12

Last updated on: 2024-02-18

Last updated on: 2024-02-19

Last updated on: 2024-02-21