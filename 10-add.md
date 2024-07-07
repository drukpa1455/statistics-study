Study Guide 10: Additional Topics

1. Non-Parametric Tests for Comparing Two Populations
   - Mann-Whitney U Test (Wilcoxon Rank-Sum Test): A non-parametric alternative to the independent samples t-test, used when the assumptions of normality or homogeneity of variances are violated.
   - Wilcoxon Signed-Rank Test: A non-parametric alternative to the paired samples t-test, used when the differences between paired observations are not normally distributed.
   
   Example (Mann-Whitney U Test in R):
   ```R
   x <- c(4, 6, 7, 8, 9)
   y <- c(1, 2, 3, 5, 6)
   wilcox.test(x, y, alternative = "greater")
   ```

2. Mood's Median Test
   - A non-parametric test for comparing the medians of two or more populations, without assuming that the populations have the same distribution or variances.
   
   Example (Mood's Median Test in R using the `RVAideMemoire` package):
   ```R
   install.packages("RVAideMemoire")
   library(RVAideMemoire)
   
   x <- c(4, 6, 7, 8, 9)
   y <- c(1, 2, 3, 5, 6)
   mood.medtest(list(x, y))
   ```

3. Graphical Techniques for Comparing Groups
   - Back-to-Back Stem-and-Leaf Plots: A graphical tool for comparing the distributions of two groups side by side.
   - Box Plots with Proportional Width: Displaying box plots with box widths proportional to the sample size of each group.
   - Box Plots with Notches: Adding notches to box plots to represent the confidence interval for the median, allowing for visual comparison of medians between groups.
   
   Example (Back-to-Back Stem-and-Leaf Plot in R using the `aplpack` package):
   ```R
   install.packages("aplpack")
   library(aplpack)
   
   x <- c(4, 6, 7, 8, 9)
   y <- c(1, 2, 3, 5, 6)
   stem.leaf.backback(x, y)
   ```

4. Graphical Techniques for Small Sample Sizes
   - Strip Charts with Median Lines: Plotting individual data points with a line representing the median, suitable for small sample sizes.
   
   Example (Strip Chart with Median Lines in R):
   ```R
   x <- c(4, 6, 7, 8, 9)
   y <- c(1, 2, 3, 5, 6)
   stripchart(list(x, y), method = "jitter", vertical = TRUE, pch = 19, col = c("blue", "red"))
   segments(1, median(x), 1.2, median(x), col = "blue", lwd = 2)
   segments(2, median(y), 2.2, median(y), col = "red", lwd = 2)
   ```