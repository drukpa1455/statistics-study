Study Guide 5: Hypothesis Testing

1. Null and Alternative Hypotheses
   - Null Hypothesis (H₀): A statement of no effect or no difference, assumed to be true unless evidence suggests otherwise.
   - Alternative Hypothesis (H₁ or Hₐ): A statement that contradicts the null hypothesis, representing the researcher's claim or the effect of interest.
   
   Example:
   ```R
   # Null hypothesis: The population mean is equal to 100
   # Alternative hypothesis: The population mean is not equal to 100
   ```

2. One and Two-Tailed Tests
   - One-Tailed Test: The alternative hypothesis specifies a direction (greater than or less than the null value).
   - Two-Tailed Test: The alternative hypothesis does not specify a direction (not equal to the null value).
   
   Example:
   ```R
   # One-tailed test: H₀: μ ≤ 100, H₁: μ > 100
   # Two-tailed test: H₀: μ = 100, H₁: μ ≠ 100
   ```

3. Test Statistics, P-Values, and Statistical Significance
   - Test Statistic: A value calculated from the sample data used to make a decision about the null hypothesis.
   - P-Value: The probability of obtaining a test statistic as extreme as, or more extreme than, the observed value, assuming the null hypothesis is true.
   - Statistical Significance: When the p-value is less than the chosen significance level (α), typically 0.05, the result is considered statistically significant, and the null hypothesis is rejected.
   
   Example:
   ```R
   # Calculate the test statistic and p-value for a one-sample t-test
   data <- rnorm(50, mean = 102, sd = 10)
   t_test <- t.test(data, mu = 100)
   t_test$statistic
   t_test$p.value
   ```

4. Type I and II Errors, Power
   - Type I Error (α): Rejecting the null hypothesis when it is actually true.
   - Type II Error (β): Failing to reject the null hypothesis when it is actually false.
   - Power (1 - β): The probability of correctly rejecting the null hypothesis when the alternative hypothesis is true.
   
   Example:
   ```R
   # Calculate the power of a one-sample t-test
   power.t.test(n = 50, delta = 2, sd = 10, type = "one.sample", alternative = "two.sided")
   ```

5. T-Tests
   - One-Sample t-Test: Tests whether the population mean is equal to a specified value.
   - Independent Two-Sample t-Test: Tests whether the means of two independent populations are equal.
   - Paired t-Test: Tests whether the mean difference between paired observations is equal to a specified value (often 0).
   
   Example:
   ```R
   # One-sample t-test
   t.test(data, mu = 100)
   
   # Independent two-sample t-test
   t.test(data1, data2, var.equal = TRUE)
   
   # Paired t-test
   t.test(before, after, paired = TRUE)
   ```

6. Other Hypothesis Tests
   - Chi-Square Test for Independence: Tests whether two categorical variables are independent.
   - One-Sample Proportion Test: Tests whether the population proportion is equal to a specified value.
   - Two-Sample Proportion Test: Tests whether the proportions of two populations are equal.
   - F-Test for Equality of Variances: Tests whether the variances of two populations are equal.
   
   Example:
   ```R
   # Chi-square test for independence
   chisq.test(contingency_table)
   
   # One-sample proportion test
   prop.test(x = 30, n = 100, p = 0.25)
   
   # Two-sample proportion test
   prop.test(x = c(30, 40), n = c(100, 120))
   
   # F-test for equality of variances
   var.test(data1, data2)
   ```

Practice Problems:

1. A company claims that the average weight of their product is 500 grams. A random sample of 25 products has a mean weight of 490 grams with a standard deviation of 30 grams. Test the company's claim at a 5% significance level.
2. A researcher wants to compare the mean test scores of two independent groups of students. Group A has 30 students with a mean score of 85 and a standard deviation of 10. Group B has 35 students with a mean score of 80 and a standard deviation of 12. Test whether there is a significant difference between the two groups at a 5% significance level.
3. A survey was conducted to determine if there is an association between gender and preference for a particular brand of smartphone. The results are shown in the contingency table below. Test for independence at a 5% significance level.

   |        | Brand A | Brand B |
   |--------|---------|---------|
   | Male   | 150     | 200     |
   | Female | 200     | 150     |

Solutions:

1. One-sample t-test: t = -1.67, p-value = 0.1082. Fail to reject the null hypothesis. There is not enough evidence to conclude that the average weight is different from 500 grams.
2. Independent two-sample t-test: t = 1.85, p-value = 0.0687. Fail to reject the null hypothesis. There is not enough evidence to conclude that there is a significant difference between the two groups.
3. Chi-square test for independence: χ² = 12.5, p-value = 0.0004. Reject the null hypothesis. There is a significant association between gender and brand preference.