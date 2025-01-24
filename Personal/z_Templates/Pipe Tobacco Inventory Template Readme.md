# **Summary**:
This set of templates is set up to
- Track pipe tobacco inventory
- Easily review a tobacco
- Compile review data for a given tobacco
- Compile a summary of the overall inventory
	- (TBI) Include review data in overall inventory summary
	- (TBI) Rework how I handle tobacco aging, not a huge fan of different entries for different ages

Note: The templates are hard coded for my folder setup, either copy it or modify the paths to match your desired configuration.
- Inventory in `The Humidor\Tobacco\Inventory`
- Reviews in `The Humidor\Tobacco\Reviews`
- Images in `The Humidor\Tobacco\z_Images` (not strict)
# **Plugins Required**:
- Templater
- Data View
- Meta Bind
# **Templates**:
Note: The top level summary is not implemented as a template, since it is a one-off. But I pushed it to the repo and if you use the same paths I do it will work for you. If not you can update the dataview query.
## **Pipe_Tobacco_Inventory_Template**
The core template for a tobacco in your inventory. Use this template for each individual tobacco and age (meaning if you bought a batch last year and more this year, they would get different pages - not super happy with that setup but WiP) 
- The Properties at the top are the fields that are pulled for the inventory table.
- The Image linked in the property will be displayed immediately below the Properties
- The Blend Details section is for a general/manufacturer's description
- The Ratings section is fully automated. 
	- Click "Initialize Button" for one time setup (will replace itself with "Add Review")
	- Click the "Add Review" button to create and open a new review file
		- `The Humidor\Tobacco\Reviews\MM-DD-YYYY Name of Tobacco`
		- Fill out the review (see template below)
	- The Flavor Notes section will populate with a list of all of the flavor notes called out in the Properties of your review, ordered by the number of times they appear
	- The Average Score will compile the average of all reviews for this tobacco
	- The Individual Scores will list a top level summary of each review
## **Pipe_Tobacco_Review_Button_Template**:
This is a simple template for the "Add Review" button that replaces the "Initialize Button" button in the inventory template. I implemented it this way because of some issues getting the name of the tobacco into the button when a new page was created
## Pipe_Tobacco_Review_Template**:
This is the page that will be created when the "Add Review" button is clicked in the inventory template. This will rename itself to have the date of the review and the name of the tobacco as the title.
- The Properties should auto populate with the date, but otherwise these fields are what will be pulled for the review summaries on the inventory pages
	- Note: Dominant_Flavors is a list. Add a new flavor note and hit enter (not a comma separated list). This will make each of them individual entities that can be counted/listed on the inventory page
- The tobacco parent page will be automatically linked
- **Context** 
	- Environment: What were you doing when you smoked? What was the weather like? What were you drinking?
- **Condition** (scored out of 15 total)
	- Ease of Preparation (10)
	- Tin Note (5)
- **Flavor** (scored out of 50)
- **Impression** (scored out of 25)
	- This is personal adjustments to the score. Any comments? Was it a huge pain to prep, or easy? Maybe it's objectively good, but not to your tastes, so you ding it here so it's not high on your rankings even though it scored perfect in the other sections.
- **Additional Info**
	- Dominant Flavors - Space to write out more details to go with the listed flavors above
	- Strength - scale of 1 to 5