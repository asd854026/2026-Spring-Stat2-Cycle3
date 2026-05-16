# Recoding Rules

## SadOrHopeless
Required binary coding:

- Original code 1 -> 1 = felt sad or hopeless
- Original code 2 -> 0 = did not feel sad or hopeless
- Missing or other invalid values -> excluded from final analysis

## CurrentCigaretteUse
CurrentCigaretteUse measures the number of days the student smoked cigarettes during the past 30 days.

### Original valid codes
- 1 = 0 days
- 2 = 1 or 2 days
- 3 = 3 to 5 days
- 4 = 6 to 9 days
- 5 = 10 to 19 days
- 6 = 20 to 29 days
- 7 = all 30 days

### Binary recoding for two-proportion inference
- Original code 1 -> smoker_binary = 0 = no current smoking in the past 30 days
- Original codes 2-7 -> smoker_binary = 1 = current cigarette use, at least 1 day in the past 30 days
- Missing or other invalid values -> excluded from final analysis

### Grouped version for exploratory EDA
- 1 -> No current smoking (0 days)
- 2-3 -> Light (1-5 days)
- 4-5 -> Moderate (6-19 days)
- 6-7 -> Frequent (20-30 days)

For the smokers-only stacked bar chart, the Non-smoker group is excluded so that the chart focuses only on the frequency composition among current smokers.
## Final Analysis Sample
Rows are included only if both the group variable and response variable have valid recoded values.
