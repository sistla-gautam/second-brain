# Contents
- installation script
- sample user-mapping file
- branding.jar file
---
### Installation script
- the installation script is used to install both the guacamole server and guacamole client
- the script will install tomcat, and place the guacamole client into the webapps folder of tomcat
###### Running the script
- run the script with `sudo` permissions
- to run the script, run the following command
```bash
sudo bash ./path/to/installation/script ./path/to/user/mapping/file
```
---
### User mapping file
- this contains the login details of the user who can access the guacamole client
- this also contains the configuration of the connections that the user will have access to
- the provided user-mapping file contains a user with the following details
	- username - `admin`
	- password - `admin`
> note that the provided `user-mapping.xml` does not contain any connection. Edit it to configure the required connection

- to edit the user-mapping file, please follow the guidelines from the official guacamole documentation from [Guacamole client configuration](https://guacamole.apache.org/doc/gug/configuring-guacamole.html#user-mapping-xml)
---
## White labelling
- this is done by the `branding.jar` file
- make sure to place the `branding.jar` file in the same directory of the installation script while running
- the `branding.jar` file is an extension that will sit in the `/etc/guacamole/extensions` folder and change the UI to be more in line with the Yokogawa branding
- any changes to the UI needs to be rebuilt again as a `bandin.jar` file and places in the `/etc/guacamole/extensions` folder