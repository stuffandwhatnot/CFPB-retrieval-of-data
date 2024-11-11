# CFPB-retrieval-of-data

install.packages("RSocrata")
library(RSocrata)

# CFPB Socrata API endpoint
url <- "https://data.consumerfinance.gov/resource/s6ew-h6mp.csv"

# Import data directly from the API
cfpb_data <- read.socrata(url)
head(cfpb_data)


# Check the structure of the data
str(cfpb_data)

# Get a summary of the data
summary(cfpb_data)

# Basic data cleaning if necessary
library(dplyr)
cfpb_data <- cfpb_data %>%
  filter(!is.na(complaint_id)) # Remove rows with missing complaint IDs
