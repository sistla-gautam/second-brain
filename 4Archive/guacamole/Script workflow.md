### Prerequisites
- Super user privileges
- .tar file of the server downloaded from the Apache guacamole release page of the required version
- internet connection (will install packages)
---
### Workflow
- checks for updates for packages with sudo update
- downloads checkinstall
- downloads the different dependencies that are required for the working of the guacamole server
- extracts the .tar file
- runs the configure script which is part of the package
- runs the make command that will build the server installer
- runs the checkinstall with the required parameters
---
### Note
- the script installs packages that have dev dependencies in them. these are required for the functioning of the guacamole server
    - pulse audio is the only dependency that is not installed - the audio when connecting to a VNC server is not available
- the parameters can be edited by changing the values inside the shell script with the required values
  