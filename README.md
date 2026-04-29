
# Diabetes Readmission Prediction

Predicting 30-day hospital readmission for diabetic patients using machine learning on the UCI Diabetes 130-US hospitals dataset (101,766 encounters, 1999–2008).

## Motivation

Hospital readmission within 30 days is a key quality-of-care metric, monitored by regulatory bodies such as CMS (US) and equivalent European systems. Identifying patients at high risk of early readmission allows targeted interventions at discharge — medication reconciliation, early follow-up, transition-of-care programs — that have been shown to reduce readmission rates.

## Dataset

[Diabetes 130-US Hospitals for Years 1999-2008](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008), UCI Machine Learning Repository.

- 101,766 hospital encounters
- 71,518 unique patients
- 50 features (demographics, diagnoses, medications, lab results)
- Outcome: readmission category (NO / >30 days / <30 days)

## Methodological decisions

- **Task formulation**: binary classification, positive class = readmission within 30 days.
- **Encounter handling**: all encounters retained (mean 1.42 encounters/patient), preserving clinically high-risk frequent flyers.
- **Train-test split**: `GroupShuffleSplit` by `patient_nbr` to prevent patient-level leakage — a common but critical pitfall in this dataset.
- **Class imbalance**: ~89:11 ratio. Baseline approach with `class_weight='balanced'`; sample weights by patient and SMOTE explored as ablations.

## Project structure
```
diabetes-readmission-prediction/
├── data/raw/         # Source CSVs (gitignored)
├── notebooks/
│   └── 01_EDA.ipynb  # Exploratory data analysis
├── src/              # Reusable code (planned)
└── requirements.txt
```
## Status

🟡 In progress — currently in exploratory data analysis phase.

## Reproducing

(...to be filled in once data download script is written...)
