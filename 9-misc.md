Study Guide 9: Miscellaneous Topics

1. Transforming Variables
   - Sometimes, the relationship between variables may not be linear, or the assumptions of a statistical model may not be met. In such cases, transforming the variables can help.
   - Common transformations include:
     - Logarithmic transformation: Used to stabilize the variance or to linearize an exponential relationship.
     - Square root transformation: Used to stabilize the variance when it is proportional to the mean.
     - Reciprocal transformation: Used to linearize a hyperbolic relationship.
   
   Example:
   ```R
   # Logarithmic transformation
   log_x <- log(x)
   
   # Square root transformation
   sqrt_x <- sqrt(x)
   
   # Reciprocal transformation
   recip_x <- 1 / x
   ```

2. Weighted Means and Proportions
   - In some situations, observations may have different levels of importance or influence. In such cases, weighted means or proportions can be used.
   - Weighted Mean: Each observation is multiplied by its corresponding weight, and the sum of the products is divided by the sum of the weights.
   - Weighted Proportion: The sum of the products of each category's value (0 or 1) and its corresponding weight is divided by the sum of the weights.
   
   Example:
   ```R
   # Weighted mean
   values <- c(2, 4, 6, 8)
   weights <- c(0.1, 0.2, 0.3, 0.4)
   weighted_mean <- sum(values * weights) / sum(weights)
   
   # Weighted proportion
   categories <- c(0, 1, 1, 0, 1)
   weights <- c(0.2, 0.3, 0.1, 0.25, 0.15)
   weighted_prop <- sum(categories * weights) / sum(weights)
   ```

3. Ranks and Percentiles
   - Ranks: The position of an observation in the ordered list of all observations.
   - Percentiles: The value below which a given percentage of observations fall.
   - These measures are useful for comparing observations across different datasets or for creating non-parametric tests.
   
   Example:
   ```R
   # Ranks
   ranks <- rank(x)
   
   # Percentiles
   quantile(x, probs = c(0.25, 0.5, 0.75))
   ```

4. Simulating Data from Different Distributions
   - Simulating data is useful for testing statistical methods, assessing the performance of models, or creating examples for teaching purposes.
   - R provides functions to generate random numbers from various probability distributions.
   
   Example:
   ```R
   # Normal distribution
   rnorm(n, mean = 0, sd = 1)
   
   # Binomial distribution
   rbinom(n, size = 10, prob = 0.5)
   
   # Poisson distribution
   rpois(n, lambda = 5)
   
   # Uniform distribution
   runif(n, min = 0, max = 1)
   
   # Exponential distribution
   rexp(n, rate = 1)
   ```

Practice Problems:

1. The following data represents the weights (in kg) and heights (in cm) of 5 individuals:
   - Weights: 60, 70, 80, 90, 100
   - Heights: 150, 160, 170, 180, 190
   Calculate the weighted mean of the heights, using the weights as the corresponding weights.

2. Generate a sample of 1000 random numbers from a normal distribution with a mean of 50 and a standard deviation of 10. Calculate the 25th, 50th, and 75th percentiles of the generated data.

Solutions:

1. Weighted mean of heights:
   ```R
   weights <- c(60, 70, 80, 90, 100)
   heights <- c(150, 160, 170, 180, 190)
   weighted_mean_height <- sum(heights * weights) / sum(weights)
   ```
   The weighted mean of the heights is 172 cm.

2. Generating data and calculating percentiles:
   ```R
   data <- rnorm(1000, mean = 50, sd = 10)
   quantile(data, probs = c(0.25, 0.5, 0.75))
   ```
   The 25th, 50th, and 75th percentiles of the generated data will vary each time the code is run due to the random nature of the generated data.