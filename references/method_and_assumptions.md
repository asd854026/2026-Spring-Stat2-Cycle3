# Method and Assumptions

## Selected Method

This project uses a **two-proportion z-test** because the main response variable, current cigarette use, is binary after recoding.

The main comparison is between:

- students who felt sad or hopeless
- students who did not feel sad or hopeless

## Hypotheses

- H0: `p_yes = p_no`
- H1: `p_yes != p_no`

where:

- `p_yes` = current cigarette use proportion among students who felt sad or hopeless
- `p_no` = current cigarette use proportion among students who did not feel sad or hopeless

## Pooled Proportion for Hypothesis Test

For the two-proportion z-test, the pooled proportion is used when calculating the standard error under the null hypothesis. In this analysis, the pooled proportion was 0.1952.

## Confidence Interval

A 95% confidence interval is calculated for the difference in proportions:

`p_yes - p_no`

The confidence interval is calculated using the two separate sample proportions, not the pooled proportion.

## Assumptions Considered

1. The two groups are treated as independent survey response groups.
2. The response variable is binary, so a two-proportion method is appropriate.
3. The sample sizes are large enough for the normal approximation.
4. Missing and invalid codes are excluded from the final main analysis.
5. The result should be interpreted as an association, not causation, because the YRBS data are observational survey data.

## Main Numerical Result

| Result | Value |
|---|---:|
| n_yes | 3,854 |
| x_yes | 1,064 |
| p_yes | 0.2761 |
| n_no | 9,320 |
| x_no | 1,508 |
| p_no | 0.1618 |
| Difference | 0.1143 |
| 95% CI | [0.0983, 0.1302] |
| z statistic | 15.0536 |
| p-value | < 0.0001 |
| Decision at alpha = 0.05 | Reject H0 |

## Interpretation of the Main Result

The current cigarette use proportion was higher in the Sad/Hopeless: Yes group than in the Sad/Hopeless: No group. The estimated difference was 0.1143, and the 95% confidence interval was entirely above 0. The two-proportion z-test also gave a p-value less than 0.0001, so we reject the null hypothesis at alpha = 0.05.

This provides statistically significant evidence that the current cigarette use proportion differs between the two groups.

## Main EDA Method Note

The main EDA supports the inference question using three descriptive visualizations:

1. A proportion gap plot comparing `p_yes` and `p_no`.
2. A 100% stacked bar chart showing binary smoking status distribution in each Sad/Hopeless group.
3. A smokers-only frequency difference plot showing how Light, Moderate, and Frequent smoking differ between groups among current smokers.

These EDA figures are descriptive. The formal inference is conducted in the two-proportion z-test.

## Additional EDA Note

The additional EDA examines **substance-related health-risk behavior clustering**. In this context, clustering means that multiple behaviors are reported by the same student.

The three behaviors are:

- current cigarette use
- current alcohol use
- current marijuana use

The additional EDA uses:

1. `health_risk_behavior_count`, ranging from 0 to 3.
2. `behavior_combination`, which identifies the exact behavior combination, such as `Alcohol only`, `Cigarette + Alcohol`, or `All three`.
3. An UpSet-style combination plot to display how substance-related health-risk behaviors cluster together.
4. A 2+ behaviors threshold summary to highlight multiple-risk behavior clustering.

This additional EDA is exploratory and is not the main two-sample inference test. It should also be interpreted as association, not causation.

## Additional EDA Numerical Highlights

| Result | Sad/Hopeless: Yes | Sad/Hopeless: No |
|---|---:|---:|
| Mean health-risk behavior count | 1.09 | 0.72 |
| Two or more behaviors | 32.8% | 20.0% |
| All three behaviors | 15.6% | 8.1% |
| No substance-related behaviors | 39.3% | 56.3% |
