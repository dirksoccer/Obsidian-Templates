---
Purchase_Date: 
Purchase_Quantity_Oz: 
Remaining_Cellar_Oz: 
Merchant: 
Brand: 
Manufacturer: 
Category: 
Image: 
tags:
---
`="!"+this.Image`
# Blend Details

# Ratings

```meta-bind-button
style: primary
label: Initialize Button
actions:
  - type: replaceSelf
    replacement: z_Templates/Tobacco_Review_Button_Template.md
    templater: True
```
## Flavors Notes

```dataview
LIST FlavorCount
FROM [[]] and "The Humidor/Tobacco/Reviews"
WHERE Dominant_Flavors
FLATTEN Dominant_Flavors as Flavors
GROUP BY Flavors
FLATTEN length(rows) as FlavorCount
SORT FlavorCount DESC
```

## Average Score

``` dataview
TABLE WITHOUT ID
sum(rows.Condition)/length(rows.Condition) as "Condition",
sum(rows.Flavor)/length(rows.Flavor) as "Flavor",
sum(rows.Room_Note)/length(rows.Room_Note) as "Room Note",
sum(rows.Impression)/length(rows.Impression) as "Impression",
(sum(rows.Condition) + sum(rows.Flavor) + sum(rows.Room_Note) + sum(rows.Impression))/length(rows.Condition) as "Overall",
sum(rows.Strength)/length(rows.Strength) as "Strength"
FROM [[]] and "The Humidor/Tobacco/Reviews"
GROUP BY ""
```

## Individual Scores
``` dataview
TABLE WITHOUT ID
Date AS Date,
Condition as "Condition",
Flavor as "Flavor",
Room_Note as "Room Note",
Impression as "Impression",
Condition + Flavor + Room_Note + Impression as "Overall",
Strength as "Strength (5)"
FROM [[]] and "The Humidor/Tobacco/Reviews"
SORT Date DESC
```