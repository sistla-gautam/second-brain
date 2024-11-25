- install postgres
```bash
sudo apt install postgres postgres-contrib
```
- download the jdbc auth extension
```bash
sudo wget https://downloads.apache.org/guacamole/1.5.5/binary/guacamole-auth-jdbc-1.5.5.tar.gz
```
- extract the .tar.gz file
```bash
sudo tar -xzf guacamole-auth-jdbc-1.5.5.tar.gz
```
- cd into the folder and move the driver to the correct place
```bash
cd ./guacamole-auth-jdbc-1.5.5/postgresql/
```
- place the jar file in the extensions folder
```bash
sudo mv ./guacamole-auth-jdbc-1.5.5/postgresql/guacamole-auth-jdbc-postgresql-1.5.5.jar /etc/guacamole/extensions/
```
- create the database
```bash
sudo -i -u postgres
createdb guacamole_db
```
- configure the database
```bash
cat schema/*.sql | psql -d guacamole_db -f -
```
> this needs to be done in the parent of the `schema` folder

- create the user and set proper permissions for the postgres database
```bash
psql -d guacamole_db -c "CREATE USER guacamole_user WITH PASSWORD 'some_password';"
psql -d guacamole_db -c "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA public TO guacamole_user;"
psql -d guacamole_db -c "GRANT SELECT, USAGE ON ALL SEQUENCES IN SCHEMA public TO guacamole_user;"
```
> remember to change the `some_password` to the required password. this password will be used to access the database

- setup the JDBC driver
```bash
sudo wget https://jdbc.postgresql.org/download/postgresql-42.7.4.jar
```
- move the file to the correct location
```bash
sudo mv ./postgresql-42.7.4.jar /etc/guacamole/lib
```
- edit the properties file
```bash
# Define variables
DB_NAME="guacamole_db"
DB_USER="guacamole_user"
DB_PASSWORD="some_password" PROPERTIES_FILE="/etc/guacamole/guacamole.properties"

{ 
echo "guacd-hostname: localhost"
echo "guacd-port: 4822"
echo ""
echo "auth-provider:net.sourceforge.guacamole.net.basic.BasicFileAuthenticationProvider"
echo "postgresql-hostname: localhost"
echo "postgresql-database: $DB_NAME"
echo "postgresql-username: $DB_USER"
echo "postgresql-password: $DB_PASSWORD"
} > $PROPERTIES_FILE

chmod 600 $PROPERTIES_FILE
```
- restart the `guacd.service` and the `tomcat.service` once the properties file is updated
```bash
sudo systemctl restart guacd.service
sudo systemctl restart tomcat.service
```