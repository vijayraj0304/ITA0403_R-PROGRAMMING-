library("reshape2")
library("dplyr")
library("modeest")

data("ChickWeight")

ordered_data <- ChickWeight[order(ChickWeight$weight), ]
last_6_records <- tail(ordered_data, 6)
cat("Last 6 records from the ordered data frame:\n")
print(last_6_records)

melted_data <- melt(ChickWeight, id.vars = c("Chick", "Time", "Diet"))
cat("Melted ChickWeight data:\n")
print(head(melted_data))

mean_weight_by_diet <- dcast(ChickWeight, Diet ~ ., value.var = "weight", fun.aggregate = mean)
cat("Mean weight values grouped by Diet:\n")
print(mean_weight_by_diet)


mode_func <- function(x) {
  tbl <- table(x)
  mode_value <- as.numeric(names(tbl[tbl == max(tbl)]))
  return(mode_value)
}

# Calculate the mode of weight grouped by Diet using dplyr and pivot_wider
mode_weight_by_diet <- ChickWeight %>%
  group_by(Diet) %>%
  summarize(ModeWeight = mode_func(weight)) %>%
  pivot_wider(names_from = Diet, values_from = ModeWeight)

# Print the mode weight values grouped by Diet
print("Mode weight values grouped by Diet:")
print(mode_weight_by_diet)
