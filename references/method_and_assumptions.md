# Method and Assumptions - Cycle 3 Question 8

## Method Choice

The response variable, current cigarette use, is binary. Therefore, the correct method is a **two-proportion z-test**, not a two-sample t-test.

## Hypotheses

Let:

- `p_yes` = true proportion of current cigarette use among students who felt sad or hopeless
- `p_no` = true proportion of current cigarette use among students who did not feel sad or hopeless

Hypotheses:

```text
H0: p_yes - p_no = 0
Ha: p_yes - p_no != 0
```

## Assumptions Considered

1. **Two groups are clearly defined**: SadOrHopeless Yes vs SadOrHopeless No.
2. **Response is binary**: current cigarette use yes/no.
3. **Independent groups**: each student belongs to only one SadOrHopeless group.
4. **Large sample condition**: each group has enough successes and failures for a normal approximation.
   - SadOrHopeless Yes: 1,064 successes, 2,790 failures
   - SadOrHopeless No: 1,508 successes, 7,812 failures
5. **Observational data**: this analysis can show association, not causation.

## Result Summary

- Difference: 0.1143 (11.43 percentage points)
- 95% CI: [0.0983, 0.1302]
- z statistic: 15.0536
- p-value: < 0.0001
