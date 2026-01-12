# Medical Insurance Regional Analysis

## Overview
This project investigates whether there are statistically significant differences in medical insurance charges across four geographical regions in the United States: Northeast, Southeast, Northwest, and Southwest.

## Research Question
**Is there a statistically significant difference in the average medical insurance charges among the four geographical regions?**

## Dataset
The analysis uses an insurance dataset (`insurance.csv`) containing 1,337 records with the following features:
- **age**: Age of the insured individual
- **sex**: Gender of the insured
- **bmi**: Body Mass Index
- **children**: Number of children/dependents
- **smoker**: Smoking status
- **region**: Geographical region (northeast, northwest, southeast, southwest)
- **charges**: Medical insurance charges (target variable)

## Methodology

### Statistical Approach
The analysis employs **Welch's ANOVA** (one-way ANOVA with unequal variances) to test for differences in mean insurance charges across regions.

**Hypotheses:**
- **Null Hypothesis (H₀)**: There is no significant difference in the mean insurance charges across the four regions
- **Alternative Hypothesis (H₁)**: At least one region has a mean insurance charge that is significantly different from others

**Significance Level**: α = 0.05

## Requirements
```
pandas
numpy
scipy
```

## Installation
```bash
pip install pandas numpy scipy
```

## Usage
1. Ensure `insurance.csv` is in the same directory as the notebook
2. Open `Analysis.ipynb` in Jupyter Notebook or JupyterLab
3. Run all cells sequentially

## Results

### Regional Mean Charges
| Region    | Mean Charge ($) |
|-----------|-----------------|
| Northeast | 13,406.38       |
| Northwest | 12,450.84       |
| Southeast | 14,735.41       |
| Southwest | 12,346.94       |

### Statistical Test Results
- **F-Statistic**: 2.566
- **P-Value**: 0.0535

### Conclusion
With a p-value of 0.0535 (slightly above the 0.05 threshold), we **fail to reject the null hypothesis**. This indicates there is insufficient statistical evidence to conclude that insurance charges differ significantly across the four regions.

### Key Insights
- **Marginal Result**: The p-value is very close to the significance threshold, suggesting the differences are borderline
- **Highest Charges**: Southeast region shows the highest average charges ($14,735)
- **Lowest Charges**: Southwest region has the lowest average charges ($12,346)
- **Within-Group Variability**: High variance within regions prevents us from confirming that regional differences are not due to chance
- **Robust Testing**: Welch's ANOVA (with `equal_var=False`) accounts for unequal variances across regions, providing a more reliable test

## Project Structure
```
.
├── Analysis.ipynb      # Main analysis notebook
├── insurance.csv       # Dataset
└── README.md          # Readme file
```

---