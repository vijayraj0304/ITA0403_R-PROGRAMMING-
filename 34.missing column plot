# Load the airquality dataset
data("airquality")

# Calculate the threshold for dropping or imputing
threshold <- nrow(airquality) * 0.1

# Loop through the missing columns
for (col in colnames(airquality)[colSums(is.na(airquality)) > 0]) {
  if (sum(is.na(airquality[[col]])) < threshold) {
    airquality <- airquality[complete.cases(airquality), ]
  } else {
    airquality[[col]][is.na(airquality[[col]])] <- mean(airquality[[col]], na.rm = TRUE)
  }
}

# Print the modified dataset
cat("Modified airquality dataset: \n")
print(head(airquality))

model <- lm(Ozone ~ Solar.R, data = airquality)
print(summary(model))

plot(airquality$Solar.R, airquality$Ozone, main = "Scatter Plot of Ozone vs Solar.R",
     xlab = "Solar.R", ylab = "Ozone")
abline(model, col = "red")
