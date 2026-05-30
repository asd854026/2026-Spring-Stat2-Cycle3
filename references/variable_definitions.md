# Variable Definitions

## Main Research Question

### `SadOrHopeless`
Original group variable for Question 8.

It identifies whether a student reported feeling sad or hopeless for two or more weeks in a row during the past 12 months.

Recoded variable:
- `sad_binary = 1`: felt sad or hopeless
- `sad_binary = 0`: did not feel sad or hopeless

Group labels:
- `Sad/Hopeless: Yes`
- `Sad/Hopeless: No`

### `CurrentCigaretteUse`
Original response variable for Question 8.

It measures the number of days the student smoked cigarettes during the past 30 days.

Recoded variable:
- `smoker_binary = 1`: smoked cigarettes on at least 1 day in the past 30 days
- `smoker_binary = 0`: smoked cigarettes on 0 days in the past 30 days

### `smoking_freq_group`
EDA-only grouped version of `CurrentCigaretteUse`.

- `Non-smoker (0 days)`
- `Light (1~5 days)`
- `Moderate (6~19 days)`
- `Frequent (20~30 days)`

This variable is used only for descriptive visualization, not for the main two-proportion z-test.

---

## Additional EDA Variables
The additional EDA compares two behavior domains:

1. substance-related risk behaviors
2. healthy diet behaviors

The purpose is exploratory and separate from the main Question 8 inference test.

## Substance-related Risk Behavior Variables

### `CurrentCigaretteUse`
Used again as one of the three substance-related risk behavior indicators.

Derived variable:
- `smoker_binary = 1`: current cigarette use
- `smoker_binary = 0`: no current cigarette use

### `CurrentAlcoholUse`
Measures the number of days the student drank alcohol during the past 30 days.

Derived variable:
- `alcohol_binary = 1`: current alcohol use
- `alcohol_binary = 0`: no current alcohol use

### `CurrentMarijuaUse`
Measures the number of times the student used marijuana during the past 30 days.

Derived variable:
- `marijuana_binary = 1`: current marijuana use
- `marijuana_binary = 0`: no current marijuana use

### `substance_risk_count`
A count of the three substance-related risk behavior indicators:

`substance_risk_count = smoker_binary + alcohol_binary + marijuana_binary`

Possible values:
- `0`: none of the three substance-related risk behaviors
- `1`: one behavior
- `2`: two behaviors
- `3`: all three behaviors

This count is calculated only when all three substance-related indicators are valid.

### `substance_behavior_combination`
This variable describes which substance-related behaviors were reported together by the same student.

Examples:
- `None`
- `Alcohol only`
- `Cigarette only`
- `Marijuana only`
- `Cigarette + Alcohol`
- `Cigarette + Marijuana`
- `Alcohol + Marijuana`
- `All three`

This variable is used for the UpSet-style combination plot.

---

## Healthy Diet Behavior Variables

### `FruitEating`
Measures how often the student ate fruit during the past 7 days.

Derived variable:
- `fruit_daily_binary = 1`: ate fruit at least 1 time per day
- `fruit_daily_binary = 0`: ate fruit less than daily

### `GreenSaladEating`
Measures how often the student ate green salad during the past 7 days.

Derived variable:
- `green_salad_daily_binary = 1`: ate green salad at least 1 time per day
- `green_salad_daily_binary = 0`: ate green salad less than daily

### `OtherVegetableEating`
Measures how often the student ate other vegetables during the past 7 days.

Derived variable:
- `other_vegetable_daily_binary = 1`: ate other vegetables at least 1 time per day
- `other_vegetable_daily_binary = 0`: ate other vegetables less than daily

### `healthy_diet_count`
A count of the three healthy diet indicators:

`healthy_diet_count = fruit_daily_binary + green_salad_daily_binary + other_vegetable_daily_binary`

Possible values:
- `0`: none of the three daily healthy diet behaviors
- `1`: one daily healthy diet behavior
- `2`: two daily healthy diet behaviors
- `3`: all three daily healthy diet behaviors

This count is calculated only when all three healthy diet indicators are valid.

### `healthy_diet_combination`
This variable describes which healthy diet behaviors were reported together by the same student.

In the plot, shorter labels are used for readability:
- `Salad` = daily green salad eating
- `Vegetables` = daily other vegetable eating

Examples:
- `None`
- `Fruit only`
- `Salad only`
- `Vegetables only`
- `Fruit + Salad`
- `Fruit + Vegetables`
- `Salad + Vegetables`
- `All three`

This variable is used for the UpSet-style healthy diet combination plot.
