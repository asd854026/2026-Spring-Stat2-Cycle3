# Recoding Rules

## Main Question 8 Recoding

### `SadOrHopeless` -> `sad_binary`
Original coding:
- code `1`: yes, felt sad or hopeless
- code `2`: no, did not feel sad or hopeless

Recoding:
- code `1` -> `sad_binary = 1`
- code `2` -> `sad_binary = 0`
- missing or invalid values -> excluded from the main analysis

### `CurrentCigaretteUse` -> `smoker_binary`
Original coding:
- code `1`: smoked cigarettes on 0 days during the past 30 days
- codes `2-7`: smoked cigarettes on at least 1 day during the past 30 days

Recoding:
- code `1` -> `smoker_binary = 0`
- codes `2-7` -> `smoker_binary = 1`
- missing or invalid values -> excluded from the main analysis

### `smoking_freq_group`
EDA-only grouped version of `CurrentCigaretteUse`:

- code `1` -> `Non-smoker (0 days)`
- codes `2-3` -> `Light (1~5 days)`
- codes `4-5` -> `Moderate (6~19 days)`
- codes `6-7` -> `Frequent (20~30 days)`

This variable is used only for descriptive visualization.

---

## Additional EDA Recoding
The additional EDA compares two domains:

1. substance-related risk behaviors
2. healthy diet behaviors

All additional EDA variables are treated as binary indicators before creating counts and combinations.

## Substance-related Risk Behavior Recoding

### `CurrentCigaretteUse` -> `smoker_binary`
- code `1` -> `0`: no current cigarette use
- codes `2-7` -> `1`: current cigarette use

### `CurrentAlcoholUse` -> `alcohol_binary`
- code `1` -> `0`: no current alcohol use
- codes `2-7` -> `1`: current alcohol use

### `CurrentMarijuaUse` -> `marijuana_binary`
- code `1` -> `0`: no current marijuana use
- codes `2-6` -> `1`: current marijuana use

### `substance_risk_count`
Calculated as:

`substance_risk_count = smoker_binary + alcohol_binary + marijuana_binary`

Rules:
- calculated only when all three substance-related indicators are valid
- possible values: `0`, `1`, `2`, `3`

### `substance_behavior_combination`
Created from `smoker_binary`, `alcohol_binary`, and `marijuana_binary`.

Examples:
- `None`
- `Alcohol only`
- `Cigarette + Alcohol`
- `All three`

Rows are included only when all three substance-related indicators are valid.

---

## Healthy Diet Behavior Recoding
The healthy diet variables are recoded using a daily-intake threshold.

For the selected healthy diet variables:
- codes `1-3` -> `0`: less than daily
- codes `4-7` -> `1`: at least 1 time per day
- missing or invalid values -> excluded from the additional EDA complete-case dataset

### `FruitEating` -> `fruit_daily_binary`
- codes `1-3` -> `0`: ate fruit less than daily
- codes `4-7` -> `1`: ate fruit at least 1 time per day

### `GreenSaladEating` -> `green_salad_daily_binary`
- codes `1-3` -> `0`: ate green salad less than daily
- codes `4-7` -> `1`: ate green salad at least 1 time per day

### `OtherVegetableEating` -> `other_vegetable_daily_binary`
- codes `1-3` -> `0`: ate other vegetables less than daily
- codes `4-7` -> `1`: ate other vegetables at least 1 time per day

### `healthy_diet_count`
Calculated as:

`healthy_diet_count = fruit_daily_binary + green_salad_daily_binary + other_vegetable_daily_binary`

Rules:
- calculated only when all three healthy diet indicators are valid
- possible values: `0`, `1`, `2`, `3`

### `healthy_diet_combination`
Created from `fruit_daily_binary`, `green_salad_daily_binary`, and `other_vegetable_daily_binary`.

For plot readability:
- `Salad` refers to daily green salad eating
- `Vegetables` refers to daily other vegetable eating

Examples:
- `None`
- `Fruit only`
- `Fruit + Salad`
- `Salad + Vegetables`
- `All three`

Rows are included only when all three healthy diet indicators are valid.

---

## Processed Data Files
The project saves processed-only datasets in `data/processed/`:

- `yrbs_cycle3_q8_processed_only.csv`: includes only processed columns used for the main Question 8 analysis.
- `yrbs_cycle3_substance_diet_processed_only.csv`: includes only processed columns used for the additional EDA on substance-related risk behaviors and healthy diet behaviors.
