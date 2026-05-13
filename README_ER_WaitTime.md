# Emergency Department Wait Time Analysis

A full data science pipeline — from exploratory analysis through to predictive modelling — applied to emergency department (ED) patient data. The goal: understand what drives wait times and build a model that can predict them.

## Problem Statement

Long ED wait times are a significant challenge for healthcare systems. This project investigates which factors (staffing levels, urgency, time of day, season, region) most influence how long patients wait, and builds regression models to predict total wait time in minutes.

## Dataset

- **Source:** ER Wait Time Dataset (hospital patient records)
- **Key features:**
  - `urgency_level` — Low / Medium / High / Critical
  - `time_of_day`, `day_of_week`, `season`, `region`
  - `nurse-to-patient_ratio`, `specialist_availability`
  - `time_to_triage_(min)`, `time_to_medical_professional_(min)`
  - `patient_satisfaction`, `patient_outcome`
  - `total_wait_time_(min)` — **target variable**

## Project Structure

```
├── er_waittime_analysis.ipynb     # Full pipeline: EDA + modelling in one notebook
└── ER_Wait_Time_Dataset.csv       # Dataset
```

## Methodology

### Exploratory Data Analysis
- Data cleaning: standardised column names, checked for nulls and duplicates
- Feature engineering: extracted `hour`, `day_of_week`, `month` from visit datetime
- Label encoding of categorical features for downstream modelling
- Visualisations:
  - Boxplot: wait time by urgency level (Low → Critical)
  - Bar chart: average wait time by time of day
  - Line chart: average wait time by day of week
  - Grouped bar chart: seasonal wait time variation by region
  - Correlation heatmap across all numerical features

### Predictive Modelling
- **Models compared:** Linear Regression vs Random Forest Regressor
- **Preprocessing pipeline:** `StandardScaler` for numerical features, `OneHotEncoder` for categorical features, assembled via `ColumnTransformer` + `sklearn Pipeline`
- **Evaluation metrics:** RMSE and R²
- **Hyperparameter tuning:** `GridSearchCV` (5-fold CV) on Random Forest (`n_estimators`, `max_depth`, `min_samples_split`)
- Best model selected and visualised with predicted vs actual scatter plot

## Key Findings

| Model | RMSE | R² |
|-------|------|----|
| Linear Regression | 24.75 | 0.8683 |
| Random Forest (baseline) | 18.78 | 0.9242 |
| Random Forest (tuned) | 18.37 | 0.9274 |

- Urgency level is the strongest driver of wait time, with Critical patients waiting significantly longer than Low urgency patients
- Wait times peak during evening hours and are highest on weekends
- Seasonal variation differs by region, suggesting staffing patterns may not match demand
- Tuned Random Forest (R² = 0.9274) significantly outperformed Linear Regression (R² = 0.8683), confirming non-linear relationships between staffing ratios and wait times

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3 | Core language |
| pandas, NumPy | Data manipulation |
| Matplotlib, Seaborn | Visualisation |
| scikit-learn | Modelling, pipelines, GridSearchCV |

## How to Run

```bash
# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn

# Open the notebook
jupyter notebook er_waittime_analysis.ipynb
```

> **Note:** Ensure `ER_Wait_Time_Dataset.csv` is in the same directory as the notebook before running.

## Author

**Prashant Shrestha**  
Master of Science in Data Science — University of Adelaide (2025)  
[LinkedIn](https://linkedin.com/in/preheria)
