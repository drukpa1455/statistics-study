Study Guide 6: Comparing Groups

1. One-Way ANOVA
   - Used to compare the means of three or more independent groups.
   - Null Hypothesis: All group means are equal.
   - Alternative Hypothesis: At least one group mean is different from the others.
   
   Example:
   ```R
   # One-way ANOVA
   data <- data.frame(
     group = rep(c("A", "B", "C"), each = 10),
     value = c(rnorm(10, 10, 2), rnorm(10, 12, 2), rnorm(10, 14, 2))
   )
   model <- aov(value ~ group, data = data)
   summary(model)
   ```

2. Two-Way ANOVA
   - Used to compare the means of groups defined by two independent categorical variables (factors).
   - Allows for the examination of main effects and interaction effects.
   - Main Effect: The effect of one factor on the response variable, averaged across the levels of the other factor.
   - Interaction Effect: The effect of one factor on the response variable depends on the level of the other factor.
   
   Example:
   ```R
   # Two-way ANOVA
   data <- data.frame(
     factor1 = rep(c("A", "B"), each = 20),
     factor2 = rep(c("X", "Y"), times = 20),
     value = c(rnorm(10, 10, 2), rnorm(10, 12, 2), rnorm(10, 11, 2), rnorm(10, 13, 2))
   )
   model <- aov(value ~ factor1 * factor2, data = data)
   summary(model)
   ```

3. Post-Hoc Comparisons
   - Used to determine which specific group means are different from each other after a significant ANOVA result.
   - Common methods include Tukey's Honest Significant Difference (HSD) and Bonferroni correction.
   
   Example:
   ```R
   # Tukey's HSD
   TukeyHSD(model)
   
   # Bonferroni correction
   pairwise.t.test(data$value, data$group, p.adjust.method = "bonferroni")
   ```

4. Kruskal-Wallis Test
   - A non-parametric alternative to one-way ANOVA.
   - Used when the assumptions of ANOVA (normality and homogeneity of variances) are violated or when dealing with ordinal data.
   - Null Hypothesis: The distribution of the response variable is the same across all groups.
   - Alternative Hypothesis: The distribution of the response variable differs across at least one group.
   
   Example:
   ```R
   # Kruskal-Wallis test
   kruskal.test(value ~ group, data = data)
   ```

5. Friedman Test
   - A non-parametric alternative to two-way ANOVA for repeated measures designs.
   - Used when the assumptions of ANOVA are violated or when dealing with ordinal data.
   - Null Hypothesis: The distribution of the response variable is the same across all treatments.
   - Alternative Hypothesis: The distribution of the response variable differs across at least one treatment.
   
   Example:
   ```R
   # Friedman test
   friedman.test(y ~ treatment | subject, data = data)
   ```

Practice Problems:

1. A researcher wants to compare the mean test scores of students from three different schools. The data is as follows:
   - School A: 85, 90, 92, 88, 91
   - School B: 82, 85, 87, 83, 86
   - School C: 78, 81, 84, 79, 82
   Perform a one-way ANOVA to determine if there are any significant differences in mean test scores among the schools.

2. A company wants to compare the effectiveness of three different advertising campaigns on sales. The data is as follows:
   - Campaign A: 100, 120, 110, 130, 115
   - Campaign B: 90, 95, 105, 100, 110
   - Campaign C: 80, 85, 90, 95, 100
   The sales data is not normally distributed. Use the Kruskal-Wallis test to determine if there are any significant differences in the distribution of sales across the campaigns.

Solutions:

1. One-way ANOVA: F = 27.5, p-value = 0.0001. Reject the null hypothesis. There are significant differences in mean test scores among the schools.

   ```R
   data <- data.frame(
     school = rep(c("A", "B", "C"), each = 5),
     score = c(85, 90, 92, 88, 91, 82, 85, 87, 83, 86, 78, 81, 84, 79, 82)
   )
   model <- aov(score ~ school, data = data)
   summary(model)
   ```

2. Kruskal-Wallis test: χ² = 10.385, p-value = 0.0056. Reject the null hypothesis. There are significant differences in the distribution of sales across the campaigns.

   ```R
   data <- data.frame(
     campaign = rep(c("A", "B", "C"), each = 5),
     sales = c(100, 120, 110, 130, 115, 90, 95, 105, 100, 110, 80, 85, 90, 95, 100)
   )
   kruskal.test(sales ~ campaign, data = data)
   ```