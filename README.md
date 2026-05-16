# Project Cycle 3 - Two-Sample Inference

## Group Information
- Group number: 27
- Member names: 112370216蘇榮盛,111370138吳丞宥

## Selected Research Question
**Question 8: Sad or Hopeless Feeling and Current Cigarette Use**

Research question: **Is the proportion of current cigarette use different between students who felt sad or hopeless and those who did not?**

## Variables

### Group Variable
- Original variable: `SadOrHopeless`
- Recoded variable: `sad_binary`
- `1` = felt sad or hopeless
- `0` = did not feel sad or hopeless

### Response Variable
- Original variable: `CurrentCigaretteUse`
- What it measures: number of days the student smoked cigarettes during the past 30 days.
- Recoded binary response: `smoker_binary`
- `0` = code 1, no smoking in the past 30 days
- `1` = codes 2-7, smoked cigarettes on at least 1 day in the past 30 days

### EDA-only Grouped Response Detail
A grouped version of `CurrentCigaretteUse` is also created for exploratory visualization only:

- code 1 = No current smoking (0 days)
- codes 2-3 = Light (1-5 days)
- codes 4-5 = Moderate (6-19 days)
- codes 6-7 = Frequent (20-30 days)

## Method
Because the main response variable is binary, this project uses a **two-proportion z-test** and a **95% confidence interval for the difference in proportions**.

The difference is defined as:

`p_yes - p_no`

where:
- `p_yes` = current cigarette use proportion among students who felt sad or hopeless
- `p_no` = current cigarette use proportion among students who did not feel sad or hopeless

## Main Result
- Valid analysis sample size: **13,174**
- Sad/Hopeless Yes: **27.6%** current cigarette use
- Sad/Hopeless No: **16.2%** current cigarette use
- Estimated difference: **11.43 percentage points**
- 95% CI: **[9.83, 13.02] percentage points**
- z statistic: **15.0536**
- p-value: **< 0.0001**

## Short Final Conclusion
At alpha = 0.05, we reject the null hypothesis. Students who felt sad or hopeless had a statistically significantly higher proportion of current cigarette use than students who did not. This is an association, not evidence of causation.

## Notebook Structure
This project follows a Cycle 2-style notebook workflow:

1. `01_DataCheck.ipynb` - load data, check variables, document detailed CurrentCigaretteUse coding, recode variables, save cleaned data.
2. `02_EDA.ipynb` - descriptive summaries and group comparison visuals.
3. `03_Inference.ipynb` - two-proportion z-test, 95% CI, and inferential result plot.
4. `04_Interpretation.ipynb` - final interpretation in context.

## Project Structure
```text
project-cycle-3/
  README.md
  data/
    raw/
      YRBS_2007.csv
    processed/
      yrbs_cycle3_q8_cleaned.csv
  notebooks/
    01_DataCheck.ipynb
    02_EDA.ipynb
    03_Inference.ipynb
    04_Interpretation.ipynb
  outputs/
    figures/
    tables/
    summary/
  report/
  references/
```
