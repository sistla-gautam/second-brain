#### initial setup
- once the container is running, we do the initial setup of the database
- we need to access the logs of the container to find the initial password
```shell
docker logs <id> | grep GENERATED
```
- this will give us the initial generated password that mysql generated

#### changing the password of the root user
- once we have the initial generated password, we will access the mysql shell with this command
```shell
docker exec -it <id> mysql -u root -p
```
- once we have the shell access to the database, we can then alter the user info with the new password
```shell
ALTER USER 'root'@'localhost' IDENTIFIED BY '_password_';
```