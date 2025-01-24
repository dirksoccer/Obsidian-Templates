<%* 
const title = tp.file.title; 
let newTitle; 
if (title.startsWith("Untitled")) { 
	newTitle = await tp.system.prompt("Enter note title");
	await tp.file.rename(newTitle); 
} 
-%>
---
Purchase_Date: 
Purchase_Quantity: 
Remaining_Quantity: 
Merchant: 
Brand: 
Manufacturer: 
Category: 
Wrapper: 
Wrapper_Country: 
Binder: 
Binder_Country: 
Filler: 
Filler_Country: 
Shape: 
Length: 
Ring_Gauge: 
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
    replacement: z_Templates/Cigar_Review_Button_Template.md
    templater: True
```
## Flavors Notes

```dataview
LIST FlavorCount
FROM [[]] and "The Humidor/Cigars/Reviews"
WHERE Dominant_Flavors
FLATTEN Dominant_Flavors as Flavors
GROUP BY Flavors
FLATTEN length(rows) as FlavorCount
SORT FlavorCount DESC
```

## Average Score

``` dataview
TABLE WITHOUT ID
sum(rows.Construction)/length(rows.Construction) as "Construction",
sum(rows.Flavor)/length(rows.Flavor) as "Flavor",
sum(rows.Impression)/length(rows.Impression) as "Impression",
(sum(rows.Construction) + sum(rows.Flavor) + sum(rows.Impression))/length(rows.Construction) as "Overall",
sum(rows.Strength)/length(rows.Strength) as "Strength",
sum(rows.Smoke_Time)/length(rows.Smoke_Time) as "Smoke Time"
FROM [[]] and "The Humidor/Cigars/Reviews"
GROUP BY ""
```

## Individual Scores
``` dataview
TABLE WITHOUT ID
Date AS Date,
Construction as "Construction",
Flavor as "Flavor",
Impression as "Impression",
Construction + Flavor + Impression as "Overall",
Strength as "Strength (5)",
Smoke_Time as "Smoke Time (Hrs)"
FROM [[]] and "The Humidor/Cigars/Reviews"
SORT Date DESC
```
