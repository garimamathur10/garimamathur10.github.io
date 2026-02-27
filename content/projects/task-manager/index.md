---
title: "WageWizard – Salary Prediction System"
date: 2026-02-01
summary: "ML-powered salary prediction platform that helps graduates set realistic expectations and make data-driven career decisions"
tags:
  - Machine Learning
  - Predictive Analytics
  - Career Tech
  - Regression
  - Decision Intelligence
  - ML 
authors:
  - me
featured: true

project:
  name: "WageWizard"
  role: "Backend Developer"
  duration: "2 months"
  team_size: 2

tech_stack:
  - Python
  - Scikit-learn
  - Random Forest
  - Pandas
  - NumPy
  - Streamlit
  - Matplotlib
  - Joblib

links:
  - type: github
    url: https://github.com/garimamathur10/WageWizard
    label: Code

highlights:
  - "Built end-to-end ML pipeline from EDA to deployment"
  - "Random Forest Regressor achieved R² = 0.98"
  - "Interactive salary prediction via Streamlit"
  - "Personalized career guidance based on predicted salary gap"

architecture:
  description: "Real-time decision-support system for early-career salary prediction"
  components:
    - User Profile Input (Education, Role, Experience)
    - Data Preprocessing Pipeline
    - ML Prediction Engine (Random Forest)
    - Recommendation Layer
    - Output Dashboard (Predicted Salary + Insights)
  diagram: |
    ┌───────────────┐
    │ User Input UI │
    └──────┬────────┘
           │
    ┌──────▼────────┐
    │ Preprocessing │
    │ (Encoding +   │
    │ Scaling)      │
    └──────┬────────┘
           │
    ┌──────▼────────┐
    │ ML Model      │
    │ Random Forest │
    └──────┬────────┘
           │
    ┌──────▼────────┐
    │ Salary Output │
    │ + Insights    │
    └───────────────┘

content: |-
  WageWizard is an AI-powered salary prediction system designed to help fresh graduates and early-career professionals make informed career decisions.

  Many job seekers struggle with unclear salary expectations and limited personalized guidance. WageWizard transforms profile data into actionable insights using predictive analytics.

  ## Business Objective

  The system predicts expected starting salary after securing a job offer using:

  - Education
  - Experience
  - Role
  - Profile attributes

  As described in the ML design canvas :contentReference[oaicite:1]{index=1}, predictions help:

  - Set realistic expectations
  - Guide skill-building decisions
  - Support career counseling

  ## ML Pipeline

  End-to-end workflow:

  ### Data Preparation
  - Kaggle salary dataset used
  - Missing values handled
  - Categorical encoding applied
  - Numerical scaling implemented

  ### Exploratory Data Analysis
  Identified key salary drivers:

  - Experience
  - Education
  - Job Role

  ### Model Development
  Models tested:

  - Linear Regression
  - XGBoost
  - Random Forest

  Final Selection:
  - Random Forest Regressor

  Performance:
  - R² = 0.98
  - MAE ≈ $2,880

  ## Decision Intelligence Layer

  Predicted salary enables:

  - Career planning support
  - Skill gap identification
  - Guidance toward internships or further education

  ## Deployment

  - Model exported using `.pkl`
  - Streamlit-ready interface
  - Real-time predictions with low latency

  ## Monitoring

  Model KPIs:

  - Target R² > 0.95
  - MAE < $5,000
  - Low prediction variance

  Future monitoring includes:

  - User satisfaction
  - Accuracy validation against actual salaries

  ## Results

  - High prediction accuracy (R² = 0.98)
  - Real-time salary estimation
  - Actionable career insights
  - Scalable architecture for future API or university portal integration

  ## Future Improvements

  - Integration with job platforms (LinkedIn, Glassdoor APIs)
  - Fairness auditing via SHAP
  - Continuous retraining with new salary data
  - Conversational chatbot interface

  ## Lessons Learned

  - Predictive models can directly support decision-making
  - Interpretability matters in career guidance systems
  - Real-time feedback improves user trust
  - ML becomes impactful when tied to user outcomes
---
