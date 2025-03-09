# GEM Data Hackathon: Comprehensive Analysis of American Entrepreneurs

## Hackathon Challenge

> "Offer a comprehensive analysis of the diverse characteristics of American entrepreneurs, including aspects such as their backgrounds, co-founder dynamics, industry preferences, impact on employment, market selection strategies, ambitions, and factors influencing their decision to discontinue their ventures. Utilize all available variables from the Global Entrepreneurship Monitor (GEM) dataset and feel free to enhance your analysis by integrating it with additional relevant datasets."

## The Butler Institute GEM Data Hackathon 2025

**The Deliverable:**

Create 3 slides that represent your findings.
- Slide 1 and 2: Your results
- Slide 3: Explanation of your methods

Email the deliverable to butlerinstitute@babson.edu by 9 p.m. ET on Sunday, March 9, 2025. Send details of your team members (if you have any) – names and emails with your submission.

**Important Dates:**
- The info session: February 24, 2025, 5 p.m. ET (virtual)
- Submit your deliverable (3 slides) by Sunday, March 9, 9 p.m. ET
- Presentation and Award Ceremony: Tuesday, April 8

**Rules for Forming Teams:**
- Each team should have no more than four members.
- All team members must be Babson students.
- Teams can have a mix of undergraduate and graduate students or can comprise only undergraduate or graduate students.

**No Software Restrictions:**
Teams are allowed to use any software package they want to clean, analyze, and visualize data. They can also use any software package to create the infographic or write their statement.

## Dataset Overview

The dataset for this hackathon is a compiled version of the United States of America Samples of the Global Entrepreneurship Monitor (GEM) Dataset, from 2015 through 2021 (seven years).

The dataset is collected annually from a nationally representative random sample of individuals, aged 18 to 64. The individuals vary from one year to another, but (much of) the questionnaire stays the same. With seven years of data, you have access to data of over 15,800 observations.

### Key Definitions

**Entrepreneur Definition:**
GEM defines an entrepreneur as someone who is currently trying to start a business or has started a business in the last 3.5 years and is paying wages. There is a binary variable in the dataset, called TEA, that captures such people. When TEA = 1, the respondent is an entrepreneur according to the GEM definition.

**Established Business Owner-Manager Definition:**
GEM defines an Established Business Owner-Manager as someone who owns and manages a business that was started more than 3.5 years ago. The binary variable ESTBBUSO captures such people.

**Weights:**
Each observation has weights in the data. You should always consider the weight of observations when you do any statistical analysis, such as calculating the averages, etc. The weight variable is WEIGHT_L.

## Updated Data Dictionary

The original dataset was processed using R code that performed the following key operations:
1. All numeric codes were converted to human-readable labels (e.g., converting '1' to 'male' for gender)
2. "Refused" and "Don't know" responses were recoded as missing values (NA)
3. Variables were renamed to be more descriptive and consistent
4. Data types were properly set (e.g., numeric values for counts, categorical values for classifications)

### Current Dataset Structure

The processed dataset has 36 variables and contains data from over 15,800 observations collected between 2015-2021.

#### Primary Variables

| Original Variable | New Variable Name | Description | Values |
|-------------------|-------------------|-------------|--------|
| WEIGHT_L | weight | Observation weight for statistical analysis | Numeric |
| TEA | new_entrepreneur | Involved in Total early-stage Entrepreneurial Activity | "Yes", "No" |
| ESTBBUSO | established_entrepreneur | Owner-Manager of an Established Business (older than 3.5 years) | "Yes", "No" |

#### Demographic Variables

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

#### Entrepreneurial Attitudes and Perceptions

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

#### Business Characteristics

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
| TEAISIC4_1D | new_entrepreneur_industry | Industry of early-stage business | 12 industry categories |
| EB_ISIC4_1D | established_entrepreneur_industry | Industry of established business | 12 industry categories |

#### Business Discontinuation and Investment

| Original Variable | New Variable Name | Description | Values |
|-------------------|-------------------|-------------|--------|
| discent | discontinued_business | Discontinued a business in past 12 months | "Yes", "No" |
| exbuscon | discontinued_business_continuation | Did business continue after respondent quit | "Yes", "No", "Business continued but activities changed" |
| busang | is_investor | Provided funds for someone else's business in past 3 years | "Yes", "No" |
| bafund | investment | Amount provided to business startups in past 3 years | "Have not provided funds" |
| barel | investment_relationship | Relationship with person who received investment | Multiple categories |

## Analysis Approach

Our analysis is structured to directly address all seven key aspects mentioned in the challenge: (1) backgrounds, (2) co-founder dynamics, (3) industry preferences, (4) impact on employment, (5) market selection strategies, (6) ambitions, and (7) factors influencing business discontinuation.

### 1. Entrepreneur Backgrounds & Demographic Analysis

This section directly addresses the "backgrounds" component of the challenge.

#### Objectives
- Create comprehensive entrepreneur personas based on demographic patterns
- Analyze intersectionality of demographic factors (gender, race, age, education, income)
- Compare profiles between new and established entrepreneurs
- Identify key background factors that predict entrepreneurial activity

#### Methods
1. **Clustering Analysis**
   - Apply k-means clustering on demographic variables (age, gender, education, income, region)
   - Identify 3-5 distinct entrepreneur personas
   - Compare cluster characteristics between new and established entrepreneurs

2. **Intersectionality Analysis**
   - Create cross-tabulations of entrepreneurship rates by multiple demographic factors
   - Calculate weighted percentages for combinations (e.g., Black women aged 25-34)
   - Identify underrepresented and overrepresented groups

3. **Entrepreneurial Journey Visualization**
   - Track progression from aspiring entrepreneur to established business owner
   - Create Sankey diagrams showing transitions between entrepreneurial stages
   - Identify demographic patterns in entrepreneurial progression

### 2. Co-founder Dynamics & Team Composition Analysis

This section directly addresses the "co-founder dynamics" component of the challenge.

#### Objectives
- Understand team composition patterns across different entrepreneur types
- Identify relationship between team size and business outcomes
- Compare solo vs. team ventures' performance
- Determine how co-founding relationships influence business success and strategy

#### Methods
1. **Team Size Distribution Analysis**
   - Calculate weighted distributions of team sizes for new and established entrepreneurs
   - Create histograms/bar charts of owner counts
   - Compare team size patterns across industries and demographics

2. **Performance Comparison**
   - Compare job creation metrics between solo and team ventures
   - Analyze market reach (local vs. international) by team size
   - Explore innovation levels by team composition

3. **Longevity Analysis**
   - Compare team sizes between new and established businesses
   - Calculate conversion rates from new to established business by team size
   - Identify optimal team size ranges for business sustainability

### 3. Business Discontinuation Factors Analysis

