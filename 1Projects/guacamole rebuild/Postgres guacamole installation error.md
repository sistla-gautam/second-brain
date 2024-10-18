### webapps folder not present
- getting error from line `ln: failed to create symbolic link '/opt/tomcat/tomcatapp/webapps': No such file or directory`
- the webapps folder is probably not created in the system
- happening right after the .war file is downloaded

**solution**
- create the webapps folder once the tomcat installation is done
- write a command to create one with the flag to see if it exists or not
```bash
mkdir -p /opt/tomcat/tomcatapp/webapps
```

### branding.jar is not present
- should be in the same folder as the script
- during execution, the `branding.jar` is not placed in the same folder structure??

### postgres is not installing
- we need to create the lib folder before downloading the file to it
```bash
sudo mkdir -p /etc/guacamole/lib
```