# Current Humidor

``` dataview
TABLE
embed(link(Image, "50")) AS Image,
Purchase_Date as "Purchase Date",
date(today) - Purchase_Date as Age,
Purchased_Quantity as "Purchased",
Remaining_Quantity as "Remaining",
Category as "Category",
Wrapper as "Wrapper",
Wrapper_Country as "Wrapper Country",
Binder_Country as "Binder Country",
Filler_Country as "Filler Country",
Shape as "Shape"
FROM "The Humidor/Cigars/Inventory"
SORT Category DESC
```

