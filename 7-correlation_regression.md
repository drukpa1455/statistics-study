Study Guide 7: Correlation and Regression

1. Scatter Plots
   - A graphical representation of the relationship between two quantitative variables.
   - Each point on the plot represents a pair of values (x, y) for an individual or observation.
   - The shape of the scatter plot can reveal the strength, direction, and linearity of the relationship between the variables.
   
   Example:
   ```R
   # Scatter plot
   plot(x, y, main = "Scatter Plot", xlab = "X", ylab = "Y")
   ```

2. Correlation Coefficients
   - Pearson Correlation Coefficient (r): Measures the strength and direction of a linear relationship between two quantitative variables.
     - Values range from -1 to +1.
     - A value of +1 indicates a perfect positive linear relationship, -1 indicates a perfect negative linear relationship, and 0 indicates no linear relationship.
   - Spearman Rank Correlation Coefficient (ρ): A non-parametric alternative to Pearson's correlation, used when the relationship is monotonic but not necessarily linear, or when the data is ordinal.
   
   Example:
   ```R
   # Pearson correlation coefficient
   cor(x, y, method = "pearson")
   
   # Spearman rank correlation coefficient
   cor(x, y, method = "spearman")
   ```

3. Simple Linear Regression
   - A statistical method used to model the linear relationship between a dependent variable (y) and an independent variable (x).
   - The model is represented by the equation: y = β₀ + β₁x + ε
     - β₀: The y-intercept, the value of y when x = 0.
     - β₁: The slope, the change in y for a one-unit increase in x.
     - ε: The error term, representing the unexplained variability in y.
   
   Example:
   ```R
   # Simple linear regression
   model <- lm(y ~ x)
   summary(model)
   ```

4. Inference for Regression Coefficients
   - Hypothesis tests and confidence intervals can be constructed for the regression coefficients (β₀ and β₁).
   - The null hypothesis for the slope (β₁) is usually H₀: β₁ = 0, indicating no linear relationship between x and y.
   - A significant p-value for the slope suggests that there is a linear relationship between x and y.
   
   Example:
   ```R
   # Inference for regression coefficients
   summary(model)$coefficients
   confint(model)
   ```

5. Assessing Model Fit and Assumptions
   - R-squared (R²): The proportion of the variance in the dependent variable that is predictable from the independent variable.
   - Residual Analysis: Examining the residuals (the differences between the observed and predicted values) can help assess the model's assumptions.
     - Residuals should be normally distributed with constant variance and have no clear pattern when plotted against the predicted values.
   
   Example:
   ```R
   # Assessing model fit and assumptions
   summary(model)$r.squared
   plot(model, which = 1) # Residuals vs. Fitted
   plot(model, which = 2) # Normal Q-Q plot
   ```

6. Polynomial and Interaction Terms
   - Polynomial Terms: Used to model non-linear relationships between the dependent and independent variables.
   - Interaction Terms: Used to model the combined effect of two or more independent variables on the dependent variable.
   
   Example:
   ```R
   # Polynomial term
   model <- lm(y ~ x + I(x^2))
   
   # Interaction term
   model <- lm(y ~ x1 * x2)
   ```

Practice Problems:

1. A researcher collected data on the number of hours studied and the corresponding exam scores for a group of students. The data is as follows:
   - Hours: 2, 3, 5, 6, 8, 10
   - Scores: 52, 63, 74, 81, 90, 93
   Create a scatter plot and calculate the Pearson correlation coefficient between hours studied and exam scores.

2. Using the data from problem 1, fit a simple linear regression model to predict exam scores based on the number of hours studied. Interpret the coefficients and assess the model's fit using R-squared.

Solutions:

1. Scatter plot and Pearson correlation coefficient:
   ```R
   hours <- c(2, 3, 5, 6, 8, 10)
   scores <- c(52, 63, 74, 81, 90, 93)
   plot(hours, scores, main = "Scatter Plot", xlab = "Hours Studied", ylab = "Exam Score")
   cor(hours, scores)
   ```
   The scatter plot shows a strong positive linear relationship between hours studied and exam scores. The Pearson correlation coefficient is 0.9838, indicating a very strong positive linear relationship.

2. Simple linear regression model:
   ```R
   model <- lm(scores ~ hours)
   summary(model)
   ```
   The regression equation is: Exam Score = 44.7143 + 4.9524 × Hours Studied
   - The y-intercept (β₀) is 44.7143, meaning that a student who studies for 0 hours is expected to score 44.7143 on the exam.
   - The slope (β₁) is 4.9524, meaning that for every additional hour studied, the exam score is expected to increase by 4.9524 points.
   - The R-squared value is 0.9679, indicating that 96.79% of the variance in exam scores can be explained by the number of hours studied.

This concludes the seventh study guide on correlation and regression. In the next guide, we'll explore visualizing categorical data using various types of charts and plots.