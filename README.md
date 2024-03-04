WINE QUALITY analysis 
R script:
# read in the winequality-red.csv dataset
wine_data <- read.csv("winequality-red.csv", sep=";", header=TRUE)
# 1. Find the number of rows and columns in the dataset
cat("Number of rows in the dataset:", nrow(wine_data), "\n")
cat("Number of columns in the dataset:", ncol(wine_data), "\n")
# 2. Calculate the mean and median values for each column
for (col_name in names(wine_data)) {
cat("Column Name:", col_name, "\n")
cat("Mean Value:", mean(wine_data[[col_name]]), "\n")
cat("Median Value:", median(wine_data[[col_name]]), "\n\n")
}
# 3. Calculate the standard deviation for each column
for (col_name in names(wine_data)) {
cat("Column Name:", col_name, "\n")
cat("Standard Deviation:", sd(wine_data[[col_name]]), "\n\n")
}
# 4. Calculate the minimum and maximum values for each column
for (col_name in names(wine_data)) {
cat("Column Name:", col_name, "\n")
cat("Minimum Value:", min(wine_data[[col_name]]), "\n")
cat("Maximum Value:", max(wine_data[[col_name]]), "\n\n")
}
# 5. Create a scatter plot of fixed acidity vs. pH
plot(wine_data$fixed.acidity, wine_data$pH, xlab="Fixed Acidity", ylab="pH", main="Fixed
Acidity vs. pH")
# 6. Create a histogram of alcohol levels
hist(wine_data$alcohol, breaks=20, xlab="Alcohol Level", ylab="Frequency", main="Histogram
of Alcohol Levels")
# 7. Identify missing values in the dataset
cat("Number of missing values in the dataset:", sum(is.na(wine_data)), "\n")
# 8. Create a boxplot of the quality ratings
boxplot(wine_data$quality, xlab="Quality Rating", ylab="Score", main="Boxplot of Quality
Ratings")
# 9. Calculate the correlation between citric acid and pH
cor(wine_data$citric.acid, wine_data$pH)
# 10. Fit a linear regression model to predict the wine quality based on physicochemical
properties
model <- lm(quality ~ ., data=wine_data)
summary(model)


Reference:
 C. Cortez. "Predicting Wine Quality with R." (Blog post) October 20, 2014. Available at:
http://cortezaproject.github.io/blog/predicting-wine-quality-with-r/.
 P. Manrique. "Data Analysis of Wine Quality using R." (Blog post) August 3, 2017.
Available at: https://www.datacamp.com/community/tutorials/data-analysis-of-winequality-
using-r.
 M. Moberg. "Predicting Wine Quality with Machine Learning in R." (Blog post) April 20,
2019. Available at: https://towardsdatascience.com/predicting-wine-quality-withmachine-
learning-in-r-af4c4e4cafe6.
 Wickham, H., & Grolemund, G. (2017). R for data science: Import, tidy, transform,
visualize, and model data. O'Reilly Media. https://r4ds.had.co.nz/
 Xie, Y. (2018). knitr: A general-purpose package for dynamic report generation in R.
https://yihui.org/knitr/
