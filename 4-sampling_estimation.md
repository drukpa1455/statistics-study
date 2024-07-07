Study Guide 4: Sampling and Estimation

1. Populations and Samples
   - Population: The entire group of individuals, objects, or events of interest.
   - Sample: A subset of the population used to make inferences about the population.
   - Parameter: A numerical summary of a population (e.g., mean, proportion).
   - Statistic: A numerical summary of a sample used to estimate a population parameter.

2. Sampling Methods
   - Simple Random Sampling: Each member of the population has an equal chance of being selected.
   - Stratified Sampling: The population is divided into homogeneous subgroups (strata), and samples are taken from each stratum.
   - Cluster Sampling: The population is divided into clusters, and a sample of clusters is randomly selected.
   
   Example:
   ```R
   # Simple random sampling
   population <- 1:100
   sample(population, size = 10)
   
   # Stratified sampling
   library(sampling)
   population <- data.frame(id = 1:100, group = rep(c("A", "B"), each = 50))
   strata(population, stratanames = "group", size = c(5, 5), method = "srswor")
   
   # Cluster sampling
   population <- data.frame(id = 1:100, cluster = rep(1:10, each = 10))
   clusters <- sample(unique(population$cluster), size = 3)
   population[population$cluster %in% clusters, ]
   ```

3. Sampling Distributions
   - Sampling Distribution: The probability distribution of a statistic obtained from all possible samples of a given size from a population.
   - Sampling Distribution of the Sample Mean: The distribution of sample means from all possible samples of a given size from a population.
   
   Example:
   ```R
   # Sampling distribution of the sample mean
   population <- rnorm(10000, mean = 50, sd = 10)
   sample_means <- replicate(1000, mean(sample(population, size = 30)))
   hist(sample_means)
   ```

4. Point Estimates and Confidence Intervals
   - Point Estimate: A single value used to estimate a population parameter (e.g., sample mean, sample proportion).
   - Confidence Interval: A range of values likely to contain the true population parameter with a certain level of confidence.
   - Margin of Error: The maximum expected difference between the point estimate and the true value of the population parameter.
   
   Example:
   ```R
   # Confidence interval for a population mean
   data <- rnorm(50, mean = 10, sd = 2)
   conf_level <- 0.95
   sample_mean <- mean(data)
   sample_sd <- sd(data)
   sample_size <- length(data)
   margin_error <- qnorm((1 + conf_level) / 2) * sample_sd / sqrt(sample_size)
   lower_bound <- sample_mean - margin_error
   upper_bound <- sample_mean + margin_error
   cat("Confidence Interval:", lower_bound, "-", upper_bound)
   ```

5. Sample Size Determination
   - Determining the appropriate sample size based on the desired level of precision, confidence level, and variability in the population.
   - Larger sample sizes generally lead to more precise estimates and narrower confidence intervals.
   
   Example:
   ```R
   # Sample size determination for estimating a population mean
   margin_error <- 0.5
   conf_level <- 0.95
   population_sd <- 2
   sample_size <- ceiling((qnorm((1 + conf_level) / 2) * population_sd / margin_error)^2)
   cat("Required Sample Size:", sample_size)
   ```

Practice Problems:

1. A company wants to estimate the average age of its customers. They take a simple random sample of 100 customers and find a sample mean age of 35 with a standard deviation of 10. Construct a 95% confidence interval for the population mean age.
2. Determine the required sample size to estimate the proportion of defective items in a large production batch. The desired margin of error is 0.03, and the confidence level is 95%. Use a conservative estimate of 0.5 for the population proportion.
3. A researcher wants to estimate the average height of students in a university. They decide to use stratified sampling based on the students' year of study (freshman, sophomore, junior, senior). Determine the sample size for each stratum if the total sample size is 400 and the strata sizes are 1000, 800, 600, and 400, respectively.

Solutions:

1. 95% CI: (33.04, 36.96)
2. Required sample size: 1068
3. Sample sizes for each stratum: 143, 114, 86, 57