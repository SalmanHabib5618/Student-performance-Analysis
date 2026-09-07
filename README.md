<<<<<<< HEAD
# Student Performance Analysis

## Problem Statement
Schools collect attendance, study hours and parental background, but rarely know which
of those factors genuinely predict exam outcomes. This project analyzes exam results for
1,000 Pakistani students to find out which factors actually matter.

## Dataset
**Pakistani Students Performance in Exams** — 1,000 rows, 8 attributes:
`gender`, `province`, `parental_level_of_education`, `lunch`, `test_preparation_course`,
`math_score`, `reading_score`, `writing_score`.

- Raw file: `data/Pakistani_Students_Performance.csv`
- Cleaned file: `data/cleaned_students_performance.csv`

## Project Structure
```
Student_Performance_Analysis/
├── README.md
├── requirements.txt
├── data/
│   ├── Pakistani_Students_Performance.csv      # raw data
│   └── cleaned_students_performance.csv        # cleaned + encoded data
├── notebooks/
│   └── Student_Performance_Analysis.ipynb      # full analysis, end to end
├── visuals/
│   ├── 01_score_distributions.png
│   ├── 02_boxplots_by_test_prep.png
│   ├── 03_correlation_heatmap.png
│   ├── 04_avg_scores_by_prep.png
│   ├── 05_avg_score_by_parental_education.png
│   ├── 06_linear_regression_actual_vs_pred.png
│   ├── 07_confusion_matrix.png
│   ├── 08_feature_importance.png
│   └── 09_decision_tree_structure.png
└── models/
    ├── linear_regression_model.pkl
    ├── decision_tree_model.pkl
    └── model_metrics.json
```

## Data Cleaning
- Standardized categorical labels (trimmed whitespace, consistent casing).
- Checked for duplicate records (none found).
- Verified score ranges fall within the valid 0–100 bounds.
- Filled 647 missing `test_preparation_course` entries with `"Not Completed"`
  (a blank entry means the course was not taken, not that data is absent).
- Encoded `parental_level_of_education` as an ordinal variable
  (Primary or Below < Matric < Intermediate < Bachelor's < Master's).

## Data Visualization
- **Distribution plots** for math, reading, and writing scores.
- **Grouped box plots** comparing each subject's score distribution by test-preparation status.
- **Correlation heatmap** across the three score columns.
- Supplementary bar charts: average scores by test-prep status, and by parental education.

## Machine Learning Models
1. **Linear Regression** — estimates the math-score lift attributable to completing test
   preparation, controlling for gender, lunch type, and parental education.
   Test-prep coefficient ≈ **+7 points** (R² = 0.11, MAE = 7.78).
2. **Decision Tree Classifier** — predicts pass/fail (reading+writing average ≥ 70) from
   math score, test-prep status, and demographic features. **Accuracy ≈ 82%.**

## Business Insights
- Completing test preparation lifts average scores by roughly **7 points in math, 10.5 in
  reading, and 15.4 in writing** — the single most actionable lever schools have.
- Reading and writing scores correlate at **0.89** — tracking one is nearly as informative
  as tracking both, useful for lightweight reporting.
- Parental education has a marginal effect on scores (71.2 → 73.5 across education levels)
  and contributes under 1% of feature importance in the classifier — **intervention (test
  prep) beats background** as a predictor of outcomes.
- A simple, interpretable decision tree reaches ~82% accuracy using just a handful of
  features, showing schools don't need extensive data collection to flag at-risk students.

## Technologies Used
- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib
- Scikit-learn
- Jupyter

## How to Run
```bash
pip install -r requirements.txt
jupyter notebook notebooks/Student_Performance_Analysis.ipynb
```
=======
# Student-performance-Analysis
>>>>>>> 5ee924ee378f9b5b4a1c2555dc0907a5d0fb81d3
