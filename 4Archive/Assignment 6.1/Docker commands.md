## container commands
#### pulling docker images
- `docker pull` the image from the hub
	- this can be easily done on the desktop application
##### list of all docker images
- this is done by running the `docker images` command
- this will list all the images accessible to 
##### running the docker image
- running of docker images is done by using the `docker run` command along with the `name` argument
```shell
docker run --name=_container_name_ --restart on-failure -d _image_name_:_tag_
```
#### listing all docker container 
- this can be done with the `docker ps` command
- this will list all the different container that are currently running
- if we need to list all the different containers (including inactive ones), we can use the `-a` argument
```shell
docker ps
docker ps -a
```
#### accessing the logs of the container
- this can be done with the `docker logs` command
	- provide the container id as the parameter
```shell
docker logs <id>
```
#### removing a docker container
- this can be done with the `rm` command
	- pass the id as the parameter
```shell
docker rm <id>
```
---
## build commands
- to create a new image of the application
```shell
docker build -t <name_of_image> /path/to/dir
```
- to remove an existing image
```shell
docker rmi <image_name>
```
to remove a docker image, we need to first delete the container that is referencing it
