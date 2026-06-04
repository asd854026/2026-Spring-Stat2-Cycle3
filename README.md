# Project Cycle 3 - Two-Sample Inference

## Project Repository
https://github.com/asd854026/2026-Spring-Stat2-Cycle3

## Presentation Video
https://youtu.be/HBRwdPVmvFI

## Group Information
- Group number: 27
- Member names: 112370216蘇榮盛, 111370138吳丞宥

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

The hypotheses are:

- **H₀:** `p_yes - p_no = 0`
- **H₁:** `p_yes - p_no ≠ 0`

The null hypothesis means that the two groups have the same current cigarette use proportion.  
The alternative hypothesis means that the two groups have different current cigarette use proportions.

## Main Result
- Valid analysis sample size: **13,174**
- Sad/Hopeless Yes: **0.2761** current cigarette use proportion
- Sad/Hopeless No: **0.1618** current cigarette use proportion
- Estimated difference: **0.1143**
- 95% CI for the difference: **[0.0983, 0.1302]**
- z statistic: **15.0536**
- p-value: **< 0.0001**

## Short Final Conclusion
At alpha = 0.05, we reject the null hypothesis. Students who felt sad or hopeless had a statistically significantly higher proportion of current cigarette use than students who did not. This is an association, not evidence of causation.

## Additional EDA
The main inference result remains Question 8. An additional exploratory EDA is included to compare two behavior domains:

**Additional EDA question:**  
**Do students who felt sad or hopeless show different clustering patterns between substance-related risk behaviors and healthy diet behaviors?**

### Substance-related risk behavior indicators
- `smoker_binary`: current cigarette use
- `alcohol_binary`: current alcohol use
- `marijuana_binary`: current marijuana use
- `substance_risk_count`: sum of the three indicators, ranging from 0 to 3
- `substance_behavior_combination`: which substance-related behaviors were reported together, such as `Alcohol only`, `Cigarette + Alcohol`, `All three`, or `None`

### Healthy diet behavior indicators
- `fruit_daily_binary`: daily fruit eating
- `green_salad_daily_binary`: daily green salad eating
- `other_vegetable_daily_binary`: daily other vegetable eating
- `healthy_diet_count`: sum of the three indicators, ranging from 0 to 3
- `healthy_diet_combination`: which healthy diet behaviors were reported together, such as `Fruit only`, `Fruit + Salad`, `All three`, or `None`

This additional EDA is exploratory only and is not the main two-sample inference test.

## Additional EDA Main Takeaway
The additional EDA suggests that substance-related risk behaviors show a clearer clustering pattern among students who felt sad or hopeless. In contrast, healthy diet behavior count does not show the same clear separation between Sad/Hopeless groups.

## Notebook Structure
1. `01_DataCheck.ipynb` - load raw data, check variables, recode main and additional EDA variables, and save processed-only datasets.
2. `02_EDA_Main.ipynb` - descriptive summaries and main Q8 visualizations, including the proportion gap plot, binary smoking status distribution, and smokers-only frequency difference plot.
3. `02_EDA_Additional.ipynb` - exploratory additional EDA comparing substance-related risk behavior clustering and healthy diet behavior clustering using UpSet-style combination plots and behavior count profiles.
4. `03_Inference.ipynb` - two-proportion z-test, 95% confidence interval, and inferential result summary.
5. `04_Interpretation.ipynb` - final interpretation in context.
