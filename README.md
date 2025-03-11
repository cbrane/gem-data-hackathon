# GEM Data Hackathon 2025

## Overview
This repository contains our comprehensive analysis for the Butler Institute GEM Data Hackathon 2025. Our team analyzed the Global Entrepreneurship Monitor (GEM) dataset to understand the diverse characteristics of American entrepreneurs from 2015-2021, revealing key patterns in entrepreneurial backgrounds, team dynamics, market strategies, and success factors.

## Challenge Statement
> "Offer a comprehensive analysis of the diverse characteristics of American entrepreneurs, including aspects such as their backgrounds, co-founder dynamics, industry preferences, impact on employment, market selection strategies, ambitions, and factors influencing their decision to discontinue their ventures. Utilize all available variables from the Global Entrepreneurship Monitor (GEM) dataset and feel free to enhance your analysis by integrating it with additional relevant datasets."

## Project Structure
- **data/**: Contains the GEM dataset with over 15,800 observations from 2015-2021
- **documentation/**: Project documentation and analysis results
  - `CLAUDE.md`: Quick reference guide for analysis techniques
  - `analysis_approach.md`: Detailed analysis plan
  - `comprehensive_gem_analysis.md`: Complete analysis findings and insights
  - `hackathon_info_doc.md`: Original hackathon challenge information
  - `success_factors_slide.md`: Key success factors for entrepreneurs
  - `temporal_regional_analysis.md`: Analysis of entrepreneurship across time and regions
  - `updated_data_dictionary.md`: Variable descriptions and data cleaning notes
- **notebooks/**: Jupyter notebooks for analysis
  - `entrepreneur_profiles.ipynb`: Analysis of entrepreneur backgrounds and demographics
  - `cofounder_dynamics.ipynb`: Analysis of team composition and co-founder relationships
  - `business_discontinuation.ipynb`: Analysis of factors leading to business discontinuation
  - `market_selection_strategies.ipynb`: Analysis of how entrepreneurs select and expand into markets
  - `industry_employment_impact.ipynb`: Analysis of industry preferences and job creation
  - `entrepreneur_ambitions.ipynb`: Analysis of future intentions and growth aspirations
  - `entrepreneurship_by_year_region.ipynb`: Temporal and regional analysis
  - `data_import.ipynb`, `gem_data_exploration.ipynb`, `gem_weighted_analysis.ipynb`: Initial exploratory analyses

## Analysis Framework
Our comprehensive analysis addresses all aspects of the challenge through seven key components:
1. **Entrepreneur Backgrounds & Demographics** - Understanding who American entrepreneurs are
2. **Co-founder Dynamics & Team Composition** - Analyzing partnership patterns and team structures
3. **Business Discontinuation Factors** - Identifying why businesses fail and survival predictors
4. **Market Selection Strategies** - Examining how entrepreneurs choose markets and impact on growth
5. **Industry Preferences & Employment Impact** - Analyzing industry patterns and job creation potential
6. **Entrepreneur Ambitions** - Understanding growth intentions and aspirations
7. **Temporal & Regional Analysis** - Examining entrepreneurship trends across time periods and US regions

## Getting Started
1. Clone this repository
2. Set up a Python environment with the required packages:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On macOS/Linux
   # venv\Scripts\activate  # On Windows
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter plotly statsmodels
   ```
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Explore the notebooks in the `notebooks/` directory

## Key Findings
Our analysis revealed several important patterns in American entrepreneurship:

### 1. Entrepreneur Profiles
- **Gender Gap**: Males have higher entrepreneurship rates (15.2% new, 9.3% established) compared to females (9.4% new, 5.8% established)
- **Age Patterns**: Middle-aged adults (35-44) have the highest new entrepreneurship rates (16.8%)
- **Race Dynamics**: Black Americans have high new entrepreneurship rates (15.1%) but lower established rates (4.8%)
- **Education Impact**: Advanced degree holders show strong established entrepreneurship rates (12.6%)

### 2. Co-founder Dynamics
- **Team Distribution**: Solo founders dominate (57.7% of new entrepreneurs), with U-shaped survival patterns favoring both solo and large teams
- **Industry Patterns**: Information/Communication has the largest teams (2.35 owners on average)
- **Performance Impact**: Large teams (6+ owners) employ significantly more people (154.0 on average) and project higher job growth

### 3. Success Factors
- **Key Predictors**: Entrepreneurial skills confidence (6.2x increase in likelihood) and knowing other entrepreneurs (3.8x) are the strongest entrepreneurship predictors
- **Regional Influence**: Mountain and Plains region has highest survival rates (35.2%)
- **Industry Selection**: Mining/Construction shows highest survival ratio (1.37), while Retail has lowest (0.32)
- **Market Strategies**: International market reach strongly correlates with job creation

### 4. Business Evolution
- **COVID-19 Impact**: Discontinuation rates increased from 5.1% (2019) to 6.4% (2021)
- **Industry Shifts**: Financial/Real Estate (+2.4%) and Administrative Services (+31.7%) showed growth post-pandemic, while Information/Communication declined (-36.3%)
- **Regional Resilience**: Mountain and Plains showed entrepreneurship boom during 2020 (23.4%)

For complete findings, please see `documentation/comprehensive_gem_analysis.md`.

## Team
- Connor Raney (https://github.com/cbrane/) - Code (all Python code in repo) & Analysis
- Arman Ozsu (https://github.com/Arman0z) - Code (Data Cleaning in R, Python version in repo) & Analysis

## Hackathon Information
- **Submission Deadline**: March 9, 2025, 9 PM ET
- **Deliverable**: 3 slides (2 for results, 1 for methodology)
- **Final Presentation**: April 8, 2025
