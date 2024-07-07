Study Guide 1: Introduction to R

1. What is R?
   - R is a free, open-source programming language and environment for statistical computing and graphics.
   - It provides a wide variety of statistical and graphical techniques and is highly extensible.

2. Installing R and RStudio
   - Download R from the Comprehensive R Archive Network (CRAN): https://cran.r-project.org/
   - Install RStudio, an integrated development environment (IDE) for R: https://www.rstudio.com/products/rstudio/download/

3. Basic Syntax and Data Types
   - R is case-sensitive and uses the "<-" symbol for assignment.
   - Basic data types include numeric, integer, character, logical, and complex.
   
   Example:
   ```R
   x <- 10
   y <- "hello"
   z <- TRUE
   ```

4. Vectors, Matrices, and Arrays
   - Vectors are one-dimensional arrays that can hold elements of the same data type.
   - Matrices are two-dimensional arrays with elements of the same data type.
   - Arrays are multi-dimensional structures with elements of the same data type.
   
   Example:
   ```R
   # Create a vector
   vec <- c(1, 2, 3, 4, 5)
   
   # Create a matrix
   mat <- matrix(1:6, nrow = 2, ncol = 3)
   ```

5. Data Frames and Lists
   - Data frames are two-dimensional structures with columns that can have different data types.
   - Lists are objects that can contain elements of different data types, including vectors, matrices, and even other lists.
   
   Example:
   ```R
   # Create a data frame
   df <- data.frame(x = 1:3, y = c("a", "b", "c"))
   
   # Create a list
   lst <- list(a = 1:3, b = "hello", c = TRUE)
   ```

6. Reading in Data and Basic Operations
   - Read in data using functions like `read.csv()`, `read.table()`, and `read.delim()`.
   - Perform basic operations on vectors and matrices using arithmetic operators (+, -, *, /).
   
   Example:
   ```R
   # Read in a CSV file
   data <- read.csv("example.csv")
   
   # Perform basic operations on vectors
   vec1 <- c(1, 2, 3)
   vec2 <- c(4, 5, 6)
   vec_sum <- vec1 + vec2
   ```

7. Installing and Loading Packages
   - Install packages using the `install.packages()` function.
   - Load packages using the `library()` function.
   
   Example:
   ```R
   # Install a package
   install.packages("ggplot2")
   
   # Load a package
   library(ggplot2)
   ```

8. Seeking Help and Documentation
   - Access help for a function using `?function_name` or `help(function_name)`.
   - View a package's documentation using `help(package = "package_name")`.
   
   Example:
   ```R
   # Get help for the 'mean' function
   ?mean
   
   # View documentation for the 'ggplot2' package
   help(package = "ggplot2")
   ```

Practice Problems:

1. Create a vector containing the numbers 1 to 10.
2. Create a 3x3 matrix filled with random integers between 1 and 100.
3. Create a data frame with three columns: "name" (character), "age" (numeric), and "student" (logical).
4. Install and load the "dplyr" package.
5. Access the help documentation for the "median" function.

Solutions:

1. `vec <- 1:10`
2. `mat <- matrix(sample(1:100, 9), nrow = 3, ncol = 3)`
3. `df <- data.frame(name = c("Alice", "Bob", "Charlie"), age = c(20, 21, 19), student = c(TRUE, FALSE, TRUE))`
4. `install.packages("dplyr")`  and  `library(dplyr)`
5. `?median`

This concludes the first study guide on Introduction to R. In the next guide, we'll dive into descriptive statistics and explore various measures of central tendency and dispersion, along with techniques for visualizing univariate data.