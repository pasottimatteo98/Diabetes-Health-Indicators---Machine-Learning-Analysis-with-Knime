# Diabetes Health Indicators Project

## Repository Structure
This repository contains KNIME workflow files for a diabetes prediction project:

- `DataAPP_TEAM14.knwf` (1,138 KB): Main data application workflow
- `Deployment_TEAM14.knwf` (46 KB): Deployment workflow for the model
- `Training_TEAM14.knwf` (104 KB): Training workflow for model development
- `TEAM14`: PDF Paper Document (806 KB)
- `.gitattributes`: Git configuration file (1 KB)

## Overview
This project analyzes health indicators that can predict diabetes without requiring specific medical tests. Using decision tree-based machine learning algorithms, the study evaluates which factors indicate diabetes presence and their impact level.

## Dataset
Data sourced from CDC's Behavioral Risk Factor Surveillance System (BRFSS), a 2015 health telephone survey with responses from 40,109 Americans across 17 variables plus the target variable "Diabetes" (0=no diabetes, 1=diabetes).

### Variables
- **Age**: Patient age (categorized)
- **Sex**: 0=female, 1=male
- **HighChol**: High cholesterol presence (0=no, 1=yes)
- **CholCheck**: Cholesterol check in last five years (0=no, 1=yes)
- **BMI**: Body Mass Index
- **Smoker**: "Have you smoked at least 100 cigarettes in your life?" (0=no, 1=yes)
- **HeartDiseaseorAttack**: Coronary heart disease or myocardial infarction (0=no, 1=yes)
- **PhysActivity**: Physical activity in past 30 days (0=no, 1=yes)
- **Fruits**: Daily fruit consumption (0=no, 1=yes)
- **Veggies**: Daily vegetable consumption (0=no, 1=yes)
- **HvyAlcoholConsump**: Heavy alcohol consumption (0=no, 1=yes)
- **GenHlth**: General health assessment (1=excellent to 5=poor)
- **MenHlth**: Days of poor mental health (1-30)
- **PhysHlth**: Days of physical illness/injury in past 30 days (1-30)
- **DiffWalk**: Difficulty walking/climbing stairs (0=no, 1=yes)
- **Hypertension**: Hypertension presence (0=no, 1=yes)
- **Stroke**: Previous stroke (0=no, 1=yes)

## Methodology
1. **Pre-processing**:
   - Normalization of numerical variables to [0,1]
   - Correlation analysis
   - Variance Inflation Factor (VIF) evaluation for multicollinearity

2. **Models Tested**:
   - Heuristic models (Decision trees, Random forests)
   - Regression-based models (Logistic regression)
   - Separation models (Support vector machines, Neural networks)
   - Probabilistic models (Naive Bayes, Tree-augmented Naive Bayes)
   - **XGBoost** (final selected model)

3. **Hyperparameter Optimization**:
   - Bayesian optimization strategies
   - Cross-validation
   - 10,000+ iterations to find optimal parameters

## Results
XGBoost performed best with a log loss of 0.221. Feature importance analysis revealed:

- **BMI**: Most significant predictor
- **Hypertension**: Positive correlation with diabetes
- **GenHlth**: Negative correlation
- **HighChol**: Positive correlation

## KNIME Workflows
The repository contains three main KNIME workflows:
- **Training workflow**: Model development and evaluation
- **Deployment workflow**: Production-ready model implementation
- **Data application workflow**: Complete data pipeline

## Future Development
- Expert domain consultation for additional relevant variables
- Dataset integration for enriched analysis
- Geographical comparison studies
- Model accuracy improvements

## Authors
Francesco Angiulli, Alice Parodi, Matteo Pasotti

## References
1. CDC: https://www.cdc.gov/diabetes/basics/diabetes.html
2. BRFSS: https://www.cdc.gov/brfss/index.html
3. KNIME: https://www.knime.com/
4. National Library of Medicine: https://pubmed.ncbi.nlm.nih.gov/29459239/
