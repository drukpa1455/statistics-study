Study Guide 2: Descriptive Statistics

1. Measures of Central Tendency
   - Mean: The arithmetic average of a set of numbers.
   - Median: The middle value when the data is sorted in ascending or descending order.
   - Mode: The most frequently occurring value in the dataset.
   
   Example:
   ```R
   data <- c(10, 12, 15, 18, 20, 20, 25)
   
   # Calculate mean
   mean(data)
   
   # Calculate median
   median(data)
   
   # Calculate mode
   mode <- function(x) {
     ux <- unique(x)
     ux[which.max(tabulate(match(x, ux)))]
   }
   mode(data)
   ```

2. Measures of Dispersion
   - Range: The difference between the maximum and minimum values.
   - Interquartile Range (IQR): The difference between the 75th and 25th percentiles.
   - Variance: The average of the squared deviations from the mean.
   - Standard Deviation: The square root of the variance.
   - Median Absolute Deviation (MAD): A robust measure of dispersion, less sensitive to outliers than standard deviation.
   
   Example:
   ```R
   # Calculate range
   max(data) - min(data)
   
   # Calculate IQR
   IQR(data)
   
   # Calculate variance
   var(data)
   
   # Calculate standard deviation
   sd(data)
   
   # Calculate MAD
   mad(data)
   ```

3. Coefficient of Variation
   - A standardized measure of dispersion, expressed as the ratio of the standard deviation to the mean.
   - Useful for comparing the dispersion of variables with different units or means.
   
   Example:
   ```R
   # Calculate coefficient of variation
   cv <- sd(data) / mean(data)
   cv
   ```

4. Quantiles and Box Plots
   - Quantiles divide the dataset into equal-sized subsets.
   - Common quantiles include quartiles (25th, 50th, 75th percentiles) and percentiles (1st to 99th).
   - Box plots (box-and-whisker plots) visually represent the distribution of data based on five summary statistics: minimum, first quartile, median, third quartile, and maximum.
   
   Example:
   ```R
   # Calculate quantiles
   quantile(data)
   
   # Create a box plot
   boxplot(data)
   ```

5. Visualizing Univariate Data
   - Histograms: Display the distribution of a continuous variable by dividing the data into bins and representing the frequency or count of observations in each bin.
   - Density Plots: A smoothed version of a histogram, showing the probability density function of the variable.
   - QQ Plots: Compare the distribution of a variable to a theoretical distribution (e.g., normal distribution) by plotting the quantiles of the data against the quantiles of the theoretical distribution.
   - Stem-and-Leaf Plots: A textual representation of the distribution of a small dataset, showing individual values and their frequencies.
   
   Example:
   ```R
   # Create a histogram
   hist(data)
   
   # Create a density plot
   plot(density(data))
   
   # Create a QQ plot
   qqnorm(data)
   qqline(data)
   
   # Create a stem-and-leaf plot
   stem(data)
   ```

6. Dealing with Outliers and Missing Data
   - Outliers are data points that significantly deviate from the rest of the dataset. They can be identified using box plots or z-scores.
   - Missing data can be represented as NA in R. Functions like `is.na()`, `na.omit()`, and `complete.cases()` help identify and handle missing data.
   
   Example:
   ```R
   # Identify outliers using z-scores
   z_scores <- (data - mean(data)) / sd(data)
   outliers <- data[abs(z_scores) > 3]
   
   # Handle missing data
   data_missing <- c(10, 12, NA, 18, 20, NA, 25)
   complete_data <- na.omit(data_missing)
   ```

Practice Problems:

1. Calculate the mean, median, and mode of the following dataset: 
   ```R
   data <- c(12, 15, 18, 20, 22, 22, 25, 28, 30)
   ```
2. Calculate the range, IQR, variance, standard deviation, and MAD of the dataset from problem 1.
3. Create a histogram and a density plot of the dataset from problem 1.
4. Create a QQ plot of the dataset from problem 1 to check for normality.
5. Identify any outliers in the following dataset using z-scores:
   ```R
   data_outliers <- c(10, 12, 15, 18, 20, 22, 50)
   ```

Solutions:

1. Mean: 21.33, Median: 22, Mode: 22
2. Range: 18, IQR: 10, Variance: 34.75, Standard Deviation: 5.90, MAD: 5.93
3. `hist(data)` and `plot(density(data))`
4. `qqnorm(data); qqline(data)`
5. Outliers: 50 (z-score > 3)