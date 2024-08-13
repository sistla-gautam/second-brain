### Installing postgres 
- run this in the WSL (ubuntu) terminal
```shell
sudo apt install postgresql postgresql-contrib
```
confirm the version of the DB using the command
```shell
psql --version
```

### Configuring postgres
- default user - pastgres requires a password to be able to work
- setting the password
```shell
sudo passwd postgres
```
### PSQL accounts
- run this in the WSL terminal to show all the different accounts that were created for psql
```shell
psql --command="\du"
```