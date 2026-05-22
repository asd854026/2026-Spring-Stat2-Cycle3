# Recoding Rules - Cycle 3 Question 8

## Main Analysis Variables

## SadOrHopeless

Required binary coding:

| Original code | Recoded value |
|---|---|
| 1 | `sad_binary = 1`, felt sad or hopeless |
| 2 | `sad_binary = 0`, did not feel sad or hopeless |
| Missing or invalid | Excluded from final analysis |

## CurrentCigaretteUse

`CurrentCigaretteUse` measures the number of days the student smoked cigarettes during the past 30 days.

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

### Binary recoding for two-proportion inference

| Original code | Recoded value |
|---|---|
| 1 | `smoker_binary = 0`, no current smoking in the past 30 days |
| 2-7 | `smoker_binary = 1`, current cigarette use |
| Missing or invalid | Excluded from final analysis |

### Grouped version for EDA

| Original code | Group |
|---|---|
| 1 | Non-smoker (0 days) |
| 2-3 | Light (1~5 days) |
| 4-5 | Moderate (6~19 days) |
| 6-7 | Frequent (20~30 days) |

The grouped version is used only for exploratory EDA. The main inference uses `smoker_binary`.

## Final Main Analysis Sample

Rows are included in the main Q8 analysis only if both of the following variables are valid:

- `sad_binary`
- `smoker_binary`

The processed-only dataset for the main analysis is saved as:

`data/processed/yrbs_cycle3_q8_processed_only.csv`

## Additional EDA Variables

## CurrentAlcoholUse

`CurrentAlcoholUse` measures the number of days the student drank alcohol during the past 30 days.

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

### Binary recoding

| Original code | Recoded value |
|---|---|
| 1 | `alcohol_binary = 0`, no current alcohol use |
| 2-7 | `alcohol_binary = 1`, current alcohol use |
| Missing or invalid | Excluded from health-risk behavior count |

## CurrentMarijuaUse

`CurrentMarijuaUse` measures how many times the student used marijuana during the past 30 days.

### Original valid codes

| Code | Meaning |
|---:|---|
| 1 | 0 times |
| 2 | 1 or 2 times |
| 3 | 3 to 9 times |
| 4 | 10 to 19 times |
| 5 | 20 to 39 times |
| 6 | 40 or more times |

### Binary recoding

| Original code | Recoded value |
|---|---|
| 1 | `marijuana_binary = 0`, no current marijuana use |
| 2-6 | `marijuana_binary = 1`, current marijuana use |
| Missing or invalid | Excluded from health-risk behavior count |

## Health-risk Behavior Count

The health-risk behavior count is calculated as:

`health_risk_behavior_count = smoker_binary + alcohol_binary + marijuana_binary`

The count is calculated only when all three indicators are valid:

- `smoker_binary`
- `alcohol_binary`
- `marijuana_binary`

Rows are included in the additional EDA only if `sad_binary` and all three health-risk indicators are valid.

The processed-only dataset for the additional EDA is saved as:

`data/processed/yrbs_cycle3_health_risk_processed_only.csv`
