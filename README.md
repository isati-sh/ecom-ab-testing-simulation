# A/B Testing Simulation — E‑Commerce Conversion Study

## Overview
This project simulates a real A/B test for an e‑commerce website to evaluate whether a new landing page (treatment) improves user conversion compared to the original one (control).

---

## Project Objectives
1. **Profile the dataset** to assess data quality and integrity  
2. **Perform A/B testing** using statistical hypothesis testing (Z‑test for proportions)  
3. **Measure lift and significance** between control and treatment groups  
4. **Model user conversion probability** with Logistic Regression  
5. **Interpret model coefficients** to extract business insights

---

## Dataset
Two CSV files were used:
- `ab_data.csv`: contains experiment group, landing page, and conversion label  
- `countries.csv`: maps each user to a country  

After merging on `user_id`, the resulting dataset includes:
| Column | Description |
|--------|--------------|
| `user_id` | Unique identifier of a user |
| `group` | Experiment group (`control` or `treatment`) |
| `landing_page` | Page version the user saw |
| `converted` | 1 if the user converted, 0 otherwise |
| `country` | Country of the user |

---

## Tech Stack
- **Languages**: Python (pandas, numpy, matplotlib, seaborn)
- **Statistical Analysis**: `scipy`, `statsmodels`
- **Machine Learning**: `scikit‑learn`
- **Visualization**: `matplotlib`, `seaborn`, `plotly`
- **Notebook Reports**: `ydata‑profiling`

---

## Project Structure
```
ecommerce_ab_testing/
│
├── data/
│   ├── ab_data.csv
│   ├── countries.csv
│   └── merged_ab_test.csv
│
├── notebooks/
│   ├── 01_data_profiling.ipynb
│   ├── 02_ab_testing_analysis.ipynb
│   └── 03_predictive_modeling.ipynb
│
├── reports/
│   ├── ab_testing_data_profiling_report.html
│   ├── AB_Test_Summary_Report.pdf
│
├── README.md
└── requirements.txt
```

---

## Key Steps

### 01 Data Profiling
Used **ydata‑profiling** to automatically analyze missing values, distributions, and correlations.

### 02 A/B Significance Testing
- Defined hypotheses:  
  - H₀: Conversion rate (control) = Conversion rate (treatment)  
  - H₁: Conversion rate (treatment) > Conversion rate (control)
- Performed **Z‑test for proportions**
- Visualized conversion lift by group and by country

### 03 Predictive Modeling
- Built a **Logistic Regression** model to estimate conversion probability  
- Encoded categorical variables (group, country) using One‑Hot Encoding  
- Evaluated model with ROC‑AUC and confusion matrix  
- Interpreted feature coefficients to understand conversion drivers

---


## License
This project is open for educational and portfolio purposes only.  
Feel free to fork and adapt it for your own learning or interview preparation.

