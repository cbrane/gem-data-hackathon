# GEM Data Hackathon - Updated Data Dictionary

This document describes the changes made to the original GEM dataset during processing, including variable renaming, recoding, and data cleaning steps.

## Changes Made to the Dataset

The original dataset was processed using R code that performed the following key operations:

1. All numeric codes were converted to human-readable labels (e.g., converting '1' to 'male' for gender)
2. "Refused" and "Don't know" responses were recoded as missing values (NA)
3. Variables were renamed to be more descriptive and consistent
4. Data types were properly set (e.g., numeric values for counts, categorical values for classifications)

## Current Dataset Structure

The processed dataset has 36 variables and contains data from over 15,800 observations collected between 2015-2021.

### Primary Variables

| Original Variable | New Variable Name | Description | Values |
|-------------------|-------------------|-------------|--------|
| WEIGHT_L | weight | Observation weight for statistical analysis | Numeric |
| TEA | new_entrepreneur | Involved in Total early-stage Entrepreneurial Activity | "Yes", "No" |
| ESTBBUSO | established_entrepreneur | Owner-Manager of an Established Business (older than 3.5 years) | "Yes", "No" |

### Demographic Variables

| Original Variable | New Variable Name | Description | Values |
|-------------------|-------------------|-------------|--------|
| yrsurv | year | Year of the survey | 2015 through 2021 |
| gender | gender | Gender of respondent | "male", "female" |
| age9c | age_range | Age range of respondent | "18-24", "25-34", "35-44", "45-54", "55-64", "65-74" |
| hhsize | household_size | Household members count including respondent | Integer (1-44) |
| ushhinc | household_income | Household income bracket | "Under $15,000" through "Over $200,000" |
| usreduc | education | Highest level of education completed | "None/Less than High School" through "Degree Graduate (Master's or PhD)" |
| race | race | Primary race | "White", "Black", "Hispanic", "Other" |
| region | region | US regions based on FEMA regions | "New England", "New York-New Jersey", "Mid-Atlantic", "Southeast", "Great Lakes", "South", "Central Midwest", "Mountain and Plains", "Pacific Southwest", "Pacific Northwest" |

### Entrepreneurial Attitudes and Perceptions

| Original Variable | New Variable Name | Description | Values |
|-------------------|-------------------|-------------|--------|
| knowent | knows_entrepreneur | Knows someone who started a business in past 2 years | "Yes", "No" |
| opport | local_opportunity | Good opportunities for starting a business in next 6 months | "Yes", "No" |
| suskill | entrepreneurial_skill | Has knowledge, skill, experience required for new business | "Yes", "No" |
| fearfail | fear_of_failure | Would fear of failure prevent starting a business | "Yes", "No" |
| nbgoodc | wants_entrepreneurship | Most people consider starting a business a desirable career | "Yes", "No" |
| nbstatus | respects_entrepreneurship | Business success brings high status and respect | "Yes", "No" |
| nbmedia | follows_entrepreneurship | Often sees stories about successful new businesses in media | "Yes", "No" |
| futsup | future_startup | Expects to start a new business within three years | "Yes", "No" |

### Business Characteristics

| Original Variable | New Variable Name | Description | Values |
|-------------------|-------------------|-------------|--------|
| TEAOWNER | new_entrepreneur_owners | Number of owners of early-stage business | Integer |
| EB_OWNER | established_entrepreneur_owners | Number of owners of established business | Integer |
| TEAJOBNOW | new_entrepreneur_employees | Current number of employees (early-stage business) | Integer |
| EB_JOBNOW | established_entrepreneur_employees | Current number of employees (established business) | Integer |
| TEAJOBGR | new_entrepreneur_new_jobs | Expected job growth in 5 years (early-stage business) | Integer |
| EB_JOBGR | established_entrepreneur_new_jobs | Expected job growth in 5 years (established business) | Integer |
| TEANEWPR | new_entrepreneur_innovation | Customers consider product/service new (early-stage) | "Yes", "No" |
| TEANEWPROD | new_entrepreneur_local_innovation | Level of innovation of product/service | "No, not new product or service", "New to people in the area where you live", "New to people in your country", "New to the world" |
| TEAEXP4C | new_entrepreneur_external_sales | Percentage of sales from customers outside country (early-stage) | "More than 75%", "25 to 75%", "Under 25%", "None" |
| EB_EXP4C | established_entrepreneur_external_sales | Percentage of sales from customers outside country (established) | "More than 75%", "25 to 75%", "Under 25%", "None" |
| TEAISIC4_1D | new_entrepreneur_industry | Industry of early-stage business | 12 industry categories (e.g., "AGRICULTURE,FORESTRY,FISHING") |
| EB_ISIC4_1D | established_entrepreneur_industry | Industry of established business | 12 industry categories (e.g., "AGRICULTURE,FORESTRY,FISHING") |

### Business Discontinuation and Investment

| Original Variable | New Variable Name | Description | Values |
|-------------------|-------------------|-------------|--------|
| discent | discontinued_business | Discontinued a business in past 12 months | "Yes", "No" |
| exbuscon | discontinued_business_continuation | Did business continue after respondent quit | "Yes", "No", "Business continued but activities changed" |
| busang | is_investor | Provided funds for someone else's business in past 3 years | "Yes", "No" |
| bafund | investment | Amount provided to business startups in past 3 years | "Have not provided funds" |
| barel | investment_relationship | Relationship with person who received investment | "Close family member...", "Some other relative...", "A work colleague", "A friend or neighbor", "A stranger with a good business idea", "Other" |

## Key Data Processing Notes

1. **Missing Values**: "Refused" and "Don't know" responses have been recoded as missing values (NA) for all variables
2. **Categorical Variables**: All categorical variables have been properly labeled and converted to factor types
3. **Numeric Variables**: Count variables (like number of employees) have been maintained as integers
4. **Data Cleaning**: The dataset has been cleaned and organized for analysis, with consistent naming conventions
5. **Variable Ordering**: The 'weight', 'new_entrepreneur', and 'established_entrepreneur' variables have been placed at the beginning of the dataset for easy access

This data dictionary reflects the final, processed dataset that has been renamed from the original numeric codes to more descriptive labels, making it more accessible for analysis.