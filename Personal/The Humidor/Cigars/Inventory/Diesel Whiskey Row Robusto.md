---
Purchase_Date: 2024-05-09
Purchase_Quantity: 10
Remaining_Quantity: 7
Merchant: CigarBid
Brand: Diesel
Manufacturer: 
Category: Habano
Wrapper: Habano
Wrapper_Country: Nicaragua
Binder: San Andres
Binder_Country: Mexico
Filler: 
Filler_Country:
  - Nicaragua
Shape: Robusto
Length: 5.5
Ring_Gauge: 52
Image: "[[diesel-whiskey-row.webp]]"
tags:
  - cigar/habano
---
`="!"+this.Image`
# Blend Details
Diesel Libation  

If you’ve been around these parts long enough, you’re well aware of the Diesel brand. No-nonsense, full-flavored, and expert construction. These phrases no doubt come to mind. Diesel Whiskey Row stays true, but takes a unique approach for the brand. The binder is aged in Rabbit Hole Bourbon barrels – a first for Diesel as well as master blender AJ Fernandez. But have no fear – these bourbon barrels that once held Rabbit Hole Bourbon were first shipped to AJ Fernandez in 2016. After many months of testing, he finally nailed down a process that imparts the perfect amount of flavor and aroma into the tobacco and Diesel Whiskey Row was born. 

The core of this cigar is made up entirely of Nicaraguan long-fillers from 3 different growing regions - Ometepe, Jalapa, and Condega – that have been aged from five to eight years. The bourbon barrel aged binder is a Mexican San Andres leaf, and it’s all held together five-years aged Ecuadorian habano wrapper. The barrel aging produces a strong oaky flavor and hints of bourbon in the aroma. You’ll also notice some floral notes, spice and some sweetness in a medium-bodied format. In my many, many samplings of this cigar, the construction has been nothing short of flawless – something we’ve come to expect from AJ-made cigars. Grab a box of these unique Diesels today, pair ‘em with a few fingers of the good stuff, and you won’t be disappointed. 

Good news! Diesel Whiskey Row has received a well-deserved 91-point rating, noting: _"The earthy, chocolate notes of this cigar frame a hearty core of wood and cedar, all combining for a finish of bread and brown sugar."_
# Ratings

```meta-bind-button
style: primary
label: Add Review
actions:
  - type: templaterCreateNote
    templateFile: z_Templates/Cigar_Review_Template.md
    folderPath: "The Humidor/Cigars/Reviews"
    fileName: Diesel Whiskey Row Robusto
```

## Flavor Notes

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