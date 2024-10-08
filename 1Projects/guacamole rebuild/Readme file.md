# Contents
- installation script
- branding.jar file
- postgres database details
---
### Installation script
- the installation script is used to install both the guacamole server and guacamole client
- the script will install tomcat, and place the guacamole client into the webapps folder of tomcat
###### Running the script
- run the script with `sudo` permissions
- to run the script, run the following command
```bash
sudo bash ./path/to/installation/script
```
- the folder needs to contain the branding.jar file also in the same folder as the 
---
## White labelling
- this is done by the `branding.jar` file
- make sure to place the `branding.jar` file in the same directory of the installation script while running
- the `branding.jar` file is an extension that will sit in the `/etc/guacamole/extensions` folder and change the UI to be more in line with the Yokogawa branding
- any changes to the UI needs to be rebuilt again as a `bandin.jar` file and places in the `/etc/guacamole/extensions` folder
---
## Postgres database details
- the postgres database is installed with a `postgres` user
- the password can be set in the script at the star of the script
```bash

DB_PASSWORD='your_secure_password' # Change this to your desired password

```
#### default username and password with postgres
`username` - `guacadmin`
`password` - `guacadmin`
