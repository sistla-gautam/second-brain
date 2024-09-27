### install dependencies
```bash
sudo apt update && sudo apt upgrade
```

```bash
add-apt-repository ppa:remmina-ppa-team/remmina-next-daily  
```

```bash
sudo apt install -y gcc vim curl wget g++ libcairo2-dev libjpeg-turbo8-dev libpng-dev libtool-bin libossp-uuid-dev libavcodec-dev  libavformat-dev libavutil-dev libswscale-dev build-essential libpango1.0-dev libssh2-1-dev libvncserver-dev libtelnet-dev libpulse-dev libssl-dev libvorbis-dev libwebp-dev libwebsockets-dev ubuntu-desktop-minimal freerdp2-dev freerdp2-x11 xrdp -y
```

```bash
sudo apt install openjdk-11-jdk
```

### setup tomcat
- create new `tomcat` user
```bash
useradd -m -U -d /opt/tomcat -s /bin/false tomcat
```
- download tomcat
```bash
wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.95/bin/apache-tomcat-9.0.95.tar.gz
```
- extract tomcat
```bash
tar -xzf apache-tomcat-*.tar.gz -C /opt/tomcat/
```
- rename and change ownership
```
mv /opt/tomcat/apache-tomcat-*/ /opt/tomcat/tomcatapp
chown -R tomcat :/opt/tomcat
```
- enable executable for all the `.sh` files
```bash
find /opt/tomcat/tomcatapp/bin/ -type f -iname "*.sh" -exec chmod +x {} \;
```

> ==TODO== - find a way to create a file and add contents to it as a shell command
- create a tomcat systemd file
```bash
vim /etc/systemd/system/tomcat.service
```
- add contents to it
```bash
[Unit]
Description=Tomcat 9 servlet container
After=network.target

[Service]
Type=forking

User=tomcat
Group=tomcat

Environment="JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64"
Environment="JAVA_OPTS=-Djava.security.egd=file:///dev/urandom -Djava.awt.headless=true"

Environment="CATALINA_BASE=/opt/tomcat/tomcatapp"
Environment="CATALINA_HOME=/opt/tomcat/tomcatapp"
Environment="CATALINA_PID=/opt/tomcat/tomcatapp/temp/tomcat.pid"
Environment="CATALINA_OPTS=-Xms512M -Xmx1024M -server -XX:+UseParallelGC"

ExecStart=/opt/tomcat/tomcatapp/bin/startup.sh
ExecStop=/opt/tomcat/tomcatapp/bin/shutdown.sh

[Install]
WantedBy=multi-user.target
```
- reload the `systemctl`
```bash
sudo systemctl daemon-reload
```
### install apache server
- download the server .tar.gz
```bash
wget https://apache.org/dyn/closer.lua/guacamole/1.5.5/source/guacamole-server-1.5.5.tar.gz
```
- extract it and cd into it
```bash
tar -xzf guacamole-server-1.5.5.tar.gz
cd guacamole-server-1.5.5/
```
- run the `./configure` script with the flags
```bash
./configure --with-init-dir=/etc/init.d
```
- compile and install
```bash
make && make install
ldconfig
```
- create a `guacd.conf` file in the correct location
```bash
mkdir /etc/guacamole
vi /etc/guacamole/guacd.conf
```
> ==TODO== - find a way to create a file and add contents to it as a shell command

file contents
```
[daemon]
pid_file = /var/run/guacd.pid
#log_level = debug

[server]
#bind_host = localhost
bind_host = 127.0.0.1
bind_port = 4822

#[ssl]
#server_certificate = /etc/ssl/certs/guacd.crt
#server_key = /etc/ssl/private/guacd.key
```
- reload the daemon
```bash
sudo systemctl daemon-reload
```

### install guacamole client
- download the `.war` file
```bash
wget https://archive.apache.org/dist/guacamole/1.5.5/binary/guacamole-1.5.5.war
```
- move and rename the file
```bash
mv ~/guacamole-1.4.0.war /etc/guacamole/guacamole.war
```
- create a symbolic link
```bash
ln -s /etc/guacamole/guacamole.war /opt/tomcat/tomcatapp/webapps
```
- set `GUACAMOLE_HOME` env var
```bash
echo "GUACAMOLE_HOME=/etc/guacamole" | sudo tee -a /etc/default/tomcat
echo "export GUACAMOLE_HOME=/etc/guacamole" | sudo tee -a /etc/profile
```
- create a `guacamole.properties` file
```bash
vim /etc/guacamole/guacamole.properties
```
- add file contents
```
guacd-hostname: localhost
guacd-port:  4822
user-mapping:  /etc/guacamole/user-mapping.xml
auth-provider:  net.sourceforge.guacamole.net.basic.BasicFileAuthenticationProvider
```
- create required symbolic links
```bash
ln -s /etc/guacamole /opt/tomcat/tomcatapp/.guacamole
```
- change the ownership at the required places
```bash
chown -R tomcat: /opt/tomcat
```
- create a user-mapping.xml
```bash
vim /etc/guacamole/user-mapping.xml
```
- file contents
```
<user-mapping>
	<authorize
		username="admin"
		password="admin">
		<connection name = "sample"></connection>
	</authorize>
</user-mapping>
```

### restart every service
```bash
sudo systemctl tomcat.service guacd.service
```