## adding the input to the editor UI
- choose any type of input
![[Pasted image 20250213103243.png]]
- click on the input to edit the properties of the widget on the right side pane
![[Pasted image 20250213103337.png]]
- Here, any value can be replaced by reading the values from the URL

## Configuring any value to read URL params
- Click on any of the fields like default value or placeholder
- enter the following value into them to get the data from URL `{{appsmith.URL.queryParams.<param>}}` where `param`  is the name of the parameter you want to read
- this will read the data from the parameter
![[Pasted image 20250213105255.png]]
![[Pasted image 20250213105316.png]]
NOTE: the data will be only visible when the data is passed in the parameter
- The URL when the data was passed
![[Pasted image 20250213105432.png]]
- The data can be passed in a similar manner when the application is deployed too