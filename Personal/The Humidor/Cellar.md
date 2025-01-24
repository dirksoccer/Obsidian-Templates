# Current Cellar

``` dataview
TABLE
embed(link(Image, "50")) AS Image,
Purchase_Date as "Purchase Date",
date(today) - Purchase_Date as Age,
Purchased_Quantity_Oz as "Purchased Oz",
Remaining_Cellar_Oz as "Remaining Oz",
Category as "Category"
FROM "The Humidor/Tobacco/Inventory"
SORT Category DESC
```

