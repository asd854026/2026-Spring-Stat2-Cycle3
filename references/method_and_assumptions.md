# Method and Assumptions

## Selected Research Question

**Question 8: Sad or Hopeless Feeling and Current Cigarette Use**

Research question:

**Is the proportion of current cigarette use different between students who felt sad or hopeless and those who did not?**

## Selected Method

This project uses a **two-proportion z-test** because the response variable, current cigarette use, is recoded as a binary variable.

- Group variable: `sad_binary`
- Response variable: `smoker_binary`
- Method: two-proportion z-test
- Significance level: `alpha = 0.05`
- Test type: two-sided test

The difference is defined as:

`p_yes - p_no`

where:

- `p_yes` = current cigarette use proportion among students who felt sad or hopeless
- `p_no` = current cigarette use proportion among students who did not feel sad or hopeless

A positive difference means that the Sad/Hopeless: Yes group has a higher current cigarette use proportion.

## Hypotheses

- `H0: p_yes = p_no`
- `H1: p_yes != p_no`

The null hypothesis states that the two groups have the same current cigarette use proportion.  
The alternative hypothesis states that the two groups have different current cigarette use proportions.

## Confidence Interval

A 95% confidence interval is calculated for the difference in proportions:

`p_hat_yes - p_hat_no`

The confidence interval uses the standard error based on the two separate sample proportions.  
This interval is used to estimate the plausible range of the difference between the two group proportions.

## Hypothesis Test

The two-proportion z-test uses the **pooled proportion** when calculating the standard error under the null hypothesis.

In this analysis:

- Pooled proportion = `0.1952`
- Test statistic: `z = 15.0536`
- p-value: `< 0.0001`

## Assumptions Considered

### 1. Are the two groups independent?

**Answer:** Yes, reasonable.

The two groups are mutually exclusive: students are classified as either Sad/Hopeless: Yes or Sad/Hopeless: No. Each row represents one student survey response.

### 2. Is the response variable appropriate for the selected method?

**Answer:** Yes.

The response variable is `smoker_binary`, coded as:

- `1` = current cigarette use
- `0` = no current cigarette use

Because the response variable is binary, a two-proportion z-test is appropriate.

### 3. Are sample sizes large enough?

**Answer:** Yes.

The success and failure counts are large enough for the normal approximation used in the two-proportion z-test.

- Sad/Hopeless: Yes group: successes = `1,064`, failures = `2,790`
- Sad/Hopeless: No group: successes = `1,508`, failures = `7,812`

All success and failure counts are greater than 10.

### 4. Are there extreme outliers for quantitative variables?

**Answer:** Not applicable.

This project uses a binary response variable, not a quantitative response variable. Therefore, extreme outliers are not relevant for the main two-proportion analysis.

### 5. Is equal variance assumed or not?

**Answer:** Not applicable.

Equal variance is not assumed because this project uses a two-proportion z-test, not a two-sample t-test.

### 6. Missing and invalid values

Rows with missing or invalid values in `SadOrHopeless` or `CurrentCigaretteUse` are excluded from the main analysis.

The final valid sample size for the main Q8 analysis is:

- `n = 13,174`

### 7. Observational data caution

The YRBS data are observational survey data. Therefore, the result should be interpreted as an association, not as evidence of causation.

## Main Numerical Result

- `n_yes = 3,854`
- `x_yes = 1,064`
- `p_hat_yes = 0.2761`

- `n_no = 9,320`
- `x_no = 1,508`
- `p_hat_no = 0.1618`

- Difference = `0.1143`
- 95% CI = `[0.0983, 0.1302]`
- z statistic = `15.0536`
- p-value = `< 0.0001`
- Decision at `alpha = 0.05`: Reject `H0`

## Main Interpretation

The current cigarette use proportion was higher in the Sad/Hopeless: Yes group than in the Sad/Hopeless: No group.

The estimated difference was `0.1143`, meaning that the Sad/Hopeless: Yes group had about an **11.43 percentage-point higher** current cigarette use proportion than the Sad/Hopeless: No group.

The 95% confidence interval `[0.0983, 0.1302]` is entirely above 0, and the p-value is less than 0.0001. Therefore, there is statistically significant evidence that the current cigarette use proportion differs between the two groups.

This result shows an association between Sad/Hopeless status and current cigarette use, but it does not prove causation.

## Additional EDA Note

The additional EDA is exploratory and is not part of the main two-proportion inference test.

It compares two behavior domains:

1. **Substance-related risk behaviors**
   - current cigarette use
   - current alcohol use
   - current marijuana use

2. **Healthy diet behaviors**
   - daily fruit eating
   - daily green salad eating
   - daily other vegetable eating

The additional EDA uses:

- `substance_risk_count`
- `healthy_diet_count`
- `substance_behavior_combination`
- `healthy_diet_combination`

The goal is to describe whether students who felt sad or hopeless show different clustering patterns between substance-related risk behaviors and healthy diet behaviors.

In the healthy diet UpSet-style plot:

- `Salad` refers to daily green salad eating.
- `Vegetables` refers to daily other vegetable eating.

Because this additional EDA is exploratory and based on observational survey data, it should also be interpreted as association, not causation.
