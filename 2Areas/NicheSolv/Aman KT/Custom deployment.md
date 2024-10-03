in some cases, only a single customer will require a different release, where as the other applications will require one of the multi tenant deployment
in this case, we will solve it by looking in the following things

- we deploy it in a new pod
- mostly change the environment variables to point to the different buckets and other services
- we sometimes need to change the hardcoded URLs in the code itself
	- URLs will point to different applications
	- URLs will point to different azure storages