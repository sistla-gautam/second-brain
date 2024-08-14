- ![[Pasted image 20240812164008.png]]
- 2 scenarios
	- if someone has already created a record, how do we access that and show it in the form. when the user submits the form, then the DB is altered
---
- can the form read some type of argument which will be used to read the DB
- can the DB be changed based on the form (if possible use postgress)

#### workflow tasks
- create a sensor that will trigger a workflow if a value exceeds a certain threshold 
	- this workflow will write a record to the DB
- create a dashboard that will contain a link to a parameterized form
	- the form will read the data from the DB and populate the form
	- submission of the form will then modify the DB for that particular record with the updated value