This section directly addresses the "factors influencing their decision to discontinue their ventures" component of the challenge.

#### Objectives
- Identify key factors leading to business discontinuation
- Understand regional and industry patterns in business failure
- Develop predictive insights for entrepreneurial sustainability
- Analyze how entrepreneur characteristics influence discontinuation decisions

#### Methods
1. **Predictive Modeling**
   - Develop decision tree or random forest models to predict business discontinuation
   - Identify key variables that contribute to business sustainability
   - Calculate feature importance to prioritize risk factors

2. **Comparative Analysis**
   - Compare demographic profiles of entrepreneurs who discontinued vs. continued businesses
   - Analyze industry-specific discontinuation rates
   - Examine regional variations in business sustainability

3. **Temporal Analysis**
   - Track discontinuation rates over the 2015-2021 period
   - Analyze pre/post-COVID effects on business discontinuation
   - Identify changing patterns in reasons for discontinuation

### 4. Market Selection Strategies & Growth Analysis

This section directly addresses the "market selection strategies" component of the challenge.

#### Objectives
- Understand how entrepreneurs select and expand into markets
- Identify relationship between market reach and business growth
- Compare local vs. national vs. international strategies
- Analyze how market selection relates to entrepreneur ambitions

#### Methods
1. **Market Reach Analysis**
   - Analyze distribution of external sales percentages across industries
   - Compare market reach between new and established entrepreneurs
   - Identify regional patterns in international market penetration

2. **Growth Correlation Analysis**
   - Calculate correlation between market reach and job creation metrics
   - Compare growth trajectories based on market selection strategies
   - Identify optimal market strategies for different industries

3. **Innovation Connection**
   - Analyze relationship between product/service innovation and market reach
   - Compare innovation levels across local, national, and global entrepreneurs
   - Develop typology of market-innovation entrepreneur profiles

### 5. Industry Preferences & Employment Impact Analysis

This section directly addresses the "industry preferences" and "impact on employment" components of the challenge.

#### Objectives
- Analyze industry distribution across entrepreneur demographics
- Measure employment impact across different industries and entrepreneur types
- Identify high-growth industries for entrepreneurship
- Assess job creation potential by industry and entrepreneur characteristics

#### Methods
1. **Industry Distribution Analysis**
   - Calculate weighted industry distributions for entrepreneurs
   - Compare industry preferences across demographic groups
   - Analyze industry trends over the 2015-2021 period

2. **Employment Impact Assessment**
   - Measure current and projected job creation by industry
   - Compare job creation metrics between new and established entrepreneurs
   - Identify entrepreneur profiles with highest employment impact

3. **Growth Sector Identification**
   - Analyze industry growth rates based on entrepreneur entry/exit
   - Compare entrepreneur activity to national industry growth trends
   - Identify emerging sectors with high entrepreneurial activity

### 6. Entrepreneur Ambitions Analysis

This section directly addresses the "ambitions" component of the challenge.

#### Objectives
- Understand future entrepreneurial intentions and ambitions
- Identify factors associated with growth-oriented mindsets
- Compare ambition levels across entrepreneur demographics and business types

#### Methods
1. **Ambition Indicators Analysis**
   - Analyze variables related to future business intentions (`future_startup`)
   - Measure growth ambitions through projected job creation
   - Examine innovation plans and market expansion intentions

2. **Ambition Predictors Modeling**
   - Identify demographic and experiential factors associated with high ambitions
   - Develop predictive models for entrepreneurial growth orientation
   - Compare ambition levels between demographic groups

3. **Ambition-Outcome Relationship**
   - Track relationship between stated ambitions and actual business outcomes
   - Compare ambition levels between new and established entrepreneurs
   - Analyze how ambitions translate to business performance

### 7. Temporal and Regional Entrepreneurship Analysis

This section addresses the comparative analysis of entrepreneurial activity across time and regions, with industry-specific insights.

#### Objectives
- Track entrepreneurial activity trends over time (2015-2021)
- Compare new vs. established business patterns across regions
- Identify regional industry specialization and gaps
- Analyze the evolution of entrepreneurship before and after major events (e.g., COVID-19)

#### Methods
1. **Temporal Trend Analysis**
   - Track new and established entrepreneurship rates by year
   - Compare entrepreneurial activity growth/decline across different regions
   - Identify seasonal and cyclical patterns in business formation
   - Examine COVID-19 impact on entrepreneurial activity by industry

2. **Regional Comparison**
   - Calculate regional entrepreneurship density (entrepreneurs per capita)
   - Compare regional industry preferences and specialization
   - Identify high-growth entrepreneurial hubs
   - Analyze the relationship between regional economic factors and entrepreneurship

3. **Industry Evolution**
   - Track industry distribution changes over time
   - Identify emerging and declining industries by region
   - Compare industry preferences between new and established entrepreneurs
   - Analyze industry resilience during economic shifts

## Key Findings and Insights

### 1. Entrepreneur Backgrounds & Demographic Profiles

Based on our analysis of entrepreneur backgrounds and demographic characteristics:

#### 1. Overall Entrepreneurship Rates

- **New Entrepreneurs**: 12.3% of respondents overall
- **Established Entrepreneurs**: 7.5% of respondents overall
- A significant gender gap exists in entrepreneurship rates

#### 2. Demographic Patterns in Entrepreneurship

##### Gender
- Males have significantly higher rates of both new entrepreneurship (15.2%) and established entrepreneurship (9.3%) 
- Females show lower rates (9.4% new, 5.8% established)
- The gender gap exists across all demographic categories

##### Age
- Middle-aged adults (35-44) have the highest new entrepreneurship rates (16.8%)
- Young adults (25-34) show strong new entrepreneurship rates (14.1%)
- Established entrepreneurship increases with age, peaking at ages 45-54 (12.6%)
- Youngest adults (18-24) have very low established entrepreneurship rates (1.3%)

##### Race
- Black Americans have high new entrepreneurship rates (15.1%) but lower established rates (4.8%)
- Hispanic Americans show the lowest new entrepreneurship rates (9.9%) and established rates (3.5%)
- White Americans have moderate new entrepreneurship rates (12.0%) but the highest established rates (9.0%)
- "Other" racial groups have high new entrepreneurship rates (14.7%) and moderate established rates (6.4%)

