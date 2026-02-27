---
title: "Ace the Space – Resume Scoring & Job Recommendation System"
date: 2025-03-01
summary: "NLP-powered resume scoring and job matching system using Sentence-BERT similarity plus experience/education fit to recommend best roles and identify gaps"
tags:
  - NLP
  - Machine Learning
  - Recommender Systems
  - BERT
  - Backend
  - Python
  - Data Engineering
tech_stack:
  - Python
  - Pandas
  - NumPy
  - Sentence-Transformers (all-MiniLM-L6-v2)
  - Scikit-learn
  - PyMuPDF
  - Seaborn
  - Matplotlib
links:
  - type: github
    url: https://github.com/garimamathur10/WageWizard
    label: Code
featured: true
status: "Prototype"
role: "Developer"
duration: "9 weeks"
team_size: 3
highlights:
  - "Matched 2,000 resumes to 24,542 job postings using Sentence-BERT cosine similarity"
  - "Built hybrid scoring: Skills (0.5) + Experience (0.3) + Education (0.2)"
  - "Estimated job experience from descriptions with regex + title-based inference"
  - "Trained an SVM classifier for high-match detection (Accuracy 0.985, F1 0.890)"

architecture:
  description: "Hybrid semantic + structured matching pipeline that scores resume-job fit and generates recommendations"
  components:
    - Resume Dataset + PDF Input
    - Data Cleaning + Feature Engineering
    - Sentence-BERT Embedding + Cosine Similarity (Skills vs Job Description)
    - Experience Requirement Estimation (Regex + Title Heuristics)
    - Education Requirement Extraction (Keyword Rules)
    - Weighted Final Match Score (0.5/0.3/0.2)
    - SVM High-Match Classifier
    - Top-N Job Recommendations + Deduplication
  diagram: |
    ┌─────────────────────┐
    │ Resume Dataset / PDF│
    └─────────┬───────────┘
              │
              ▼
    ┌─────────────────────┐       ┌──────────────────────┐
    │ Feature Extraction   │       │ Job Postings Dataset  │
    │ - Skills text        │       │ - Title, Description  │
    │ - Experience years   │       │ - Location, Company   │
    │ - Education level    │       └─────────┬────────────┘
    └─────────┬───────────┘                 │
              │                               ▼
              ▼                     ┌─────────────────────┐
    ┌─────────────────────┐         │ Sentence-BERT        │
    │ Structured Scoring   │         │ Embeddings           │
    │ - Exp fit score      │         │ + Cosine Similarity  │
    │ - Edu fit score      │         └─────────┬───────────┘
    └─────────┬───────────┘                   │
              └──────────────┬────────────────┘
                             ▼
                    ┌─────────────────────┐
                    │ Weighted Match Score │
                    │ (0.5/0.3/0.2)        │
                    └─────────┬───────────┘
                              ▼
                    ┌─────────────────────┐
                    │ Top Job Recs + SVM   │
                    └─────────────────────┘

