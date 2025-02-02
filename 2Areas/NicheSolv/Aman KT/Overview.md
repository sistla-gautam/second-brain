# main components
- Environment 
	- each of them are kubernetes cluster
	- managed by Azure - we dont control them
	- most services run as pods (think of them as containers of docker)


### structure of kubernetes deployment
this is only for stateless apps
- deploy
- pod
- container
also has 2 other components for storing ENV vars
- secrets - holds secret values
- config map - holds non secret values
> once a secrets or configmap is changed, we need to restart the pods

##### exposing the application
- if we ever need to make the STS or the deployment accessible, we need to connect it to a service
	- this service will make the application exposed
	- YTI uses Istio - this is a ingress controller
		- istio is the best way to expose the application to a domain

> istio and OPA are the two sidecar applications. these side car applications are used for most applications
###### Istio structure
- gateway
	- this holds the list of all the baseUrls
	- if we need a new domain, we need to list it here
- virtual service
	- handles the routing of the application to the different subdomains (paths)
- kubernetes
	- the same structure as the kubernetes

###### OPA structure
- this is the sidecar that will look into if the user has the required permissions
- this will read the JWT token given from the platform
- depending on that, it will allow or deny different URLs