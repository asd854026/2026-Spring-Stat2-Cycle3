# Variable Definitions - Cycle 3 Question 8

## Research Question

Is the proportion of current cigarette use different between students who felt sad or hopeless and those who did not?

## Main Group Variable: SadOrHopeless

| Item | Definition |
|---|---|
| Original variable name | `SadOrHopeless` |
| Role | Group variable / explanatory grouping variable |
| Group 1 | Students who felt sad or hopeless |
| Group 0 | Students who did not feel sad or hopeless |

### Recoded variables

| Recoded variable | Definition |
|---|---|
| `sad_binary` | 1 = felt sad or hopeless, 0 = did not feel sad or hopeless |
| `sad_group` | Group label for Sad/Hopeless Yes or No |

## Main Response Variable: CurrentCigaretteUse

| Item | Definition |
|---|---|
| Original variable name | `CurrentCigaretteUse` |
| Role | Main response variable |
| What it measures | Number of days the student smoked cigarettes during the past 30 days |

### Original valid codes

| Code | Meaning |
|---:|---|
| 1 | 0 days |
| 2 | 1 or 2 days |
| 3 | 3 to 5 days |
| 4 | 6 to 9 days |
| 5 | 10 to 19 days |
| 6 | 20 to 29 days |
| 7 | all 30 days |

### Main binary recoding for inference

| Original code | Recoded value |
|---|---|
| 1 | `smoker_binary = 0`, no current cigarette use |
| 2-7 | `smoker_binary = 1`, current cigarette use |

### Grouped version for EDA

| Original code | Group |
|---|---|
| 1 | Non-smoker (0 days) |
| 2-3 | Light (1~5 days) |
| 4-5 | Moderate (6~19 days) |
| 6-7 | Frequent (20~30 days) |

The grouped version is used only for exploratory EDA. The main two-sample inference uses the binary response `smoker_binary`.

## Difference Definition

The estimated difference is defined as:

`p_yes - p_no`

where:

- `p_yes` = current cigarette use proportion in the Sad/Hopeless: Yes group
- `p_no` = current cigarette use proportion in the Sad/Hopeless: No group

A positive difference means the Sad/Hopeless: Yes group has a higher current cigarette use proportion.

## Additional EDA Variables

The additional EDA uses a health-risk behavior count based on current cigarette use, current alcohol use, and current marijuana use.

### CurrentAlcoholUse

| Item | Definition |
|---|---|
| Original variable name | `CurrentAlcoholUse` |
| What it measures | Number of days the student drank alcohol during the past 30 days |

Binary recoding:

| Original code | Recoded value |
|---|---|
| 1 | `alcohol_binary = 0`, no current alcohol use |
| 2-7 | `alcohol_binary = 1`, current alcohol use |

### CurrentMarijuaUse

| Item | Definition |
|---|---|
| Original variable name | `CurrentMarijuaUse` |
| What it measures | Number of times the student used marijuana during the past 30 days |

Original valid codes:

| Code | Meaning |
|---:|---|
| 1 | 0 times |
| 2 | 1 or 2 times |
| 3 | 3 to 9 times |
| 4 | 10 to 19 times |
| 5 | 20 to 39 times |
| 6 | 40 or more times |

Binary recoding:

| Original code | Recoded value |
|---|---|
| 1 | `marijuana_binary = 0`, no current marijuana use |
| 2-6 | `marijuana_binary = 1`, current marijuana use |

### Health-risk behavior count

The health-risk behavior count is calculated as:

`health_risk_behavior_count = smoker_binary + alcohol_binary + marijuana_binary`

The value ranges from 0 to 3.

| Count | Meaning |
|---:|---|
| 0 | No reported health-risk behaviors |
| 1 | One reported health-risk behavior |
| 2 | Two reported health-risk behaviors |
| 3 | Three reported health-risk behaviors |

The health-risk behavior count is calculated only when all three indicators are valid.
