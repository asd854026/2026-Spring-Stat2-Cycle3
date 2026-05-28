# Project Cycle 3 - Two-Sample Inference

## Group Information
- Group number: 27
- Member names (Student ID / Name / GitHub ID):
  
  112370216 / 蘇榮盛 / asd854026
  
  111370138 / 吳丞宥 / 111370138

## Selected Research Question
**Question 8: Sad or Hopeless Feeling and Current Cigarette Use**

Research question: **Is the proportion of current cigarette use different between students who felt sad or hopeless and those who did not?**

------------------------------------------------------------------------------------------------

Additional EDA: **Do students who felt sad or hopeless show stronger clustering of substance-related health-risk behaviors?**

Note: In this extension, clustering means that multiple substance-related health-risk behaviors are reported by the same student. The three behaviors are current cigarette use, current alcohol use, and current marijuana use.

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

- code 1 = Non-smoker (0 days)
- codes 2-3 = Light (1-5 days)
- codes 4-5 = Moderate (6-19 days)
- codes 6-7 = Frequent (20-30 days)

### Additional EDA Variables
The additional EDA uses three binary substance-related health-risk indicators:

- `smoker_binary` = current cigarette use
- `alcohol_binary` = current alcohol use
- `marijuana_binary` = current marijuana use

Two additional variables are created for the extension:

- `health_risk_behavior_count` = `smoker_binary + alcohol_binary + marijuana_binary`, ranging from 0 to 3
- `behavior_combination` = the exact combination of behaviors reported, such as `None`, `Alcohol only`, `Cigarette + Alcohol`, or `All three`

The health-risk behavior count and behavior combinations are created only when all three indicators are valid.

## Method
Because the main response variable is binary, this project uses a **two-proportion z-test** and a **95% confidence interval for the difference in proportions**.

The difference is defined as:

`p_yes - p_no`

where:
- `p_yes` = current cigarette use proportion among students who felt sad or hopeless
- `p_no` = current cigarette use proportion among students who did not feel sad or hopeless

The additional EDA is exploratory. It is used to describe substance-related health-risk behavior clustering and is not part of the main inference test.

## Main Result
- Valid analysis sample size: **13,174**
- Sad/Hopeless Yes: **0.2761** current cigarette use proportion
- Sad/Hopeless No: **0.1618** current cigarette use proportion
- Estimated difference: **0.1143** using `p_yes - p_no`
- 95% CI for the difference: **[0.0983, 0.1302]**
- z statistic: **15.0536**
- p-value: **< 0.0001**

## Short Final Conclusion
At alpha = 0.05, we reject the null hypothesis. Students who felt sad or hopeless had a statistically significantly higher proportion of current cigarette use than students who did not. This result should be interpreted as an association, not evidence of causation.

## Additional EDA Result
The additional EDA suggests stronger clustering of substance-related health-risk behaviors among students who felt sad or hopeless.

Key exploratory findings:

- Sad/Hopeless Yes group mean health-risk behavior count: **1.09**
- Sad/Hopeless No group mean health-risk behavior count: **0.72**
- Sad/Hopeless Yes group with two or more behaviors: **32.8%**
- Sad/Hopeless No group with two or more behaviors: **20.0%**
- `All three` behaviors appeared in **15.6%** of the Sad/Hopeless Yes group and **8.1%** of the Sad/Hopeless No group.

These additional findings are exploratory and should also be interpreted as association, not causation.

## Notebook Structure
1. `01_DataCheck.ipynb` - load raw data, check variables, recode variables, create processed-only datasets.
2. `02_EDA_Main.ipynb` - main Q8 EDA using group summary, proportion gap plot, binary smoking status distribution, and smokers-only frequency difference plot.
3. `02_EDA_Additional.ipynb` - exploratory EDA for substance-related health-risk behavior clustering using behavior combinations, an UpSet-style combination plot, and a 2+ behaviors summary.
4. `03_Inference.ipynb` - two-proportion z-test, 95% CI, and inference summary.
5. `04_Interpretation.ipynb` - final interpretation in context.

## Project Structure
```text
2026-Spring-Stat2-Cycle3/
  README.md
  data/
    raw/
      YRBS_2007.csv
    processed/
      yrbs_cycle3_q8_processed_only.csv
      yrbs_cycle3_health_risk_processed_only.csv
  notebooks/
    01_DataCheck.ipynb
    02_EDA_Main.ipynb
    02_EDA_Additional.ipynb
    03_Inference.ipynb
    04_Interpretation.ipynb
  outputs/
    figures/
    tables/
    summary/
  report/
  references/
    variable_definitions.md
    recoding_rules.md
    method_and_assumptions.md
```
