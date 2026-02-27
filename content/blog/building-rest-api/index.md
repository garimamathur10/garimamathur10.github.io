---
title: "Building SchedWiz: A Big Data-Driven Adaptive Study Scheduling System"
date: 2025-06-01
summary: "How I built SchedWiz in my Big Data class using PySpark + ML to turn large-scale learning behavior data into adaptive, real-time study schedules"
tags:
  - Big Data
  - PySpark
  - Machine Learning
  - Predictive Analytics
  - Causal Inference
  - Education Tech
authors:
  - me
featured: true

project:
  name: "SchedWiz – AI Study Scheduler"
  role: "ML Developer"
  duration: "3 months"
  team_size: 5

tech_stack:
  - Python
  - PySpark
  - PyTorch
  - TensorFlow
  - Streamlit
  - Pandas
  - Seaborn
  - Multithreading

links:
  - type: github
    url: https://github.com/yourrepo/schedwiz
    label: Code

highlights:
  - "Built as part of a Big Data coursework project using the OULAD dataset (32k+ students)"
  - "73.3% test accuracy for student outcome prediction (Fail/Pass/Distinction)"
  - "Generated personalized, adaptive schedules in real-time via multithreaded orchestration"
  - "Measured 12.6% causal lift in outcomes for high early engagement using PSM + DiD"

content: |-
  Building intelligent systems is not only about training models — it’s about using data to drive decisions at scale. SchedWiz was built as part of my Big Data coursework, where the goal was to translate large-scale learning behavior data into actionable study schedules.

## Overview

  Students often struggle with static schedules, inconsistent habits, and difficulty prioritizing tasks. Traditional study planning rarely adapts to changing performance and upcoming exam timelines. SchedWiz addresses this by converting academic performance and engagement signals into dynamic, personalized study plans.

  Students enter key details (scores, exam dates, subject difficulty, available hours) through a Streamlit interface. The system predicts academic outcomes and generates an adaptive schedule that prioritizes weak subjects and urgent exams, updating as inputs change.

## Big Data Class Connection

The project was designed around Big Data principles:
- **Large-scale processing** using PySpark for joins, aggregations, feature engineering, and scalable preprocessing.
- **Heterogeneous data integration** combining demographics, assessments, and behavioral engagement signals.
- **Decision-making at scale** by translating model outputs into scheduling actions.
- **Evaluation beyond accuracy** by measuring causal impact of early engagement.

## Dataset & Data Strategy

**Dataset:** Open University Learning Analytics Dataset (OULAD)
- 32,000+ students
- Student demographics, assessment results, course structure, VLE engagement logs

**Outcome Variable:**
- Final result: Fail / Pass / Distinction (multi-class classification)

**Key Explanatory Features (examples):**
- Performance: avg_score, last_score, weighted_score, score_trend
- Engagement: total_clicks, active_days, click_variability
- Behavioral windows: clicks_first_14_days, clicks_last_7_days
- Demographics/context: age_band, highest_education, imd_band

## Analytics Framework

### Exploratory Analytics
- Distribution of scores across demographics and modules
- Engagement patterns over time (weekly/cumulative)
- Correlation analysis and outlier detection
- Tools: Pandas + PySpark aggregations, plots via Seaborn

### Predictive Analytics
- **MLP (PyTorch/TensorFlow)** trained on engineered features
- **Spark ML pipelines** (e.g., Gradient Boosted Trees) for tabular baselines
- Evaluation: accuracy, precision/recall, class-wise F1

### Causal Analytics
- Propensity Score Matching (PSM) + Difference-in-Differences (DiD)
- Used to estimate the effect of **early engagement** on outcomes

## System Architecture

architecture:
  description: "End-to-end adaptive scheduling pipeline powered by predictive modeling and decision optimization"
  components:
    - Student Input Layer (Streamlit UI)
    - Data Processing Layer (PySpark)
    - ML Prediction Layer (MLP Classifier)
    - Decision Engine (Scheduler Agent)
    - Output Layer (Personalized Study Plan)
  diagram: |
    ┌─────────────┐     ┌──────────────┐     ┌─────────────┐
    │ Streamlit UI│────▶│ ML Pipeline  │────▶│ Risk Class  │
    └─────────────┘     │  (PySpark)   │     └─────────────┘
                        └──────┬───────┘
                               │
                        ┌──────▼───────┐
                        │ Scheduler    │
                        │ Multithreaded│
                        └──────┬───────┘
                               │
                        ┌──────▼───────┐
                        │ Study Plan   │
                        └──────────────┘

links:
  - type: github
    url: https://github.com/yourrepo/schedwiz
    label: Code

highlights:
  - "Built using OULAD dataset (32k+ students)"
  - "73.3% outcome prediction accuracy"
  - "Real-time adaptive scheduling"
  - "12.6% causal improvement observed"

content: |-
  SchedWiz was developed as part of my Big Data coursework to transform large-scale student learning data into personalized study plans.

  Students struggle with rigid schedules and poor prioritization. This system uses predictive analytics and behavioral data to dynamically generate optimized study timelines.

  ## Big Data Approach

  The system leverages:

  - PySpark for scalable preprocessing
  - Machine learning for academic risk prediction
  - Scheduling logic for decision-making
  - Causal inference to measure impact

  ## Dataset

  Open University Learning Analytics Dataset (OULAD)

  Key features:
  - Performance metrics
  - Engagement signals
  - Behavioral trends
  - Demographic context

  ## Analytics

  Exploratory → Predictive → Causal

  - MLP for outcome classification
  - Spark pipelines for scalability
  - PSM + DiD for engagement impact

  
  ## Challenges & Solutions
  
  ### Challenge 1: Static Study Planning
  **Problem:** Traditional schedules do not adapt to changing performance or deadlines  
  **Solution:** Built ML-driven prioritization and dynamic hour allocation based on predicted risk + exam proximity
  
  ### Challenge 2: Measuring True Impact
  **Problem:** Accuracy alone doesn’t prove schedules improve outcomes  
  **Solution:** Added causal evaluation using PSM + DiD to estimate engagement-driven improvements
  
  ### Challenge 3: Responsiveness at Scale
  **Problem:** Scheduling logic must remain fast as data and users scale  
  **Solution:** Implemented concurrency-aware orchestration and cache-aware scheduling logic

  ## Results

  - **Prediction Accuracy:** 73.3% test accuracy (74.98% training accuracy)
  - **Scale:** modeled 32,000+ students (OULAD)
  - **Impact:** 12.6% estimated lift in outcomes for high early engagement
  - **Reliability:** added schema validation and data quality checks to reduce noisy schedule outputs

  ## Future Improvement 

  - Improve “Distinction” prediction (address class imbalance)
  - Add real-time schedule reshuffling from continuous signals (engagement + assessments)
  - LMS integration for real-time data ingestion
  - Progress dashboard + personalized recommendations

  ## Lessons Learned

  - Big Data value comes from combining heterogeneous signals into actionable decisions
  - Causal evaluation increases confidence beyond predictive accuracy
  - Concurrency and orchestration matter for real-time user-facing planning systems
  - Reliability (validation, data quality) is essential before scaling to production
---
