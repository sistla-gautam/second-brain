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

## container commands
- to view all the running containers