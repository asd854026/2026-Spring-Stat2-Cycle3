# Variable Definitions

## Research Question
Is the proportion of current cigarette use different between students who felt sad or hopeless and those who did not?

## Group Variable: SadOrHopeless
- Role: group variable / explanatory grouping variable
- Original variable name: `SadOrHopeless`
- Group 1: students who felt sad or hopeless (`sad_binary = 1`)
- Group 0: students who did not feel sad or hopeless (`sad_binary = 0`)

## Response Variable: CurrentCigaretteUse
- Role in this project: response variable
- Original variable name: `CurrentCigaretteUse`
- What it measures: number of days the student smoked cigarettes during the past 30 days.

### Valid codes used
- `1` = 0 days
- `2` = 1 or 2 days
- `3` = 3 to 5 days
- `4` = 6 to 9 days
- `5` = 10 to 19 days
- `6` = 20 to 29 days
- `7` = all 30 days

### Main recoding rule for inference
- `1` -> `smoker_binary = 0` = non-smoker in the past 30 days
- `2` to `7` -> `smoker_binary = 1` = reported smoking on at least 1 day in the past 30 days

### Grouped version for EDA
- `1` -> Non-smoker (0 days)
- `2`, `3` -> Light (1-5 days)
- `4`, `5` -> Moderate (6-19 days)
- `6`, `7` -> Frequent (20-30 days)

The grouped version is used only to describe the smoking frequency pattern. The main two-sample inference still uses the binary response `smoker_binary`.

## Difference Definition
The estimated difference is defined as:

`p_yes - p_no`

This means a positive difference indicates that the Sad/Hopeless Yes group has a higher current cigarette use proportion.