content: |-
  Ace the Space is a resume scoring and job recommendation system that evaluates candidate profiles against job postings using a hybrid approach: semantic similarity for skills and weighted structured-fit scoring for experience and education.

  ## Overview

  Traditional keyword matching often misses strong candidates due to phrasing differences. This system uses Sentence-BERT embeddings to compare resume skills with job descriptions, then combines that with experience alignment and education requirements to compute a final match score. It also supports a resume PDF input flow to recommend top jobs directly from extracted text.

  ## Project Objectives

  1. Automate Resume Scoring – Use NLP to extract and analyze skills, job titles, and experience from resumes.
  2. Enhance Candidate-Job Matching – Match resumes with the most relevant job descriptions based on semantic similarity and role alignment.
  3. Identify Skill Gaps – Highlight missing skills in resumes required for top matches (future extension).
  4. Optimize Recruitment Efficiency – Reduce manual shortlisting by ranking candidates and surfacing high matches.
  5. Provide Personalized Job Recommendations – Recommend top roles for each resume based on fit scores.
  6. Evaluate & Improve Matching Accuracy – Measure performance with accuracy, precision, recall, and F1-score.

  ## Data

  **Resume dataset (2,000 records):**
  - Name, Job Title, Skills, Experience (Years), Education, Certification, Location

  **Job dataset (24,542 postings):**
  - Title, Description, Location, Company (company_name had many missing values)

  ## Data Cleaning

  - Filled missing resume certifications with `"No Certification"`.
  - Dropped job postings with missing descriptions.
  - Dropped salary-related columns with heavy missingness to keep the dataset focused on matching signals.

  ## EDA

  - Visualized distribution of resume experience (years).
  - Extracted and plotted top 10 most frequent skills across resumes.
  - Plotted top 10 job titles by frequency in job postings.

  ## Workflow

  ### Step 1: Skills Matching (Semantic Similarity)

  - Used `SentenceTransformer("all-MiniLM-L6-v2")`.
  - Encoded resume skills text and job descriptions into embeddings.
  - Computed cosine similarity to build a score matrix.

  **Output:**
  - `skills_df` with shape `(2000, 24542)`.

  ### Step 2: Experience Fit Scoring

  Estimated job required experience:
  - Regex extraction from job descriptions for patterns like `X years`, `X+ years`, `X yrs`, `experience`.
  - If missing, inferred from title:
    - Senior/Lead/Manager → random 6–10 years
    - Junior/Entry → random 0–2 years
    - Otherwise → filled with median

  Experience score logic:
  - job_exp=0 → 1.0
  - ±1 year → 1.0
  - ±3 years → 0.75
  - ±5 years → 0.5
  - otherwise → 0.1

  ### Step 3: Education Fit Scoring

  Resume education mapping:
  - Bachelor=1, Master/MBA=2, PhD/Doctorate=3

  Job education requirement extraction:
  - Keywords from job description: bachelor / master / phd.

  Education score logic:
  - resume >= required → 1.0
  - slightly under → 0.75 / 0.5
  - otherwise → 0.1

  ### Step 4: Weighted Final Score

  - Normalized Skills/Experience/Education scores using MinMaxScaler.
  - Combined with weights:
    - Skills 0.5
    - Experience 0.3
    - Education 0.2

  Final Score formula:
  `Final = 0.5*Skills + 0.3*Experience + 0.2*Education`

  ### Step 5: High-Match Classifier (SVM)

  Built a classification layer to label resume-job pairs as “high match”:
  - Label = 1 if Final Score > 0.7 else 0
  - Model: SVM (RBF kernel) with class_weight="balanced"

  **Performance:**
  - Accuracy: 0.9853
  - Precision: 0.8022
  - F1 Score: 0.8902
  - Recall improved for the minority “match” class using balanced weights.

  ### Step 6: Resume PDF → Top Job Recommendations

  - Extracted resume text from PDF using PyMuPDF.
  - Embedded full resume text and compared to job titles (or job text source).
  - Ranked and returned Top 5 unique job titles by similarity score.

  Example top matches (from a sample resume):
  - Data Analytics Engineer
  - Analytics Engineer
  - Sr. Analytics Engineer
  - Business Intelligence Developer
  - Sr. Data Intelligence Analyst

  ## Results

  - Scaled semantic similarity matching across 2,000 resumes and 24,542 job postings.
  - Produced ranked job recommendations using hybrid semantic + structured scoring.
  - Achieved strong high-match classification performance with SVM.
  - Enabled end-to-end flow from PDF resume → recommended roles.

  ## Challenges & Solutions

  ### Challenge 1: Missing / Noisy Requirements in Job Descriptions
  **Solution:** Built heuristic inference (regex + title signals) and fallback to median experience.

  ### Challenge 2: Scaling Similarity Computation
  **Solution:** Stored similarity matrix and sampled pairs for training to reduce compute/memory overhead.

  ### Challenge 3: Imbalanced Match Labels
  **Solution:** Used `class_weight="balanced"` in SVM to improve recall for positive matches.

  ## Future Improvements

  - Skill gap extraction (NER + keyword diff between job requirements and resume skills).
  - Replace heuristic experience extraction with a learned information extractor.
  - Improve scale with ANN retrieval (FAISS) instead of full matrix similarity.
  - Add Streamlit UI for interactive scoring and recommendations.
  - Add explainability (why a job matched: skills overlap, missing requirements, etc.).
---
