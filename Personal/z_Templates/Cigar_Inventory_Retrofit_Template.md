```meta-bind-button
style: primary
label: Initialize Button
actions:
  - type: replaceSelf
    replacement: z_Templates/Cigar_Review_Button_Template.md
    templater: True
```

## Average
``` dataview
TABLE WITHOUT ID
sum(rows.Construction)/length(rows.Construction) as "Construction",
sum(rows.Flavor)/length(rows.Flavor) as "Flavor",
sum(rows.Adjustment)/length(rows.Adjustment) as "Adjustment",
(sum(rows.Construction) + sum(rows.Flavor) + sum(rows.Adjustment))/length(rows.Construction) as "Overall",
sum(rows.Strength)/length(rows.Strength) as "Strength",
sum(rows.Smoke_Time)/length(rows.Smoke_Time) as "Smoke Time"
FROM [[]] and "The Humidor/Cigars/Reviews"
GROUP BY ""
```

## Individual Scores
``` dataview
TABLE WITHOUT ID
Date AS Date,
Construction as "Construction (25)",
Flavor as "Flavor (75)",
Adjustment as "Adjustment",
Construction + Flavor + Adjustment as "Overall",
Strength as "Strength (5)",
Smoke_Time as "Smoke Time (Hrs)"
FROM [[]] and "The Humidor/Cigars/Reviews"
SORT Date DESC
```
## Dominant Flavors
```dataview
LIST FlavorCount
FROM [[]] and "The Humidor/Cigars/Reviews"
WHERE Dominant_Flavors
FLATTEN Dominant_Flavors as Flavors
GROUP BY Flavors
FLATTEN length(rows) as FlavorCount
SORT FlavorCount DESC
```