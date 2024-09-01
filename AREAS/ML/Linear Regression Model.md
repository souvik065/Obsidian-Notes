
# What is linear regression?

Linear regression analysis is used to predict the value of a variable based on the value of another variable. The variable you want to predict is called the dependent variable. The variable you are using to predict the other variable's value is called the independent variable.


# Make sure your data meets linear-regression assumptions

Before you attempt to perform linear regression, you need to make sure that your data can be analyzed using this procedure. Your data must pass through certain required assumptions.

Here’s how you can check for these assumptions:

1. The variables should be measured at a continuous level. Examples of continuous variables are time, sales, weight and test scores. 
2. Use a scatterplot to find out quickly if there is a linear relationship between those two variables.
3. The observations should be independent of each other (that is, there should be no dependency).
4. Your data should have no significant outliers. 
5. Check for homoscedasticity — a statistical concept in which the variances along the best-fit linear-regression line remain similar all through that line.
6. The residuals (errors) of the best-fit regression line follow normal distribution.


**A Linear Regression model is a statistical technique used to model the relationship between a dependent variable (often called the target or output) and one or more independent variables (also known as predictors or features). The goal of linear regression is to find the best-fitting linear relationship (line) between the input variables and the output variable.**

### Key Concepts:

1. **Linear Equation**:
    
    - For simple linear regression (one independent variable), the model can be expressed as:
        
        **y=β0+β1x+ϵy = \beta_0 + \beta_1x + \epsilony=β0​+β1​x+ϵ**
        
        
        Where:
        
        - yyy is the dependent variable (output)
        - xxx is the independent variable (input)
        - β0\beta_0β0​ is the intercept
        - β1\beta_1β1​ is the slope of the line
        - ϵ\epsilonϵ is the error term (residual)
    - For multiple linear regression (more than one independent variable), the model is extended to:
        
        y=β0+β1x1+β2x2+⋯+βnxn+ϵy = \beta_0 + \beta_1x_1 + \beta_2x_2 + \dots + \beta_nx_n + \epsilony=β0​+β1​x1​+β2​x2​+⋯+βn​xn​+ϵ
2. **Objective**:
    
    - The objective of linear regression is to minimize the sum of squared differences between the observed values and the values predicted by the linear model. This process is called **Ordinary Least Squares (OLS)**.
3. **Assumptions**:
    
    - **Linearity**: The relationship between the dependent and independent variables is linear.
    - **Independence**: The observations are independent of each other.
    - **Homoscedasticity**: The variance of residuals is the same for all values of the independent variables.
    - **Normality**: The residuals (errors) are normally distributed.
4. **Interpretation**:
    
    - The coefficients β1,β2,…\beta_1, \beta_2, \dotsβ1​,β2​,… represent the change in the dependent variable for a one-unit change in the corresponding independent variable, assuming all other variables are held constant.
5. **Applications**:
    
    - Predicting values (e.g., house prices based on features like size, location).
    - Understanding relationships between variables.
    - Making inferences about the significance of predictors.
6. **Implementation**:
    
    - Linear regression can be implemented using various libraries in programming languages like Python (e.g., `scikit-learn`, `statsmodels`) or R.


**Resource :**
[Linear Regression By IBM](https://www.ibm.com/topics/linear-regression#:~:text=IBM-,What%20is%20linear%20regression%3F,is%20called%20the%20independent%20variable.)
[ChatGPT](https://chatgpt.com/c/9fb9348b-e457-40cb-a360-28215205752a)
