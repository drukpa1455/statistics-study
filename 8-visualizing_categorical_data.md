Study Guide 8: Visualizing Categorical Data

1. Bar Charts
   - Used to display the frequencies or proportions of different categories of a categorical variable.
   - The height of each bar represents the frequency or proportion of observations in that category.
   
   Example:
   ```R
   # Bar chart
   data <- data.frame(category = c("A", "B", "C", "D"), 
                      frequency = c(20, 35, 15, 30))
   barplot(data$frequency, names.arg = data$category, 
           main = "Bar Chart", xlab = "Category", ylab = "Frequency")
   ```

2. Pie Charts
   - Used to display the proportions of different categories of a categorical variable.
   - The size of each slice represents the proportion of observations in that category.
   - Note: Pie charts can be difficult to interpret and compare, so use them with caution.
   
   Example:
   ```R
   # Pie chart
   pie(data$frequency, labels = data$category, main = "Pie Chart")
   ```

3. Stacked and Grouped Bar Charts
   - Used to display the frequencies or proportions of different categories of a categorical variable, broken down by another categorical variable.
   - Stacked Bar Chart: The bars are divided into segments, with the height of each segment representing the frequency or proportion of observations in that combination of categories.
   - Grouped Bar Chart: The bars for each category of the second variable are placed side by side within each category of the first variable.
   
   Example:
   ```R
   # Stacked bar chart
   data2 <- data.frame(category = rep(c("A", "B", "C"), each = 2), 
                       group = rep(c("X", "Y"), times = 3),
                       value = c(10, 20, 15, 25, 5, 10))
   barplot(table(data2$category, data2$group), 
           main = "Stacked Bar Chart", xlab = "Category", ylab = "Frequency",
           col = c("lightblue", "mistyrose"), legend = rownames(table(data2$group)))
   
   # Grouped bar chart
   barplot(table(data2$category, data2$group), beside = TRUE,
           main = "Grouped Bar Chart", xlab = "Category", ylab = "Frequency",
           col = c("lightblue", "mistyrose"), legend = rownames(table(data2$group)))
   ```

4. Mosaic Plots
   - Used to visualize the relationship between two or more categorical variables.
   - The area of each rectangle represents the proportion of observations in that combination of categories.
   
   Example:
   ```R
   # Mosaic plot
   mosaicplot(~ category + group, data = data2, main = "Mosaic Plot",
              color = c("lightblue", "mistyrose"))
   ```

5. Segmented Bar Charts
   - Used to display the proportions of different categories of a categorical variable, broken down by another categorical variable.
   - Each bar represents a category of the first variable, and the segments within each bar represent the proportions of the categories of the second variable.
   
   Example:
   ```R
   # Segmented bar chart
   library(ggplot2)
   ggplot(data2, aes(x = category, fill = group)) +
     geom_bar(position = "fill") +
     labs(title = "Segmented Bar Chart", x = "Category", y = "Proportion") +
     scale_fill_manual(values = c("lightblue", "mistyrose"))
   ```

Practice Problems:

1. The following data represents the number of students enrolled in different courses:
   - Course: Math, Science, English, History
   - Enrollment: 50, 75, 60, 45
   Create a bar chart to display the enrollment in each course.

2. Using the data from problem 1, create a pie chart to display the proportion of students enrolled in each course.

3. The following data represents the number of students enrolled in different courses, broken down by gender:
   - Course: Math, Science, English, History
   - Male: 30, 45, 25, 20
   - Female: 20, 30, 35, 25
   Create a grouped bar chart to display the enrollment in each course by gender.

Solutions:

1. Bar chart:
   ```R
   course <- c("Math", "Science", "English", "History")
   enrollment <- c(50, 75, 60, 45)
   barplot(enrollment, names.arg = course, main = "Course Enrollment",
           xlab = "Course", ylab = "Enrollment")
   ```

2. Pie chart:
   ```R
   pie(enrollment, labels = course, main = "Course Enrollment Proportions")
   ```

3. Grouped bar chart:
   ```R
   course <- c("Math", "Science", "English", "History")
   male <- c(30, 45, 25, 20)
   female <- c(20, 30, 35, 25)
   enrollment <- data.frame(course = rep(course, 2), 
                            gender = rep(c("Male", "Female"), each = 4),
                            count = c(male, female))
   ggplot(enrollment, aes(x = course, y = count, fill = gender)) +
     geom_bar(stat = "identity", position = "dodge") +
     labs(title = "Course Enrollment by Gender", x = "Course", y = "Enrollment") +
     scale_fill_manual(values = c("lightblue", "mistyrose"))
   ```

This concludes the eighth study guide on visualizing categorical data. In the next and final guide, we'll cover some miscellaneous topics that are useful in various statistical analyses.