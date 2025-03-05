# GEM Data Hackathon Guide

## Project Overview
- Hackathon focused on analyzing GEM (Global Entrepreneurship Monitor) data
- Main dataset: Hackathon_GEM_Data_FULL.csv (~3.2MB)
- PDF Guide: "Butler Institute GEM Data Hackathon Guide 2025"

## Python Environment Setup
```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On macOS/Linux
# venv\Scripts\activate  # On Windows

# Install key data science packages
pip install pandas numpy matplotlib seaborn scikit-learn jupyter plotly

# Launch Jupyter Notebook
jupyter notebook
```

## Data Analysis Workflow
1. Data Loading and Exploration
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load the data
gem_data = pd.read_csv('Hackathon_GEM_Data_FULL.csv')

# Initial exploration
gem_data.head()
gem_data.info()
gem_data.describe()

# Check for missing values
gem_data.isnull().sum()
```

2. Data Cleaning
```python
# Handle missing values
# Remove duplicates
# Convert data types as needed
```

3. Exploratory Data Analysis
```python
# Summary statistics
# Correlation analysis
# Data visualization
```

4. Feature Engineering
```python
# Create new features based on existing data
# Encode categorical variables
# Scale/normalize numerical features
```

5. Advanced Analysis
```python
# Statistical tests
# Machine learning models
# Time series analysis (if applicable)
```

## Visualization Techniques
```python
# Basic plots
sns.histplot(data=gem_data, x='column_name')
sns.scatterplot(data=gem_data, x='column_x', y='column_y')

# Advanced visualizations
sns.pairplot(gem_data[['col1', 'col2', 'col3']])
sns.heatmap(gem_data.corr(), annot=True, cmap='coolwarm')

# Interactive plotting with Plotly
import plotly.express as px
fig = px.scatter(gem_data, x='column_x', y='column_y', color='category')
fig.show()
```

## Useful Git Commands
```bash
# Initialize repository (if needed)
git init

# Add files
git add .

# Commit changes
git commit -m "Description of changes"

# Create and checkout new branch
git checkout -b feature-branch-name
```

## Note
This file will be updated as we explore the GEM dataset and understand more about the specific requirements and goals of the hackathon.