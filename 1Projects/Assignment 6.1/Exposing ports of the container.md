- this can be done in the docker compose file
- here, we need to specify the ports that will get used in the `ports` section
```yml
version: '3'
services:
  mysql:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: root
    ports:
      - "3306:3306"
    volumes:
      - mysql_data:/var/lib/mysql

volumes:
  mysql_data:

```
in this, we specify the ports as `3306:3306`. this way, the ports from `3306` of the container will be mapped to the `3306` port of the local machine