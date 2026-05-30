# Method and Assumptions

## Main Research Question
Question 8 asks whether the proportion of current cigarette use is different between students who felt sad or hopeless and those who did not.

Because the response variable is binary, the main analysis uses a **two-proportion z-test** and a **95% confidence interval for the difference in proportions**.

## Parameter Definitions
Let:

- `p_yes` = the true proportion of current cigarette use among students who felt sad or hopeless
- `p_no` = the true proportion of current cigarette use among students who did not feel sad or hopeless

The estimated difference is:

`p_yes - p_no`

## Hypotheses

- Null hypothesis: `H0: p_yes - p_no = 0`
- Alternative hypothesis: `H1: p_yes - p_no != 0`

The test is two-sided with significance level `alpha = 0.05`.

## Method Choice
A two-proportion z-test is appropriate because:

1. the group variable has two groups: Sad/Hopeless Yes and Sad/Hopeless No;
2. the response variable is binary: current cigarette use vs no current cigarette use;
3. the sample sizes are large enough for the normal approximation.

## Confidence Interval
A 95% confidence interval is calculated for the difference in current cigarette use proportions.

The confidence interval uses the separate sample proportions from the two groups.

## Hypothesis Test
For the two-proportion z-test, the pooled proportion is used when calculating the standard error under the null hypothesis.

## Assumptions Considered

### 1. Two groups are clearly defined
The two groups are:

- students who felt sad or hopeless
- students who did not feel sad or hopeless

### 2. Binary response variable
`CurrentCigaretteUse` is recoded into a binary response:

- `1` = current cigarette use
- `0` = no current cigarette use

### 3. Large sample size
Both groups have large enough sample sizes, and the expected success and failure counts are sufficiently large for a two-proportion z-test.

### 4. Missing and invalid values
Rows with missing or invalid values in the group or response variable are excluded from the main analysis.

### 5. Observational data
The YRBS data are observational survey data. Therefore, the result should be interpreted as an association, not as evidence of causation.

## Main Numerical Result
The main inference result is:

- `p_yes = 0.2761`
- `p_no = 0.1618`
- estimated difference = `0.1143`
- 95% CI = `[0.0983, 0.1302]`
- z statistic = `15.0536`
- p-value `< 0.0001`

At `alpha = 0.05`, the null hypothesis is rejected.

## Additional EDA Note
The additional EDA is exploratory and separate from the main two-proportion inference test.

It compares two behavior domains:

1. **Substance-related risk behavior clustering**
   - current cigarette use
   - current alcohol use
   - current marijuana use

2. **Healthy diet behavior clustering**
   - daily fruit eating
   - daily green salad eating
   - daily other vegetable eating

In this context, **clustering** means that multiple behaviors in the same domain are reported by the same student.

The additional EDA uses:

- `substance_risk_count`
- `healthy_diet_count`
- `substance_behavior_combination`
- `healthy_diet_combination`

The UpSet-style combination plots are used to show which behaviors appear together within each domain. The summary profile plot compares the percentage of students reporting Sad/Hopeless across behavior count levels from 0 to 3.

These additional EDA results should be interpreted as descriptive associations only. They do not replace the main Question 8 inference result and should not be interpreted as causal evidence.
