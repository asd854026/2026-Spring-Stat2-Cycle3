# Project Cycle 3 - Two-Sample Inference Demo / Formal Draft

## Group Information

- Group number: 27
- Member names: 112370216蘇榮盛, 111370138吳丞宥
- Dataset: `YRBS_2007.csv`, `yrbs_2007_cycle3_q8_cleaned.csv`
- Selected question: **Question 8 - Sad or Hopeless Feeling and Current Cigarette Use**

## Research Question

**Is the proportion of current cigarette use different between students who felt sad or hopeless and those who did not?**

## Variables

- Group variable: `SadOrHopeless`
  - `1` = felt sad or hopeless for two or more weeks in a row
  - `2` = did not feel sad or hopeless
- Response variable: `CurrentCigaretteUse`
  - success = codes `2-7` = currently used cigarettes on at least 1 day
  - failure = code `1` = did not currently use cigarettes

## Method Used

Because the response variable is binary, this project uses a **two-proportion z-test** and a **95% confidence interval for the difference in proportions**.

Difference is defined as:

```text
p_yes - p_no
```

where:

- `p_yes` = proportion of current cigarette use among students who felt sad or hopeless
- `p_no` = proportion of current cigarette use among students who did not feel sad or hopeless

## Main Results

| group                        |   sample_size |   current_cigarette_users |   proportion | proportion_percent   |
|:-----------------------------|--------------:|--------------------------:|-------------:|:---------------------|
| Felt sad or hopeless         |          3854 |                      1064 |       0.2761 | 27.61%               |
| Did not feel sad or hopeless |          9320 |                      1508 |       0.1618 | 16.18%               |

## Statistical Output

- Estimated difference: **0.1143** = **11.43 percentage points**
- 95% CI for difference: **[0.0983, 0.1302]** = **[9.83, 13.02] percentage points**
- Test statistic: **z = 15.0536**
- p-value: **< 0.0001**
- Significance level: **alpha = 0.05**
- Decision: **Reject H0**

## Short Final Conclusion

The sample proportion of current cigarette use was higher among students who felt sad or hopeless (27.6%) than among students who did not (16.2%). The estimated difference was about **11.43 percentage points**. Since the p-value was **< 0.0001**, we reject the null hypothesis at the 0.05 level. There is strong evidence that the proportion of current cigarette use differs between the two groups. This is an association only and should not be interpreted as a causal relationship.

## Project Structure

```text
project-cycle-3-q8-real/
  README.md
  data/
    raw/
      YRBS_2007.csv
    processed/
      yrbs_2007_cycle3_q8_cleaned.csv
  notebooks/
    01_cycle3_q8_analysis.ipynb
  outputs/
    figures/
    tables/
    summary/
  report/
  references/
```
