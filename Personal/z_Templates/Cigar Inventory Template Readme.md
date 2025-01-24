# **Summary**:
This set of templates is set up to
- Track cigar inventory
- Easily review a cigar
- Compile review data for a given cigar
- Compile a summary of the overall inventory
	- (TBI) Include review data in overall inventory summary

Note: The templates are hard coded for my folder setup, either copy it or modify the paths to match your desired configuration.
- Inventory in `The Humidor\Cigars\Inventory`
- Reviews in `The Humidor\Cigars\Reviews`
- Images in `The Humidor\Cigars\z_Images` (not strict)
# **Plugins Required**:
- Templater
- Data View
- Meta Bind
# **Templates**:
Note: The top level summary is not implemented as a template, since it is a one-off. But I pushed it to the repo and if you use the same paths I do it will work for you. If not you can update the dataview query.
## **Cigar_Inventory_Template**
The core template for a cigar in your inventory. Use this template for each individual stick and size (I like to have my reviews and inventory separated by size as well). 
- The Properties at the top are the fields that are pulled for the inventory table.
- The Image linked in the property will be displayed immediately below the Properties
- The Blend Details section is for a general/manufacturer's description
- The Ratings section is fully automated. 
	- Click "Initialize Button" for one time setup (will replace itself with "Add Review")
	- Click the "Add Review" button to create and open a new review file
		- `The Humidor\Cigars\Reviews\MM-DD-YYYY Name of Cigar`
		- Fill out the review (see template below)
	- The Flavor Notes section will populate with a list of all of the flavor notes called out in the Properties of your review, ordered by the number of times they appear
	- The Average Score will compile the average of all reviews for this stick
	- The Individual Scores will list a top level summary of each review
## **Cigar_Review_Button_Template**:
This is a simple template for the "Add Review" button that replaces the "Initialize Button" button in the inventory template. I implemented it this way because of some issues getting the name of the cigar into the button when a new page was created
## **Cigar_Review_Template**:
This is the page that will be created when the "Add Review" button is clicked in the inventory template. This will rename itself to have the date of the review and the name of the cigar as the title.
- The Properties should auto populate with the date, but otherwise these fields are what will be pulled for the review summaries on the inventory pages
	- Note: Dominant_Flavors is a list. Add a new flavor note and hit enter (not a comma separated list). This will make each of them individual entities that can be counted/listed on the inventory page
- The Cigar parent page will be automatically linked
- **Context** 
	- Storage: Temp? RH? Other comments?
	- Environment: What were you doing when you smoked? What was the weather like? What were you drinking?
- **Construction** (scored out of 30 total)
	- Appearance and Feel (10)
	- Draw (10)
	- Burn (10)
- **Flavor** (scored out of 45)
	- First Third
	- Second Third
	- Final Third
- **Impression** (scored out of 25)
	- This is personal adjustments to the score. Any comments? Maybe it burned poorly but it was a windy day on the golf course, so you give it a few points back. Maybe it's objectively good, but not to your tastes, so you ding it here so it's not high on your rankings even though it scored perfect in the other sections.
- **Additional Info**
	- Dominant Flavors - Space to write out more details to go with the listed flavors above
	- Strength - scale of 1 to 5
	- Smoke Time - entered as a number (hours) up above, but can explain here
## **Cigar_Inventory_Retrofit_Template**: 
Deprecated - used to update old versions of the Inventory that were in my vault