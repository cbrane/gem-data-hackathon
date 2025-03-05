```r
rm(list = ls())
gc()
cat("\014")

library(dplyr)
library(tidyr)
# library(skimr)
# library(naniar)

setwd("C:/Users/aozsu1/OneDrive/3. docs & data/2025 GEM Data Hackathon/")
data <-  read.csv("2025Hackathon.csv")


# skim(data)
# vis_miss(data)


# Create a function to map all variables to their labels
recode_data_labels <- function(data) {
  # Create a copy of the original data
  data_labeled <- data
  
  # recode gender
  data_labeled$gender <- factor(data$gender,
                                levels = c(1, 2),
                                labels = c("male", "female"))
  
  # recode age range
  data_labeled$age9c <- factor(data$age9c,
                               levels = c(2, 3, 4, 5, 6, 7),
                               labels = c("18-24", "25-34", "35-44", "45-54", "55-64", "65-74"))
  
  # recode household size (special case with numeric values to preserve)
  data_labeled$hhsize <- case_when(
    data$hhsize == -2 ~ "Refused",
    data$hhsize == -1 ~ "Don't know",
    data$hhsize >= 1 & data$hhsize <= 44 ~ as.character(data$hhsize),
    TRUE ~ NA_character_
  )
  
  # recode income brackets
  data_labeled$ushhinc <- factor(data$ushhinc,
                                 levels = c(1, 2, 3, 4, 5, 6, 7, 8, 9),
                                 labels = c("Under $15,000", 
                                            "$15,000 to under $25,000",
                                            "$25,000 to under $35,000",
                                            "$35,000 to under $50,000",
                                            "$50,000 to under $75,000",
                                            "$75,000 to under $100,000",
                                            "$100,000 to under $150,000",
                                            "$150,000 to under $200,000",
                                            "Over $200,000"))
  
  # recode education level
  data_labeled$usreduc <- factor(data$usreduc,
                                 levels = c(1, 2, 3, 4, 5, 6),
                                 labels = c("None/Less than High School",
                                            "Some High School",
                                            "Completed High School",
                                            "Some College/University",
                                            "Completed College/University",
                                            "Degree Graduate (Master's or PhD)"))
  
  # recode race
  data_labeled$race <- factor(data$race,
                              levels = c(-2, -1, 1, 2, 3, 4),
                              labels = c("Refused", "Don't know", "White", "Black", "Hispanic", "Other"))
  
  # recode region
  data_labeled$region <- factor(data$region,
                                levels = c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10),
                                labels = c("New England", 
                                           "New York-New Jersey", 
                                           "Mid-Atlantic", 
                                           "Southeast", 
                                           "Great Lakes", 
                                           "South", 
                                           "Central Midwest", 
                                           "Mountain and Plains", 
                                           "Pacific Southwest", 
                                           "Pacific Northwest"))
  
  # recode variables with standard Yes/No patterns
  yes_no_vars <- c("knowent", "opport", "suskill", "fearfail", "nbgoodc", "nbstatus", 
                   "nbmedia", "TEA", "ESTBBUSO", "futsup", "discent", "busang")
  
  for (var in yes_no_vars) {
    if (var %in% names(data)) {
      data_labeled[[var]] <- factor(data[[var]],
                                    levels = c(-2, -1, 0, 1),
                                    labels = c("Refused", "Don't know", "No", "Yes"))
    }
  }
  
  # recode TEANEWPR
  data_labeled$TEANEWPR <- factor(data$TEANEWPR,
                                  levels = c(-2, -1, 1, 2),
                                  labels = c("Refused", "Don't know", "Yes", "No"))
  
  # recode TEANEWPROD
  data_labeled$TEANEWPROD <- factor(data$TEANEWPROD,
                                    levels = c(-2, -1, 1, 2, 3, 4),
                                    labels = c("Refused", 
                                               "Don't know", 
                                               "No, not new product or service",
                                               "New to people in the area where you live",
                                               "New to people in your country",
                                               "New to the world"))
  
  # recode TEAEXP4C
  data_labeled$TEAEXP4C <- factor(data$TEAEXP4C,
                                  levels = c(-2, -1, 1, 2, 3, 4),
                                  labels = c("Refused", 
                                             "Don't know", 
                                             "More than 75%",
                                             "25 to 75%",
                                             "Under 25%",
                                             "None"))
  
  # recode EB_EXP4C
  data_labeled$EB_EXP4C <- factor(data$EB_EXP4C,
                                  levels = c(-2, -1, 5, 6, 7, 8),
                                  labels = c("Refused", 
                                             "Don't know", 
                                             "More than 75%",
                                             "25 to 75%",
                                             "Under 25%",
                                             "None"))
  
  # recode industry classifications (both TEA and EB use same coding)
  industry_labels <- c("NOT CLASSIFIED/MISSING",
                       "AGRICULTURE,FORESTRY,FISHING",
                       "MINING,CONSTRUCTION",
                       "MANUFACTURING",
                       "UTILISATION, TRANSPORT, STORAGE",
                       "WHOLESALE TRADE",
                       "RETAIL TRADE, HOTELS & RESTAURANTS",
                       "INFORMATION AND COMMUNICATION",
                       "FINANCIAL INTERMEDIATION, REAL ESTATE",
                       "PROFESSIONAL SERVICES",
                       "ADMINISTRATIVE SERVICES",
                       "GOVERNMENT, HEALTH, EDUCATION, SOCIAL SERVICES",
                       "PERSONAL/CONSUMER SERVICE ACTIVITIES")
  
  data_labeled$TEAISIC4_1D <- factor(data$TEAISIC4_1D,
                                     levels = c(-2, 1:12),
                                     labels = industry_labels)
  
  data_labeled$EB_ISIC4_1D <- factor(data$EB_ISIC4_1D,
                                     levels = c(-2, 1:12),
                                     labels = industry_labels)
  
  # recode exbuscon
  data_labeled$exbuscon <- factor(data$exbuscon,
                                  levels = c(-2, -1, 1, 2, 3),
                                  labels = c("Refused", 
                                             "Don't know", 
                                             "Yes",
                                             "No",
                                             "Business continued but activities changed"))
  
  # recode bafund
  data_labeled$bafund <- factor(data$bafund,
                                levels = c(-3, -2, -1),
                                labels = c("Have not provided funds", "Refused", "Don't know"))
  
  # recode barel
  data_labeled$barel <- factor(data$barel,
                               levels = c(-2, -1, 1, 2, 3, 4, 5, 6),
                               labels = c("Refused", 
                                          "Don't know", 
                                          "Close family member, such as a spouse, brother, child, parent, or grandchild",
                                          "Some other relative, kin, or blood relation",
                                          "A work colleague",
                                          "A friend or neighbor, or",
                                          "A stranger with a good business idea",
                                          "Other"))
  
  # Variables that don't need recoding:
  # yrsurv (actual year values)
  # TEAOWNER, EB_OWNER, TEAJOBNOW, EB_JOBNOW, TEAJOBGR, EB_JOBGR (numeric values to maintain)
  # WEIGHT_L (observation weights)
  
  return(data_labeled)
}

# Apply the function to the dataset
data <- recode_data_labels(data)


levels(data$knowent)[levels(data$knowent) %in% c("Refused", "Don't know")] <- NA
levels(data$opport)[levels(data$opport) %in% c("Refused", "Don't know")] <- NA
levels(data$suskill)[levels(data$suskill) %in% c("Refused", "Don't know")] <- NA
levels(data$fearfail)[levels(data$fearfail) %in% c("Refused", "Don't know")] <- NA
levels(data$nbgoodc)[levels(data$nbgoodc) %in% c("Refused", "Don't know")] <- NA
levels(data$nbstatus)[levels(data$nbstatus) %in% c("Refused", "Don't know")] <- NA
levels(data$nbmedia)[levels(data$nbmedia) %in% c("Refused", "Don't know")] <- NA
levels(data$futsup)[levels(data$futsup) %in% c("Refused", "Don't know")] <- NA
levels(data$discent)[levels(data$discent) %in% c("Refused", "Don't know")] <- NA
levels(data$exbuscon)[levels(data$exbuscon) %in% c("Refused", "Don't know")] <- NA
levels(data$busang)[levels(data$busang) %in% c("Refused", "Don't know")] <- NA
levels(data$barel)[levels(data$barel) %in% c("Refused", "Don't know")] <- NA
levels(data$ESTBBUSO)[levels(data$ESTBBUSO) %in% c("Refused", "Don't know")] <- NA
levels(data$TEAEXP4C)[levels(data$TEAEXP4C) %in% c("Refused", "Don't know")] <- NA
levels(data$EB_EXP4C)[levels(data$EB_EXP4C) %in% c("Refused", "Don't know")] <- NA
levels(data$TEANEWPR)[levels(data$TEANEWPR) %in% c("Refused", "Don't know")] <- NA
levels(data$TEANEWPROD)[levels(data$TEANEWPROD) %in% c("Refused", "Don't know")] <- NA
levels(data$TEA)[levels(data$TEA) %in% c("Refused", "Don't know")] <- NA
levels(data$race)[levels(data$race) %in% c("Refused", "Don't know")] <- NA




# Typecast
data$hhsize <- as.integer(data$hhsize)
data$TEAJOBGR <- as.integer(data$TEAJOBGR)
data$EB_JOBGR <- as.integer(data$EB_JOBGR)
data$EB_OWNER <- as.integer(data$EB_OWNER)
data$TEAOWNER <- as.integer(data$TEAOWNER)
data$EB_JOBNOW <- as.integer(data$EB_JOBNOW)
data$TEAJOBNOW <- as.integer(data$TEAJOBNOW)
data$yrsurv <- as.factor(data$yrsurv)










# Reorder data
data <- data %>% select(WEIGHT_L, TEA, ESTBBUSO, everything())

data <- data %>% rename(
  year = yrsurv,
  gender = gender,
  age_range = age9c,
  household_size = hhsize,
  household_income = ushhinc,
  education = usreduc,
  race = race,
  region = region,
  knows_entrepreneur = knowent,
  local_opportunity = opport,
  entrepreneurial_skill = suskill,
  fear_of_failure = fearfail,
  wants_entrepreneurship = nbgoodc,
  respects_entrepreneurship = nbstatus,
  follows_entrepreneurship = nbmedia,
  new_entrepreneur = TEA,
  established_entrepreneur = ESTBBUSO,
  new_entrepreneur_owners = TEAOWNER,
  established_entrepreneur_owners = EB_OWNER,
  new_entrepreneur_employees = TEAJOBNOW,
  established_entrepreneur_employees = EB_JOBNOW,
  new_entrepreneur_new_jobs = TEAJOBGR,
  established_entrepreneur_new_jobs = EB_JOBGR,
  new_entrepreneur_innovation = TEANEWPR,
  new_entrepreneur_local_innovation = TEANEWPROD,
  new_entrepreneur_external_sales = TEAEXP4C,
  established_entrepreneur_external_sales = EB_EXP4C,
  new_entrepreneur_industry = TEAISIC4_1D,
  established_entrepreneur_industry = EB_ISIC4_1D,
  future_startup = futsup,
  discontinued_business = discent,
  discontinued_business_continuation = exbuscon,
  is_investor = busang,
  investment = bafund,
  investment_relationship = barel,
  weight = WEIGHT_L
)

# # Remove mostly empty question data
# data <- data %>%
#   select(-c(discontinued_business_continuation, investment, new_entrepreneur_local_innovation, investment_relationship, household_income, education, new_entrepreneur_industry, established_entrepreneur_industry, new_entrepreneur_new_jobs, established_entrepreneur_new_jobs, new_entrepreneur_owners, established_entrepreneur_owners, new_entrepreneur_external_sales, established_entrepreneur_external_sales, new_entrepreneur_innovation, new_entrepreneur_employees, established_entrepreneur_employees))

# skim(data)
# vis_miss(data)

write.csv(data, file = "Hackathon_GEM_Data.csv", row.names = FALSE)

```