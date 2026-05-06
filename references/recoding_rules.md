# Recoding Rules - Cycle 3 Question 8

This project follows the required Cycle 3 recoding rules.

## SadOrHopeless

```python
SadOrHopeless_binary = 1 if SadOrHopeless == 1
SadOrHopeless_binary = 0 if SadOrHopeless == 2
```

## CurrentCigaretteUse

```python
CurrentCigaretteUse_binary = 0 if CurrentCigaretteUse == 1
CurrentCigaretteUse_binary = 1 if CurrentCigaretteUse in [2, 3, 4, 5, 6, 7]
```

## Missing / Invalid Values

Rows with missing or invalid values in either variable are removed before inference.

This avoids treating survey category codes as continuous numerical values.
