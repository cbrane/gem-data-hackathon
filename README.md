# GEM Data Hackathon 2025

## Overview
This repository contains our analysis for the Butler Institute GEM Data Hackathon 2025. Our team is analyzing the Global Entrepreneurship Monitor (GEM) dataset to understand the diverse characteristics of American entrepreneurs from 2015-2021.

## Challenge Statement
> "Offer a comprehensive analysis of the diverse characteristics of American entrepreneurs, including aspects such as their backgrounds, co-founder dynamics, industry preferences, impact on employment, market selection strategies, ambitions, and factors influencing their decision to discontinue their ventures. Utilize all available variables from the Global Entrepreneurship Monitor (GEM) dataset and feel free to enhance your analysis by integrating it with additional relevant datasets."

## Project Structure
- **data/**: Contains the GEM dataset
- **documentation/**: Contains project documentation and data dictionaries
  - `CLAUDE.md`: Quick reference guide for analysis techniques
  - `analysis_approach.md`: Detailed analysis plan
  - `hackathon_info_doc.md`: Original hackathon challenge information
  - `project_progress.md`: Current progress report
  - `updated_data_dictionary.md`: Variable descriptions and data cleaning notes
- **notebooks/**: Jupyter notebooks for analysis
  - `entrepreneur_profiles.ipynb`: Analysis of entrepreneur backgrounds and demographics
  - `cofounder_dynamics.ipynb`: Analysis of team composition and co-founder relationships
  - `business_discontinuation.ipynb`: Analysis of factors leading to business discontinuation
  - `data_import.ipynb`, `gem_data_exploration.ipynb`, `gem_weighted_analysis.ipynb`: Initial exploratory analyses

## Analysis Framework
Our analysis is organized into six key components:
1. **Entrepreneur Backgrounds & Demographics** - Understanding who American entrepreneurs are
2. **Co-founder Dynamics & Team Composition** - Analyzing partnership patterns
3. **Business Discontinuation Factors** - Identifying why businesses fail
4. **Market Selection Strategies** - Examining how entrepreneurs choose markets
5. **Industry Preferences & Employment Impact** - Analyzing industry patterns and job creation
6. **Entrepreneur Ambitions** - Understanding growth intentions and aspirations

## Getting Started
1. Clone this repository
2. Set up a Python environment with the required packages:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On macOS/Linux
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter plotly statsmodels
   ```
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Explore the notebooks in the `notebooks/` directory

## Key Insights
Our analysis has revealed several interesting patterns in American entrepreneurship:
- Demographic analysis shows varying entrepreneurship rates across gender, age, race, and education levels
- Team composition varies significantly by industry and affects business performance
- Certain factors strongly predict business discontinuation
- [Additional insights to be added as analysis progresses]

## Team
- Connor Raney

## Hackathon Information
- **Submission Deadline**: March 9, 2025, 9 PM ET
- **Deliverable**: 3 slides (2 for results, 1 for methodology)