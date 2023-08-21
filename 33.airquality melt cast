library("dplyr")
library("reshape2")
data("airquality")

print(summary(airquality))

melted_data <- melt(airquality, id.vars = c("Month", "Day"), variable.name = "Measurement")
cat("Melted airquality dataset: \n")
print(head(melted_data))

melted_data <- melt(airquality, id.vars = c("Month", "Day"))
cat("Melted airquality dataset with Month and Day as ID variables: \n")
print(head(melted_data))

casted_data <- dcast(melted_data, Month + Day ~ variable)
cat("Casted airquality data with Month and Day as features:\n")
print(casted_data)

melted_data <- melt(airquality, id.vars = c("Month"), measure.vars = c("Ozone", "Solar.R", "Wind", "Temp"))
averages_per_month <- dcast(melted_data, Month ~ variable, mean)
cat("Average values of Ozone, Solar.R, Wind, and Temp per month:\n")
print(averages_per_month)
