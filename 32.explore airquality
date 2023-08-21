data("airquality")

mean_tem <- sum(airquality$Temp)/length(airquality$Temp)
cat("\nMean of Temperature : ", mean_tem, "\n")

cat("\nFirst five rows of airquality dataset: \n")
print(head(airquality, n = 5))

selected_columns <- airquality[, !(names(airquality) %in% c("Temp", "Wind"))]
cat("\nColumns from airquality dataset except Temp and Wind: \n")
print(selected_columns)

coldest_day_row <- airquality[which.min(airquality$Temp), ]
cat("\nInformation about the coldest day: \n")
print(coldest_day_row)

days_greater_than_17mph <- sum(airquality$Wind > 17)
cat("\nNumber of days with wind speed greater than 17 mph:", days_greater_than_17mph, "\n")
