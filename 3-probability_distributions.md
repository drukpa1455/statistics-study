Study Guide 3: Probability and Probability Distributions

1. Basic Probability Concepts
   - Sample Space: The set of all possible outcomes of an experiment or random process.
   - Event: A subset of the sample space.
   - Probability: A measure of the likelihood that an event will occur, ranging from 0 to 1.
   - Axioms of Probability: 
     - P(A) ≥ 0 for any event A
     - P(S) = 1, where S is the sample space
     - For mutually exclusive events A and B, P(A ∪ B) = P(A) + P(B)

2. Conditional Probability and Independence
   - Conditional Probability: The probability of an event A occurring given that another event B has occurred, denoted as P(A|B).
   - Independence: Two events A and B are independent if P(A ∩ B) = P(A) × P(B).
   
   Example:
   ```R
   # Conditional probability
   P_A <- 0.6
   P_B_given_A <- 0.4
   P_A_and_B <- P_A * P_B_given_A
   
   # Independence
   P_C <- 0.5
   P_D <- 0.7
   if (P_C * P_D == 0.35) {
     print("C and D are independent")
   } else {
     print("C and D are not independent")
   }
   ```

3. Discrete and Continuous Random Variables
   - Random Variable: A function that assigns a numerical value to each outcome in a sample space.
   - Discrete Random Variable: A random variable that can only take on a countable number of distinct values.
   - Continuous Random Variable: A random variable that can take on any value within a specified range or interval.

4. Expectation, Variance, and Standard Deviation
   - Expectation (Mean): The average value of a random variable, denoted as E(X).
   - Variance: A measure of the dispersion of a random variable around its mean, denoted as Var(X) or σ^2.
   - Standard Deviation: The square root of the variance, denoted as SD(X) or σ.
   
   Example:
   ```R
   # Expectation and variance of a discrete random variable
   X <- c(1, 2, 3, 4, 5)
   P <- c(0.1, 0.2, 0.4, 0.2, 0.1)
   
   E_X <- sum(X * P)
   Var_X <- sum((X - E_X)^2 * P)
   SD_X <- sqrt(Var_X)
   ```

5. Common Probability Distributions
   - Binomial Distribution: Models the number of successes in a fixed number of independent trials with a constant probability of success.
   - Poisson Distribution: Models the number of events occurring in a fixed interval of time or space, given a known average rate of occurrence.
   - Uniform Distribution: Models a situation where all outcomes within a specified range are equally likely.
   - Exponential Distribution: Models the time between events in a Poisson process.
   - Normal Distribution: A continuous probability distribution that is symmetric and bell-shaped, characterized by its mean and standard deviation.
   
   Example:
   ```R
   # Binomial distribution
   dbinom(3, size = 10, prob = 0.4)
   
   # Poisson distribution
   dpois(2, lambda = 3)
   
   # Uniform distribution
   dunif(0.5, min = 0, max = 1)
   
   # Exponential distribution
   dexp(2, rate = 0.5)
   
   # Normal distribution
   dnorm(0, mean = 0, sd = 1)
   ```

6. Central Limit Theorem and Its Applications
   - Central Limit Theorem: States that the sum or average of a large number of independent and identically distributed random variables will be approximately normally distributed, regardless of the distribution of the original variables.
   - Applications: Sampling distributions, confidence intervals, and hypothesis testing.
   
   Example:
   ```R
   # Central Limit Theorem
   sample_means <- replicate(1000, mean(rnorm(30)))
   hist(sample_means)
   ```

Practice Problems:

1. You roll a fair six-sided die. What is the probability of getting an even number?
2. Given P(A) = 0.4 and P(B|A) = 0.6, find P(A ∩ B).
3. The number of customers arriving at a store follows a Poisson distribution with a mean of 5 per hour. What is the probability that exactly 3 customers arrive in an hour?
4. The time between arrivals at a bus stop follows an exponential distribution with a mean of 10 minutes. What is the probability that the time between arrivals is less than 5 minutes?
5. Use the Central Limit Theorem to create a histogram of 1000 sample means, each based on 50 observations from a uniform distribution between 0 and 1.

Solutions:

1. P(Even) = 0.5
2. P(A ∩ B) = P(A) × P(B|A) = 0.4 × 0.6 = 0.24
3. P(X = 3) = dpois(3, lambda = 5) = 0.1404
4. P(X < 5) = pexp(5, rate = 1/10) = 0.3935
5. 
   ```R
   sample_means <- replicate(1000, mean(runif(50, min = 0, max = 1)))
   hist(sample_means)
   ```

This concludes the third study guide on probability and probability distributions. In the next guide, we'll explore sampling and estimation, covering key concepts such as populations, samples, sampling distributions, and confidence intervals.