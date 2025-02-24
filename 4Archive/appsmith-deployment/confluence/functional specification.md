## Main features
- used to create interactive forms and share the same with other users
- allows connecting to databases and API endpoints to execute queries or API calls
- accept user input either from a anonymous user or from a logged in user

## Initial configuration
- Once invited, the user will be part of a default workspace (tenant specific)
- this workspace will contain other applications that the user will have access to
- depending on the role of the user, the user can edit or execute the application
![[Pasted image 20250203141505.png]]
#### steps to create a simple form application
- click on the "Create new" button
![[Pasted image 20250203141528.png]]
- press the "Application" option in the dropdown
![[Pasted image 20250203141537.png]]
- place the "Input" widget into the UI
![[Pasted image 20250203141636.png]]
- Configure the input as required
![[Pasted image 20250203141753.png]]
- deploy the application by clicking on the "Deploy" button in the top right corner
![[Pasted image 20250203141807.png]]

#### steps to access a deployed application
- once the application is deployed, the application is hosted on a particular URL
- use this URL to access the application
![[Pasted image 20250203141959.png]]

#### steps to publish the deployed application in the BI editor dashboard

- copy the URL of the application that needs to be shared
- this URL can then be used in the dashboard with different widgets
	- table
	- tree
![[Pasted image 20250203142310.png]]
- the URL can also be appended with URL query parameters (optional) to get the required data to the application
![[Pasted image 20250203142416.png]]
- the application needs to be configured to read the data from the URL in the correct manner
![[Pasted image 20250203142601.png]]