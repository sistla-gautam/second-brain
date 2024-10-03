### Things to run
- RTS server (8091 port)
- redis (6379 port)
- mongodb (27017 port)

### **Pre-requisites**
Before you can start to hack on the Appsmith server, your machine should have the following installed:
- Java - OpenJDK 17.
- Maven - Version 3+ (preferably 3.6).
- A MongoDB database - Refer to the Setting up a local MongoDB instance section to setup a MongoDB instance using `Docker`.
- A Redis instance - Refer to the Setting up a local Redis instance section to setup a Redis instance using `Docker`.
- An IDE - We use IntelliJ IDEA as our primary IDE for backend development. To set it up, refer to the Setting up IntelliJ IDEA section.
---
# Running Redis

- Connect to WSL using the VS Code 
- Open the Rancher application and make sure it shows the online status
- check all container of docker
```bash
	docker ps -a
```
- find the required redis container and get the ID of it
- start the container by the command
    ```bash
    docker start <ID>
    ```
---
# Running Mongo
- run the command
    ```bash
    mongod --replSet rs0 --port 27017 --dbpath /data/db --bind_ip localhost
    ```
- to stop mongo, we can run the following command
    ```bash
    sudo systemctl stop mongod
    sudo rm /tmp/mongodb-27017.sock
    ```
---
# Running nginx

Can either run from the script or directly from the docker container
> The container method will not work if the nginx has not been run ever before

###### script method
go to client location
```bash
./start-https.sh --with-docker
```

###### Container method
- run the command to find all the nginx containers
    ```bash
    docker ps -a | grep nginx
    ```
- find the ID of the required container and run the command to start that container
    ```bash
    docker start <ID>
    ```
- we now need to access the shell of the given process of nginx
    ```bash
    docker exec -it <ID> sh
    ```
- here, we access the hosts file
    ```bash
    vi /etc/hosts
    ```
- we remove the line that points to the internal (the one that is NOT of type [127.XXX.XXX](http://127.XXX.XXX))
- reload the nginx
    ```bash
    nginx -s reload
    ```
---
# Running RTS
- navigate to path /app/client/packages/rts
```bash
yarn install

yarn start
```
This will start the RTS server on port 8091

---
# Building AppSmith
> Build the server everytime there is some change to the server.
> Compile is not necessary all the time
```bash
mvn clean compile
./build.sh -DskipTests
```

---
# Running the server
- go to the server location
```bash
./scripts/start-dev-server.sh
```
- to check the status of appsmith once it runs
```
http://localhost:8080/api/v1/users/me
```

---
# Front end
- go to client location
```bash
yarn start
```

> The app will be running on `dev.appsmith.com`