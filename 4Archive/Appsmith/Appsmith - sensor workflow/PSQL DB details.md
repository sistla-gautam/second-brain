
| key           | value            |
| ------------- | ---------------- |
| host          | 3.109.203.156    |
| port          | 5432             |
| user          | postgres         |
| password      | mysecretpassword |
| database_name | test1            |
- this does not have type of SSL configuration. do not make use of SSL flag
- the connection string is
```shell
postgres://postgres:mysecretpassword@3.109.203.156:5432/test1
```