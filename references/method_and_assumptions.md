# Method and Assumptions - Cycle 3 Question 8

## Selected Method
This project uses a two-proportion z-test because the main response variable, current cigarette use, is binary after recoding.

## Hypotheses
- H0: p_yes = p_no
- H1: p_yes != p_no

where:
- p_yes = current cigarette use proportion among students who felt sad or hopeless
- p_no = current cigarette use proportion among students who did not feel sad or hopeless

## Confidence Interval
A 95% confidence interval is calculated for the difference in proportions:

`p_hat_yes - p_hat_no`

## Assumptions Considered
1. The two groups are treated as independent survey response groups.
2. The response variable is binary, so a two-proportion method is appropriate.
3. The sample sizes are large enough for a normal approximation.
4. Missing and invalid codes are excluded from the final analysis.
5. This is observational survey data, so the result should be interpreted as association, not causation.

## Main Numerical Result
- n_yes = 3,854, x_yes = 1,064, p_hat_yes = 0.2761
- n_no = 9,320, x_no = 1,508, p_hat_no = 0.1618
- Difference = 0.1143
- 95% CI = [0.0983, 0.1302]
- z = 15.0536
- p-value = < 0.0001