##### Education
- Completed college/university graduates have high new entrepreneurship rates (14.1%)
- Advanced degree holders (Master's/PhD) show strong entrepreneurship rates (13.1% new, 12.6% established)
- Those with some college education also show high new entrepreneurship rates (13.5%)
- Interestingly, those with no/less than high school education have high established entrepreneurship rates (14.1%)
- People with some high school education have the lowest new entrepreneurship rates (4.2%)

##### Regional Variations
- Mountain and Plains region has the highest new entrepreneurship rate (20.8%)
- Southeast (14.6%) and Pacific Southwest (12.8%) follow with high rates
- New York-New Jersey has the lowest new entrepreneurship rate (8.3%)
- Central Midwest has the highest established entrepreneurship rate (11.0%)

##### Income
- Higher income brackets generally show higher entrepreneurship rates
- Highest new entrepreneurship rates in the over $200,000 income bracket (20.0%)
- Lowest new entrepreneurship rates in the $15,000 to $25,000 bracket (6.3%)
- Established entrepreneurship follows a similar pattern, peaking at 22.1% for the highest income bracket

#### 3. Intersectionality Analysis

##### Gender and Race
- Male entrepreneurs from "Other" racial groups have the highest new entrepreneurship rate (19.3%)
- Black males (15.0%) and White males (15.1%) show similarly high rates
- Hispanic males have lower rates (13.1%)
- Black females have higher entrepreneurship rates (15.2%) than White females (8.8%)
- Hispanic females have the lowest rates overall (6.6%)

##### Gender and Age
- Young male adults (25-34) show the highest new entrepreneurship rate (20.2%)
- Middle-aged males (35-44) follow closely (18.4%)
- Middle-aged females (35-44) have the highest rate among women (15.1%)
- Older adults (55-64) show the lowest rates for both genders

##### Race and Education
- Black Americans with advanced degrees have very high new entrepreneurship rates (20.8%)
- "Other" racial groups with completed college education show high rates (22.8%)
- Hispanic Americans with completed high school have notably low rates (4.8%)

#### 4. Entrepreneur Personas

Two main entrepreneur personas emerged from the clustering analysis:

- **Persona 1 (62.6% of entrepreneurs)**: 
  - Predominantly male
  - Young adults (25-34)
  - White
  - College educated
  - Located in the Southeast region

- **Persona 2 (37.4% of entrepreneurs)**:
  - Predominantly female
  - Middle-aged (35-44)
  - White
  - College educated
  - Located in the Southeast region

#### 5. New vs. Established Entrepreneur Comparison

##### Age Distribution
- New entrepreneurs are significantly younger
- 68% of new entrepreneurs are under 45, compared to 39% of established entrepreneurs
- 45-54 age group shows the biggest difference: 21% of new entrepreneurs vs. 37% of established

##### Gender Distribution
- Gender distribution is nearly identical between new and established entrepreneurs
- Males make up approximately 62% of both groups
- Females make up approximately 38% of both groups

##### Race Distribution
- New entrepreneurs are more racially diverse
- White entrepreneurs make up 65% of new entrepreneurs vs. 79% of established entrepreneurs
- Black entrepreneurs comprise 15% of new entrepreneurs but only 8% of established
- Similar patterns for Hispanic and Other racial groups

##### Education Distribution
- New entrepreneurs have higher representation of college graduates (37% vs. 33%)
- Established entrepreneurs have higher representation of advanced degree holders (29% vs. 18%)
- Some college entrepreneurs are more prevalent among new entrepreneurs (24% vs. 16%)

#### 6. Key Predictors of Entrepreneurial Activity

Psychological and social factors strongly influence entrepreneurship rates:

- **Having entrepreneurial skills**: Strongest predictor, increasing likelihood 6.2x
- **Knowing other entrepreneurs**: Second strongest predictor, increasing likelihood 3.8x
- **Seeing local opportunities**: Increases entrepreneurship likelihood 2.1x
- **Fear of failure**: Decreases entrepreneurship likelihood by 38% (0.62x relative likelihood)

These findings provide valuable insights into the diverse profiles of American entrepreneurs and the key factors that drive entrepreneurial activity across different demographic groups.

### 2. Co-founder Dynamics & Team Composition

Based on our analysis of co-founder dynamics and team composition in the GEM data, here are the key findings:

#### 1. Team Size Distribution

- **Solo Founders Dominate**: The majority of entrepreneurs operate as solo founders
  - 57.7% of new entrepreneurs are solo founders
  - 65.3% of established entrepreneurs are solo founders
- **Team Composition**:
  - Duo teams (2 founders) make up 21.0% of new and 20.3% of established ventures
  - Small teams (3-5 founders) represent 18.0% of new but only 10.0% of established ventures
  - Large teams (6+ founders) are rare: 3.4% of new and 4.4% of established ventures
- **Raw Numbers**: Average team size is 1.91 for new entrepreneurs and 7.34 for established entrepreneurs (though the established number is skewed by outliers)

#### 2. Industry Patterns in Team Formation

- **Industries with Largest Teams** (new entrepreneurs):
  - Information and Communication (2.35 owners on average)
  - Financial Intermediation and Real Estate (2.23)
  - Agriculture, Forestry, Fishing (2.00)
- **Industries with Smallest Teams**:
  - Wholesale Trade (1.72)
  - Mining, Construction (1.74)
  - Professional Services (1.76)
- **Team Size Distribution by Industry**:
  - Information and Communication has the lowest solo founder rate (49.8%) and highest small team rate (26.6%)
  - Professional Services has the highest solo founder rate (64.3%)
  - Government, Health, Education, Social Services also shows high solo founder rates (63.6%)

#### 3. Team Size and Business Performance

##### Employment
- **Current Employees by Team Size**:
  - Large teams (6+ owners) employ significantly more people (154.0 on average)
  - Duo teams employ more people (23.6) than solo ventures (17.1) or small teams (15.2)
  - Median values show a steady increase with team size (solo: 1, duo: 2, small team: 3, large team: 6)

##### Projected Job Growth
- **5-Year Job Projections**:
  - Large teams project the highest job growth (119.2 new jobs on average)
  - Small teams (3-5 owners) project substantial growth (35.6 new jobs)
  - Solo ventures project more job growth (14.6) than duo teams (7.7)
  - Median projections increase with team size (solo: 2, duo: 4, small team: 6, large team: 7)

##### External Market Reach
- **External Sales Percentage**:
  - Small teams (3-5 owners) have the highest rate of moderate external sales (17.1% with 25-75% external sales)
  - Large teams (6+) have the highest rate of substantial external sales (13.3% with more than 75% external sales)
  - Duo teams have the highest rate of primarily local sales (87.2% with under 25% external sales)

#### 4. Team Size and Innovation

- The innovation data showed that 100% of ventures in all team size categories reported having innovative products/services
- This is likely due to the specific subsample that answered the innovation question (only 626 entrepreneurs)
- The data doesn't show meaningful differences in innovation rates across team sizes

#### 5. Demographic Patterns in Team Formation

##### Gender
- **Team Size by Gender**:
  - Male entrepreneurs have larger teams on average (1.99 owners) than female entrepreneurs (1.72)
  - Female entrepreneurs are more likely to be solo founders (62.3% vs. 53.1% for males)
  - Males are twice as likely to have small teams of 3-5 people (22.3% vs. 10.7% for females)

##### Race
- **Team Size by Race**:
  - Hispanic entrepreneurs have the largest teams on average (2.05 owners)
  - Black entrepreneurs have the smallest teams (1.62 owners)
  - Hispanic entrepreneurs have the lowest rate of solo ventures (43.9%)
  - "Other" racial groups have the highest rate of small teams (30.7%)
  - Black and "Other" entrepreneurs have no representation in large teams in this sample

##### Education
- **Team Size by Education Level**:
  - Entrepreneurs with some college/university education have the largest teams (2.18 owners)
  - Those with less than high school education have the smallest teams (1.36 owners)
  - Advanced degree holders (Masters/PhD) have above-average team sizes (1.94 owners)

#### 6. Business Longevity and Team Size

- **Established/New Entrepreneur Ratio** (proxy for survival rate):
  - Large teams (6+ owners) have the highest ratio (1.32), suggesting better survival rates
  - Solo ventures also show good survival (ratio of 1.13)
  - Duo teams have a slightly lower ratio (0.96)
  - Small teams (3-5 owners) have the lowest ratio (0.55), suggesting either:
    - Lower survival rates for these teams, or
    - A recent trend toward larger founding teams
  - This U-shaped pattern suggests both very small and very large teams may be more sustainable

#### 7. Solo vs. Team Ventures Comparison

- **Key Performance Differences**:
  - Team ventures have 84% more current employees (31.6 vs. 17.1)
  - Team ventures project 95% more job growth (28.4 vs. 14.6 new jobs)
  - Market reach is nearly identical for both types:
    - Solo: 82.6% local (<25% external sales) vs. Team: 81.6% local
    - Solo: 17.4% significant external sales vs. Team: 18.4% significant external sales

These findings reveal significant differences in team composition across industries and demographics, as well as the important impact of team size on business performance metrics. The data suggests that while solo ventures remain dominant, team-based approaches show advantages in employment and growth metrics.

#### Limitations
- Data for certain metrics is limited (e.g., innovation data was available for only 626 entrepreneurs)
- The survey captures a snapshot in time and doesn't track individual businesses over their lifecycle
- Team size alone doesn't capture the quality of co-founder relationships or skill complementarity

### 3. Business Discontinuation Factors

Based on our analysis of business discontinuation factors in the GEM data, here are the key findings:

#### 1. Overview & General Statistics

- **Overall Discontinuation Rate**: 4.64% of respondents reported discontinuing a business
- **Business Continuation**: Of discontinued businesses:
  - 58.5% ceased operations completely
  - 39.5% continued in some other form
  - 2.0% continued but with changed activities

#### 2. Demographic Patterns in Business Discontinuation

##### Gender
- Males have higher discontinuation rates (5.3%) than females (4.0%)
- The gender gap persisted across all years and widened during the pandemic

##### Age
- Middle-aged entrepreneurs (35-44) show highest discontinuation rates (5.2%)
- Young adults (25-34) follow closely (4.8%)
- Older (55-64) and middle-aged (45-54) entrepreneurs have lower rates (4.6% and 4.2%)

##### Race
- Minority groups show higher discontinuation rates:
  - "Other" races: 5.1%
  - Black entrepreneurs: 5.0%
  - Hispanic entrepreneurs: 4.7%
  - White entrepreneurs: 4.2%

##### Education
- Surprisingly, very low education (none/less than high school) shows highest discontinuation rate (5.1%)
- Advanced degree holders (Masters/PhD) have second highest rate (4.1%)
- High school graduates and those with some high school have lowest rates (3.2% and 2.7%)

##### Regional Variations
- Highest in Pacific Northwest (5.8%) and Pacific Southwest (5.3%)
- Southeast region follows at 5.0%
- Lowest in New England (2.0%)

#### 3. Industry Patterns

- Highest discontinuation rates in:
  - Retail, hotels & restaurants (10.9%)
  - Utilization, transport & storage (10.3%)
  - Mining & construction (9.2%)
  
- Lowest discontinuation rates in:
  - Professional services (4.4%)
  - Financial intermediation & real estate (4.6%)
  - Wholesale trade (5.7%)

#### 4. Entrepreneurial Attitudes & Experience

- **Knowledge of other entrepreneurs**: Those who know entrepreneurs have significantly higher discontinuation rates (6.8%) compared to those who don't (3.0%)

- **Entrepreneurial skill**: Those who believe they have entrepreneurial skills show higher discontinuation rates (6.6%) compared to those who don't (2.1%)

- **Fear of failure**: Counter-intuitively, those without fear of failure have slightly higher discontinuation rates (5.1%) compared to those with fear of failure (4.1%)

#### 5. Temporal Trends & COVID-19 Impact

- Discontinuation rates increased steadily from 2016 (3.4%) to 2021 (6.4%)
- A dramatic increase occurred during the COVID-19 pandemic:
  - 2019: 5.1%
  - 2020: 6.1% (pandemic year)
  - 2021: 6.4% (continued impact)
  
- Gender differences widened during the pandemic:
  - Males saw a sharper increase in discontinuation rates (5.5% in 2019 to 7.4% in 2021)
  - Females showed more modest increases (4.8% in 2019 to 5.4% in 2021)

#### 6. Predictive Modeling Results

- **Most important predictors of business discontinuation** (by variable):
  1. Region (25.9% importance)
  2. Education (18.1%)
  3. Age (15.3%)
  4. Race (9.0%)
  5. Fear of failure (7.0%)
  6. Gender (7.0%)

- **Top specific predictive factors**:
  1. Being in the 25-34 age range
  2. Having some college/university education
  3. Having completed college/university
  4. Being in the Southeast region
  5. Having an advanced degree

#### 7. Key Insights & Implications

- Geographic location appears to be the strongest predictor of business discontinuation
- Higher education levels correlate with higher discontinuation rates, contrary to what might be expected
- Entrepreneurial confidence (skill belief) and connections (knowing other entrepreneurs) correlate with higher discontinuation rates, possibly indicating greater risk-taking
- The pandemic significantly accelerated business discontinuations, with lasting effects into 2021
- Retail and hospitality sectors were particularly vulnerable to discontinuation
- A substantial portion (41.5%) of "discontinued" businesses continue in some form, suggesting business pivots rather than complete failures

### 4. Market Selection Strategies & Growth

Based on our analysis of market selection strategies and growth, here are the key findings:

#### Market Reach Analysis
- Most new entrepreneurs (82%) focus primarily on local markets (under 25% external sales)
- Only 5% of entrepreneurs are internationally-focused with more than 75% external sales
- Regional differences exist in market reach, with Mid-Atlantic and New England showing stronger international orientation
- Market reach follows a clear demographic pattern with education, age, and income playing significant roles

#### Growth and Job Creation
- International market reach correlates strongly with job creation
- Entrepreneurs with over 75% external sales create significantly more jobs (weighted average)
- Local market entrepreneurs (under 25% external sales) create fewer jobs on average
- The relationship between market reach and job creation is consistent across regions and demographics

#### Innovation Connection
- Higher innovation levels correlate with greater international market reach
- Entrepreneurs with products/services that are new to all customers are more likely to have international sales
- Local innovation (new to local market) shows similar patterns but with less pronounced effect
- Innovation appears to be a key enabler of broader market penetration and growth

#### Entrepreneur Profiles
- The "International - High Innovation" profile creates the most jobs on average
- "Local - Low Innovation" entrepreneurs create significantly fewer jobs
- Market-innovation profiles show consistent patterns across demographics
- Education level is particularly important in determining market-innovation profile, with higher education correlating with greater international reach and innovation

#### Demographic Patterns
- Gender: Male entrepreneurs show slightly higher propensity for international markets
- Age: Entrepreneurs aged 35-44 demonstrate the strongest international market orientation
- Education: College graduates and those with post-graduate education are more likely to pursue international markets
- Income: Higher household income correlates with greater likelihood of international market penetration

#### Strategic Implications
- Market selection strategy is a critical factor in entrepreneurial job creation impact
- Innovation and market reach together create a powerful combination for growth
- Educational background appears to be an important factor in enabling successful international market strategies
- Supporting international market expansion could be an effective policy for increasing entrepreneurial job creation

### 5. Industry Preferences & Employment Impact

Based on our analysis of industry preferences and employment impact, here are the key findings:

#### Industry Distribution
- Retail Trade & Hospitality is the dominant industry choice (20% of entrepreneurs)
- Healthcare & Education ranks second (16% of entrepreneurs)
- Professional Services follows at 12% of entrepreneurs
- Significant gender differences exist:
  - Women have higher representation in Retail (25% vs 17%) and Healthcare/Education (21% vs 12%)
  - Men dominate in Construction (8% vs 3%) and Information/Communication (8% vs 4%)

#### Employment Impact
- Wholesale Trade has the highest average employees per business (120)
- Administrative Services (70) and Retail/Restaurants (40) also show strong current employment
- Administrative Services leads in projected job creation (52 new jobs per business)
- Government/Health/Education ranks third in future job creation (27 jobs)
- Agriculture/Forestry/Fishing shows the lowest job creation potential (4 jobs)
- Job creation efficiency (jobs per employee) is highest in Administrative Services

#### High-Growth Industries
- Administrative Services leads with the highest composite growth score (0.45)
- Retail/Restaurants and Professional Services tie for second (0.41) in overall growth potential
- Information/Communication showed a significant decline (-2.4%) post-COVID
- Financial/Real Estate experienced substantial growth (+2.4%) post-COVID
- Agriculture/Forestry/Fishing shows the lowest growth potential (0.05)

#### Demographic Representation in Growth Industries
- Hispanic (43%) and Black (41%) entrepreneurs have higher representation in high-growth industries
- Women show stronger presence in high-growth industries (42%) than men (34%)
- Government/Health/Education shows higher representation among older entrepreneurs (55-64)

#### Implications
- Administrative Services, Retail, and Professional Services offer the strongest growth opportunities for entrepreneurs
- Targeted support for underrepresented groups in high-potential industries could maximize economic impact
- Financial/Real Estate and Administrative Services show resilience and growth post-pandemic
- Industry preferences vary significantly by demographic characteristics, suggesting tailored approaches to entrepreneurship development
- Job creation potential differs greatly between industries, with some industries creating 10x more jobs than others

### 6. Entrepreneur Ambitions

Based on our analysis of entrepreneur ambitions, here are the key findings:

#### Ambition Indicators
- **Future Intentions**: Almost half (49.3%) of current entrepreneurs intend to start another business within the next 3 years, showing a high level of serial entrepreneurship.
- **Growth Ambitions**: The largest segment (36.5%) of entrepreneurs has moderate growth ambitions (1-5 jobs), while 30% expect no growth and about 12% have hyper-growth ambitions (20+ jobs).
- **Ambition Distribution**: Low ambition entrepreneurs form the largest group (36.2%), while high and very high ambition entrepreneurs together make up about 38% of the sample.

#### Demographic Patterns
- **Gender Differences**: Male entrepreneurs show higher ambition, with 41.5% in high/very high ambition categories versus 34.3% for females. Most notably, males show 56% higher rates of very high ambition (23.2% vs 14.8% for females).
- **Age Patterns**: Younger entrepreneurs (25-34) show the highest very high ambition rates (19.1%), while those 55+ have the highest low ambition rates (40.1%). Notably, the youngest entrepreneurs (18-24) show a uniquely balanced distribution between low (31.4%) and moderate (32.5%) ambition.
- **Race Differences**: White entrepreneurs have the highest rates of low ambition (43.1%), while Black entrepreneurs demonstrate a markedly more balanced ambition distribution across all four categories (26.2% low, 26.7% moderate, 21.3% high, 25.7% very high). Black, Hispanic, and other race groups show significantly higher rates of very high ambition (20.7-25.7%) compared to White entrepreneurs (15.4%).
- **Educational Influence**: Entrepreneurs with some college education have the highest rates of moderate ambition (36.1%), while those with graduate degrees have high rates of both low ambition (35.2%) and moderate ambition (32.6%). Interestingly, those with some high school education show unusually high rates of very high ambition (35.9%) despite having 0% in the high ambition category, suggesting a U-shaped relationship between education and extreme ambition levels.
- **Income Effects**: Household income over $100,000 appears as one of the top predictors of high entrepreneurial ambition, suggesting financial security may enable more ambitious ventures rather than necessity-based entrepreneurship.

#### Ambition Predictors
- **Key Factors**: Number of business owners, industry type, and education level are the strongest predictors of entrepreneurial ambition, though based on a limited sample of 181 entrepreneurs with complete data.
- **Industry Effects**: Retail/restaurant and professional services entrepreneurs show stronger ambition indicators.
- **Regional Variations**: The South and Southeast regions appear among the top predictors for entrepreneurial ambition, suggesting potential geographic influences on growth orientation.

#### Ambition-Outcome Relationship
- **Business Performance**: A statistically significant but modest positive correlation (0.0663, p-value 0.0484) exists between ambition level and business size, suggesting ambition may play a small role in business outcomes.
- **Business Size Distribution**: The density plot shows that higher ambition entrepreneurs tend to have slightly more employees, though there is substantial overlap between ambition categories.
- **Serial Entrepreneurship Gap**: New entrepreneurs are 3.7x more likely to plan another startup (49.3%) than established entrepreneurs (13.3%), indicating new entrepreneurs are significantly more likely to pursue multiple ventures simultaneously or sequentially.
- **Business Size Structure**: Most entrepreneurs operate micro-businesses (1-5 employees): 50.2% of new entrepreneurs and 47.6% of established entrepreneurs. However, established entrepreneurs have higher proportions in small (15.5% vs. 12.3%), medium (7.4% vs. 4.7%), and large (3.1% vs. 1.6%) business categories, reflecting a quantifiable "scaling gap" in business development stages.
- **Innovation Relationship**: While innovation data was insufficient for complete analysis, the attempt to measure the relationship between ambition and innovation suggests an important direction for future research with more complete data.

### 7. Temporal and Regional Entrepreneurship Analysis

Based on our analysis of entrepreneurial activity across time, regions, and industries, we can draw the following key insights:

#### Temporal Trends
1. **Temporal Trends**:
   - New entrepreneurship rates showed a consistent upward trend from 2015 (12.0%) to 2019 (17.0%), with a slight decline during COVID-19 in 2020 (15.5%) that stabilized in 2021 (15.7%)
   - Established entrepreneurship rates were more volatile but also peaked in 2019 (11.0%), dropped slightly during COVID (10.3%), and continued to decline in 2021 (9.0%)
   - The gap between new and established entrepreneurship rates widened over time, suggesting challenges in business sustainability

2. **Regional Patterns**:
   - The South (16.5%) and Mountain and Plains (16.2%) regions had the highest new entrepreneurship rates
   - Mountain and Plains stood out with the highest established entrepreneurship rate (13.3%) and showed extreme volatility over time, particularly with established entrepreneurship more than doubling from 2020 (14.1%) to 2021 (21.2%)
   - Great Lakes region showed the lowest new entrepreneurship rate (12.8%)
   - New York-New Jersey had the lowest established entrepreneurship rate (7.2%)
   - Pacific Northwest exhibited the largest single-year jump in new entrepreneurship (20.8% in 2018)
   - Central Midwest had the strongest post-pandemic recovery, increasing from 12.5% to 17.1% in 2021
   - COVID-19 affected regions differently, with Mountain and Plains showing a significant jump in new entrepreneurship during 2020 (23.4%)

3. **Industry Evolution**:
   - Retail Trade, Hotels & Restaurants consistently dominated new entrepreneurship (about 20% of all new ventures)
   - Financial Intermediation and Real Estate showed steady growth for new entrepreneurs, increasing from 6.7% in 2015 to 10.1% in 2021, and was the only top industry to maintain growth momentum through the pandemic
   - Administrative Services and NOT CLASSIFIED/MISSING categories saw the largest positive change post-COVID (+31.7% and +290.6% respectively)
   - Information and Communication industry experienced the steepest decline post-COVID (-36.3%), followed by Professional Services (-24.7%)
   - Professional Services declined steeply from 15% in 2015 to 6.6% in 2021
   - Manufacturing showed steady growth until 2019 (9.9%) before declining post-pandemic
   - Government/Health/Education saw a recovery in 2020 after declining for years, suggesting pandemic response opportunities

4. **Regional Industry Specialization**:
   - New York-New Jersey has the highest concentration in Retail/Hotels/Restaurants (24.8%), significantly above other regions
   - Central Midwest shows unique specialization in Government/Health/Education (23.3%) and Manufacturing (13%)
   - Pacific Northwest has distinctive strength in Mining/Construction (12.3%) and Personal/Consumer Services (10.8%)
   - New England has surprisingly low Agriculture participation (0.9%) despite being a traditionally agricultural region

5. **New vs. Established Business Dynamics**:
   - Mining and Construction industries showed the highest survival ratio (1.37), followed by Agriculture/Forestry/Fishing (1.02)
   - Retail Trade, Hotels & Restaurants had the lowest survival ratio (0.32) despite being the most popular sector for new entrepreneurs
   - Business size distribution reveals that established entrepreneurs tend to have larger businesses with more employees than new entrepreneurs
   - 31% of new entrepreneurs are solopreneurs (0 employees) compared to 26% of established entrepreneurs
   - Established entrepreneurs are more likely to have small (6-20 employees), medium (21-100) and large (100+) businesses
   - Survival ratios vary dramatically by region-industry combinations, with New England Agriculture entrepreneurs having an 11x higher likelihood of becoming established in Retail
   - New entrepreneurs in Information/Communication in Central Midwest have 10.9x higher survival rates when they transition to Agriculture

6. **COVID-19 Impact**:
   - Surprisingly, Retail/Hotels/Restaurants showed remarkable stability (+0.2%) despite pandemic lockdowns
   - Personal/Consumer Services remained virtually unchanged (0.02%)
   - The dramatic increase in "Not Classified/Missing" (290.6%) suggests emergence of new business models or reporting challenges during the pandemic
   - Transportation/Storage showed modest growth (+7.1%) reflecting increased delivery and logistics demand
   - Information and Communication saw the steepest decline, suggesting digital transformation paradoxically hurt this sector

7. **Entrepreneurial Survival Factors** (from our detailed survival analysis):
   - **Regional Variation**: Mountain and Plains region has the highest entrepreneurial survival rate at approximately 35.2%, while New York-New Jersey has the lowest at around 20.1%
   - **Age Factor**: Entrepreneurs aged 55-64 show notably higher survival rates (approximately 32.8%) compared to younger entrepreneurs, with those aged 18-24 having the lowest survival rates (around 17.9%)
   - **Skill Confidence**: Entrepreneurs who believe they have the skills to start a business ("Yes" responses) show dramatically higher survival rates (around 28.5%) than those who don't (around 8.1%), suggesting self-efficacy is a critical factor
   - **Network Effects**: Entrepreneurs who know other entrepreneurs demonstrate significantly higher survival rates (approximately 28.7%) than those without entrepreneurial connections (around 20.1%), highlighting the importance of professional networks
   - **Regional-Industry Combinations**: The analysis revealed specific geographic-industry niches with exceptionally high survival rates, including Mining/Construction in Mountain and Plains (over 65% survival rate) and Manufacturing in Central Midwest (over 60% survival rate)
   - **Fear of Failure**: Interestingly, entrepreneurs reporting fear of failure showed only slightly lower survival rates than those without such fears, suggesting this factor may be less predictive than commonly assumed
   - **Predictive Modeling**: Our logistic regression model demonstrated moderate predictive power with an AUC of approximately 0.70, indicating that demographic, geographic, and attitudinal factors can help predict entrepreneurial survival

8. **Policy Implications**:
   - High-failure-rate industries like Retail, Restaurants and Professional Services need targeted support to improve sustainability
   - Regional disparities suggest opportunities for knowledge transfer from high-entrepreneurship regions to lower ones
   - COVID-19 accelerated growth in Financial Services and Administrative Services, indicating potential for further development
   - Support for micro-businesses (1-5 employees) is critical as they represent approximately 50% of both new and established ventures
   - The significant drop in Information and Communication entrepreneurship post-COVID warrants investigation to address barriers in this typically high-innovation sector
   - Regional industry specializations suggest opportunities for targeted economic development programs aligned with existing strengths
   - Entrepreneurial networks and mentorship programs could significantly improve survival rates, especially for demographic groups with lower baseline success rates
   - Entrepreneurial education should emphasize skill development and confidence building, as these factors strongly correlate with business survival
   - Support programs might be most effectively targeted at young entrepreneurs (18-24), who show the lowest survival rates but potentially the highest long-term impact
   - Age-specific entrepreneurship programs should consider the different needs and challenges faced by different age cohorts

## Conclusion: Cross-Cutting Insights and Implications

Our comprehensive analysis of American entrepreneurs using the GEM dataset from 2015-2021 reveals several important cross-cutting themes and insights:

### 1. Demographic Paradoxes and Opportunities

- **The Entrepreneurial Diversity Gap**: Black Americans show high new entrepreneurship rates (15.1%) but significantly lower established rates (4.8%), with similar patterns for Hispanic and other minority entrepreneurs. This stark transition gap suggests systemic barriers to long-term business sustainability for minority-owned businesses, despite their initially higher entrepreneurial activity.

- **The Gender Entrepreneurship Paradox**: Women show substantially lower entrepreneurship rates (9.4% new, 5.8% established) compared to men (15.2% new, 9.3% established), yet have significantly lower business discontinuation rates (4.0% vs. 5.3%). This suggests women may be more selective and prudent in their entrepreneurial ventures, pointing to untapped potential for economic growth through targeted support for female entrepreneurs.

- **Age and Ambition Inverse Relationship**: Younger entrepreneurs (25-34) show higher very high ambition rates (19.1%) but lower survival rates (young adults 18-24 have just 17.9% survival), while entrepreneurs aged 55-64 show notably higher survival rates (32.8%) but higher low ambition rates (40.1%). This creates an opportunity for mutually beneficial mentorship programs.

- **Race and Ambition Dynamics**: While White entrepreneurs have the highest rates of low ambition (43.1%), Black entrepreneurs show a remarkably balanced and more ambitious profile across all categories, with significantly higher rates of very high ambition (25.7%) compared to White entrepreneurs (15.4%). This suggests underutilized entrepreneurial potential in minority communities.

### 2. Team Dynamics and Business Success

- **The Team Size Paradox**: Both solo ventures (57.7% of new entrepreneurs) and very large teams (6+ founders) show better survival rates (established/new ratios of 1.13 and 1.32 respectively) than mid-sized teams (small 3-5 person teams have the lowest ratio at 0.55). This U-shaped relationship challenges conventional wisdom about optimal founding team structures.

- **Industry-Specific Team Structures**: Information and Communication (2.35 owners) and Financial Intermediation (2.23 owners) benefit from larger founding teams, while Professional Services (1.76) and Construction (1.74) show smaller average team sizes. This indicates that optimal team structures vary significantly by industry.

- **Growth Impact of Team Size**: Large teams (6+ owners) employ 154.0 people on average and project creating 119.2 new jobs, dramatically outperforming other team sizes. However, solo ventures project more job growth (14.6 jobs) than duo teams (7.7 jobs), suggesting that different team structures optimize for different growth trajectories.

- **Demographic Team Patterns**: Male entrepreneurs form larger teams (1.99 owners vs. 1.72 for females), while Hispanic entrepreneurs have the largest teams by race (2.05 owners) and Black entrepreneurs have the smallest (1.62). These patterns may reflect different cultural approaches to entrepreneurship or access to co-founding networks.

### 3. Regional Entrepreneurial Ecosystems

- **Geographic Performance Disparities**: Mountain and Plains region stands out with both the highest new entrepreneurship rate (20.8%) and established entrepreneurship rate (13.3%), with approximately 35.2% business survival rates. In stark contrast, New York-New Jersey has the lowest new entrepreneurship rate (8.3%) and just 20.1% business survival rates. These extreme differences suggest fundamental ecosystem factors that significantly impact entrepreneurial success.

- **COVID-19 Regional Resilience**: Regional responses to COVID-19 varied dramatically, with Mountain and Plains showing a significant entrepreneurship boom during 2020 (23.4% new entrepreneurship rate), Central Midwest demonstrating strong post-pandemic recovery (increasing from 12.5% to 17.1% in 2021), while other regions struggled. This natural experiment reveals regional economic resilience factors.

- **Regional-Industry Specialization**: Each region demonstrates distinct entrepreneurial specializations: New York-New Jersey in Retail/Restaurants (24.8%), Central Midwest in Government/Health/Education (23.3%), Pacific Northwest in Mining/Construction (12.3%). These specializations largely align with broader regional economic characteristics and suggest targeted policy approaches.

- **Regional Survival Variations**: Business survival rates vary dramatically by region-industry combinations, with Mining/Construction in Mountain and Plains achieving over 65% survival rates and Manufacturing in Central Midwest exceeding 60%. These specialized "success pockets" offer valuable lessons for entrepreneurs and policymakers alike.

### 4. Market Reach, Innovation and Growth Dynamics

- **Market Reach Patterns**: The vast majority (82%) of American entrepreneurs focus primarily on local markets (under 25% external sales), with only 5% pursuing international strategies (over 75% external sales). This heavy local focus may be limiting growth potential, as international market reach strongly correlates with job creation.

- **The Innovation-Market Reach Connection**: Our analysis reveals a powerful synergy between innovation and international market reach. Entrepreneurs with products/services that are new to all customers are significantly more likely to pursue international markets, and this "International - High Innovation" profile creates the most jobs on average.

- **Education-Innovation-Market Reach Relationship**: College graduates and those with post-graduate education are more likely to pursue international markets and develop innovative products. This educational advantage appears to be a critical factor in enabling broader market strategies and growth outcomes.

- **Industry Growth Resilience**: Administrative Services (composite growth score 0.45), Retail/Restaurants (0.41), and Financial/Real Estate (substantial +2.4% growth post-COVID) demonstrate strong growth potential post-pandemic. Surprisingly, Information/Communication showed significant vulnerability (-36.3% decline post-COVID) despite widespread digital transformation trends.

- **Job Creation Disparities**: The employment impact varies dramatically across industries, with Administrative Services (52 projected new jobs per business) and Wholesale Trade (120 current employees per business) vastly outperforming Agriculture/Forestry/Fishing (just 4 projected new jobs). These 10x differences highlight the importance of industry selection for economic impact.

### 5. Entrepreneurial Mindset and Success Factors

- **Psychological Success Drivers**: Self-perception of entrepreneurial skills emerges as the single strongest predictor of entrepreneurial activity, increasing likelihood by 6.2x. This confidence also translates to survival outcomes, with entrepreneurs who believe they have the skills showing dramatically higher survival rates (28.5%) than those who don't (8.1%). However, this confidence also correlates with higher discontinuation rates (6.6% vs. 2.1%), suggesting a complex relationship between confidence, risk-taking, and outcomes.

- **Network Effects**: Knowing other entrepreneurs increases entrepreneurship likelihood by 3.8x and significantly boosts survival rates (28.7% vs. 20.1% for those without entrepreneurial connections). These strong network effects highlight the critical importance of entrepreneurial communities and mentorship for both business formation and sustainability.

- **Ambition-Reality Gap**: While 49.3% of current entrepreneurs intend to start another business within three years and many express high growth ambitions, the correlation between stated ambitions and actual business outcomes is modest (correlation of just 0.0663). This suggests the need for better support structures to help entrepreneurs bridge the gap between ambition and execution.

- **Fear of Failure Paradox**: Fear of failure decreases entrepreneurship likelihood by 38%, yet shows a counterintuitive relationship with outcomes – those without fear of failure actually have slightly higher discontinuation rates (5.1%) compared to those with fear of failure (4.1%). This challenges conventional wisdom about risk aversion and suggests that some caution may be beneficial.

### 6. Business Evolution and Sustainability

- **Entrepreneurial Transition Challenges**: We observe a widening gap between new and established entrepreneurship rates over time, with a consistent upward trend in new entrepreneurship from 2015 (12.0%) to 2019 (17.0%) but more volatile and generally lower established rates. This suggests growing challenges in business sustainability despite increased entrepreneurial activity.

- **Industry Sustainability Variations**: Mining and Construction industries showed the highest survival ratio (1.37), while Retail Trade, Hotels & Restaurants had the lowest (0.32) despite being the most popular sector for new entrepreneurs. This massive difference (over 4x) in survival outcomes by industry highlights the critical importance of sector selection.

- **Business Size Evolution**: A clear progression emerges from new to established entrepreneurs in business size, with established entrepreneurs having lower rates of solopreneurs (26% vs. 31% for new) and higher rates of small (15.5% vs. 12.3%), medium (7.4% vs. 4.7%), and large businesses (3.1% vs. 1.6%). However, both groups are dominated by micro-businesses (1-5 employees), representing approximately 50% of both new and established ventures.

- **Pivoting Rather Than Failing**: Of discontinued businesses, 41.5% continue in some form rather than ceasing operations completely, suggesting that "business discontinuation" often represents strategic pivots or transitions rather than outright failures. This underscores the importance of adaptability and evolution in entrepreneurial journeys.

### 7. COVID-19 Impact and Industry Transformation

- **Pandemic Disruption**: Discontinuation rates increased significantly during the COVID-19 pandemic, rising from 5.1% in 2019 to 6.4% in 2021, with gender differences widening (males saw sharper increases from 5.5% to 7.4%, while females saw more modest increases from 4.8% to 5.4%).

- **Unexpected Industry Resilience**: Retail/Hotels/Restaurants showed remarkable stability (+0.2%) despite pandemic lockdowns and restrictions, defying expectations of sector collapse. Meanwhile, Information and Communication experienced the steepest decline (-36.3%) despite widespread digital transformation, suggesting complex industry dynamics during the crisis.

- **Emerging Sectors**: Administrative Services (+31.7%) and Financial/Real Estate (+2.4%) demonstrated significant growth during and after the pandemic, while the dramatic increase in "Not Classified/Missing" businesses (290.6%) suggests the emergence of entirely new business models or categories outside traditional classification systems.

- **Gender Industry Shifts**: Women showed stronger presence in high-growth industries post-pandemic (42%) than men (34%), and Hispanic (43%) and Black (41%) entrepreneurs have higher representation in these growth sectors. This suggests that demographic groups traditionally underrepresented in entrepreneurship may be better positioned for the post-pandemic economy.

### 8. Predictive Insights and Entrepreneurial Profiles

- **Business Discontinuation Predictors**: Region (25.9% importance), education (18.1%), and age (15.3%) emerge as the strongest predictors of business discontinuation, with specific risk factors including being aged 25-34, having some college education, and operating in the Southeast region. These predictive insights provide a framework for identifying ventures at risk.

- **High-Growth Entrepreneur Profile**: Our analysis identifies a clear profile of high-growth entrepreneurs: typically male, aged 25-44, with higher education, operating in teams of 3+ people, in Administrative Services or Wholesale Trade, with international market reach and innovative products/services. This profile creates significantly more jobs and economic impact.

- **Sustainable Business Profile**: The most sustainable businesses tend to be operated by older entrepreneurs (55-64), in the Mountain and Plains region, in Construction or Financial Services industries, with strong entrepreneurial skill confidence and networks. The stark difference between high-growth and high-sustainability profiles suggests entrepreneurs may need to choose their priority.

- **Serial Entrepreneurship Gap**: New entrepreneurs are 3.7x more likely to plan another startup (49.3%) than established entrepreneurs (13.3%), indicating that entrepreneurial ambition tends to stabilize as businesses mature. This serial entrepreneurship tendency represents both opportunity (innovation) and risk (diverted focus) for economic development.

### 9. Policy and Support Implications

- **Targeted Demographic Support**: The data strongly suggests the need for targeted programs addressing the specific challenges faced by minority entrepreneurs in transitioning from new to established businesses. Black entrepreneurs show particular promise with balanced ambition profiles and high representation in growth industries.

- **Industry-Specific Interventions**: Given the dramatic differences in survival rates across industries (from 32% in Retail to 137% in Construction), industry-specific support approaches are likely to be more effective than one-size-fits-all programs. Particular attention should be paid to balancing support between popular but high-failure industries and less popular but more sustainable sectors.

- **Regional Ecosystem Development**: The stark regional differences in entrepreneurship rates, survival, and industry specialization suggest that policies tailored to regional conditions will be more effective than national approaches. The Mountain and Plains region offers a particularly valuable model for successful entrepreneurial ecosystem development.

- **Education and Network Development**: Given the critical role of entrepreneurial networks and skills confidence in both business formation and survival, programs that combine skill development with community building could have outsized impacts on entrepreneurial success, particularly for demographic groups with lower baseline performance.

- **Innovation and Market Expansion Support**: The strong connection between innovation, international market reach, and job creation suggests that support for product development and export capabilities could significantly enhance the economic impact of American entrepreneurship, particularly for businesses with growth potential.

This comprehensive analysis provides a multifaceted view of American entrepreneurship, revealing complex patterns and opportunities that challenge conventional wisdom and highlight pathways for more effective entrepreneurship support and development.