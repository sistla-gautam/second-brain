- download the .tar.gz file
- extract the file
```bash
sudo tar -xvf /tmp/apache-tomcat-10.1.24.tar.gz -C /opt/tomcat
```
- update the permissions for the user to read the folder
```bash
sudo chown -R tomcat:tomcat /opt/tomcat
```
- write a service file to start tomcat
	- service file location - `/etc/systemd/system`
	- file name - `tomcat.service`
- service file contents
```bash
[Unit] Description-Tomcat Server
After-network.target

[Service]
Type=forking User-tomcat Group-tomcat Environment="JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64" WorkingDirectory=/opt/tomcat/apache-tomcat-10.1.24 ExecStart=/opt/tomcat/apache-tomcat-10.1.24/bin/startup.sh

[Install]
WantedBy=multi-user.target
```
- reload the systemctl daemon
```bash
sudo systemctl daemon-reload
```
