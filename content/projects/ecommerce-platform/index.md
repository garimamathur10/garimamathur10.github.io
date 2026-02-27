---
title: "SchedWiz – AI Study Scheduler"
date: 2025-06-01
summary: "AI-powered adaptive study planner using ML and real-time scheduling to personalize student learning"

tags:
  - Machine Learning
  - Backend
  - Data Systems
  - Education Tech

tech_stack:
  - Python
  - PyTorch
  - TensorFlow
  - PySpark
  - Streamlit
  - Pandas
  - Seaborn
  - Multithreading


links:
  - type: github
    url: [https://github.com/garimamathur10/SchedWiz]
    label: Code
  - type: live
    url: [https://github.com/garimamathur10/SchedWiz/blob/main/Demo_SchedWiz_BDA_Project.mp4]
    label: Demo
featured: true
status: "Live"
role: "ML Developer"
duration: "3 months"
team_size: 5

highlights:
  - "Served 32k+ students with adaptive schedules"
  - "73.3% prediction accuracy"
  - "Real-time personalized planning"
  - "12.6% causal improvement in performance"

overview: |
  SchedWiz is an AI-powered study scheduler that personalizes, adapts, and optimizes study plans to boost student productivity and academic performance.
  It transforms academic performance data into dynamic learning schedules that prioritize weaker subjects and upcoming exams.

methodology: |
  Uses ML, PySpark, and an interactive Streamlit interface:
  - Ingests scores, exam dates, and difficulty levels
  - Performs EDA with Pandas and Seaborn
  - Predicts performance via MLP (PyTorch + TensorFlow)
  - Multithreaded scheduling pipeline
  - Applies causal inference (PSM + DiD)

results: |
  - 73.3% prediction accuracy
  - 32,000+ students served
  - 12.6% performance improvement
  - Real-time scheduling via concurrency

architecture:
  description: "System architecture for real-time adaptive study plan generation"
  diagram: |
    ┌─────────────┐     ┌──────────────┐     ┌─────────────┐
    │ Streamlit UI│────▶│ ML Pipeline  │────▶│ Study Plan  │
    └─────────────┘     │  (PySpark)   │     └─────────────┘
                        └──────┬───────┘
                               │
                        ┌──────▼───────┐
                        │ Scheduler    │
                        │ Multithreaded│
                        └──────────────┘

challenges:
  - name: Static Planning
    solution: ML-driven dynamic scheduling

  - name: Measuring Impact
    solution: Causal inference (PSM + DiD)

  - name: Real-Time Responsiveness
    solution: Concurrency-based scheduling pipeline

tech_details:
  ml:
    - PyTorch
    - TensorFlow
    - PySpark
  backend:
    - Python
    - Multithreading
    - Data Pipelines
  analytics:
    - Pandas
    - Seaborn
  interface:
    - Streamlit

future_improvements:
  - Mobile interface
  - Progress dashboard
  - Collaborative planning
  - Recommendation engine

lessons_learned:
  - Adaptive planning improves engagement
  - Causal methods strengthen ML insights
  - Concurrency improves responsiveness
  - Structured pipelines increase reliability
---
