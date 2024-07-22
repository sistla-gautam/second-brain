- APIs cannot make calls if they are blocked by CORs
- if they are blocked by CORs, there are ways to bypass it
	- run a proxy server
	- run the call with a no-cors mode

##### proxy server
- we can by pass this with a proxy server 
- we create a server that will pass the requests to the required server
- now, our code needs to call that proxy server instead of the original server
- this way, only the server is able to call the API and hence does not trigger the CORs error

#### no-cors mode
- this is a much more restricted method to solve the issue
- we add a mode: no-cors to the calls options
- this way, the call will travel through, but the response will be opaque
	- that is, the response will only be visible as to if it is success or fail
	- the contents inside the response will not be visible to read the data