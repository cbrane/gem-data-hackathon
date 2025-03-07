# GEM Data Hackathon Guide

## Project Overview
- Hackathon focused on analyzing GEM (Global Entrepreneurship Monitor) data (2015-2021)
- Challenge: Analyze diverse characteristics of American entrepreneurs
- Main dataset: Hackathon_GEM_Data_FULL.csv (~3.2MB)
- Deliverable: 3 slides due March 9, 2025, 9 PM ET

## Challenge Statement
> "Offer a comprehensive analysis of the diverse characteristics of American entrepreneurs, including aspects such as their backgrounds, co-founder dynamics, industry preferences, impact on employment, market selection strategies, ambitions, and factors influencing their decision to discontinue their ventures. Utilize all available variables from the Global Entrepreneurship Monitor (GEM) dataset and feel free to enhance your analysis by integrating it with additional relevant datasets."

## Project Structure
- **documentation/** - Contains project documentation and data dictionaries
- **notebooks/** - Jupyter notebooks for analysis
- **data/** - Contains the GEM dataset

## Analysis Plan
We've organized our analysis into the following components:
1. Entrepreneur Backgrounds & Demographics
2. Co-founder Dynamics & Team Composition
3. Business Discontinuation Factors
4. Market Selection Strategies
5. Industry Preferences & Employment Impact
6. Entrepreneur Ambitions

## Python Environment Setup
```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On macOS/Linux
# venv\Scripts\activate  # On Windows

# Install key data science packages
pip install pandas numpy matplotlib seaborn scikit-learn jupyter plotly statsmodels

# Launch Jupyter Notebook
jupyter notebook
```

## Data Analysis Workflow

### 1. Data Loading and Exploration
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Set plot styling
plt.style.use('seaborn-v0_8-whitegrid')
sns.set_palette('viridis')
plt.rcParams['figure.figsize'] = (10, 6)
plt.rcParams['font.size'] = 12

# Load the data
gem_data = pd.read_csv('../data/Hackathon_GEM_Data_FULL.csv')

# Initial exploration
gem_data.head()
gem_data.info()
gem_data.describe()

# Check for missing values
gem_data.isnull().sum()
```

### 2. Working with Survey Weights
```python
# Always use the 'weight' column for weighted analyses
# Calculate weighted percentages
weighted_percentage = pd.crosstab(
    index=gem_data['demographic_variable'],
    columns=gem_data['outcome_variable'],
    values=gem_data['weight'],
    aggfunc='sum',
    normalize='index'
) * 100

# Calculate weighted means
weighted_mean = np.average(gem_data['numeric_variable'], weights=gem_data['weight'])
```

### 3. Visualization Best Practices
```python
# Add appropriate titles and labels
plt.title('Clear Title Describing the Visualization')
plt.xlabel('X-Axis Label')
plt.ylabel('Y-Axis Label')

# Add data labels on bars
for i, v in enumerate(values):
    plt.text(i, v + 0.2, f"{v:.1f}%", ha='center')

# Include a legend when needed
plt.legend(title='Legend Title')

# Use tight_layout() to prevent label cutoff
plt.tight_layout()
```

### 4. Machine Learning Techniques
```python
from sklearn.preprocessing import OneHotEncoder
from sklearn.compose import ColumnTransformer
from sklearn.pipeline import Pipeline
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import classification_report

# Create preprocessing pipeline for categorical variables
categorical_transformer = Pipeline(steps=[
    ('encoder', OneHotEncoder(handle_unknown='ignore'))
])

# Create the modeling pipeline
model = Pipeline(steps=[
    ('preprocessor', preprocessor),
    ('classifier', RandomForestClassifier(n_estimators=100, random_state=42))
])

# Use sample weights from survey
model.fit(X_train, y_train, classifier__sample_weight=weights_train)
```

## Notebook Structure
1. **entrepreneur_profiles.ipynb** - Analyzing entrepreneur backgrounds and demographics
2. **cofounder_dynamics.ipynb** - Examining team composition and co-founder relationships
3. **business_discontinuation.ipynb** - Investigating factors leading to business discontinuation
4. Additional notebooks for remaining analysis components (to be created)

## Useful Git Commands
```bash
# Add files
git add .

# Commit changes
git commit -m "Description of changes"

# Create and checkout new branch
git checkout -b feature-branch-name
```

## Key Variables for Analysis
- **Demographic Variables**: gender, age_range, race, education, household_income, region
- **Entrepreneurship Indicators**: new_entrepreneur, established_entrepreneur
- **Business Characteristics**: new_entrepreneur_industry, new_entrepreneur_owners, new_entrepreneur_employees
- **Performance Metrics**: new_entrepreneur_new_jobs (projected job growth)
- **Discontinuation Variables**: discontinued_business, discontinued_business_continuation