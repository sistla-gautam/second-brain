- create a dashboard that will show the different laptops available for usage
- create google forms that will be able to update the status of the different assets in the sheets

### high level TODO
- [ ] create dashboards for asset management
- [ ] create a new sheet that will show the different assets based on input information
	- [ ] this can be made by the original all assets sheet
- [ ] take care of "in-office" "out-of-office" conditions
---
##### Forms to create
*focus on CRUD operation*
- New asset
	- serial number
	- type
	- model name, manufacturer
	- date purchased
- Upgrade of asset (RAM upgrade, OS change)
	- asset serial number (or any other type of ID)
	- original value
	- updated value
- Removal of asset
- Problem reporting for an Asset
	- asset details
	- problem faced

##### Actions to create (automations)
- Start of usage
	- should dynamically show the different values which are available for usage based on availability
	- need not show who will be using it, will just be a text value
	- will update the status of that asset to "being used"
- Stop of usage
	- should dynamically show the different values which are being used
	- will update the status of that to "unused"
- Borrow of assets for short periods
	- should show the different values
	- will update the status of the asset to "borrowed"

##### Dashboards
- Overview
	- borrowed
	- available assets
		- show numbers of laptops
		- number of 
	- laptops to be repaired
- Specific forms
	- inputs the type of asset to display
	- displays the required assets only
	- the history of the different users of a particular asset
		- should be a running list that shows the different transactions of the assets
