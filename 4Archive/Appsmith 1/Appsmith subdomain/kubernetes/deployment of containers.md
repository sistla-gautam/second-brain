- we first run the command to get all the containers that contain appsmith
```shell
 kubectl get pods -n appsmith
```
- we then edit the configuration 
```shell
 kubectl edit deploy appsmith -n appsmith
```
- we replace the image hash with the new given hash value
	- we get this from the workflow -> tag the docker image
- we can then once again recheck the containers using the following command
```shell
 kubectl get pods -n appsmith
```