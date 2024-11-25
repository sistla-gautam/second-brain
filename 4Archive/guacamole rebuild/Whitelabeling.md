###### extension folder creation
- we are using an extension to get the branding for guacamole login page
- the extension name is `guacamole customize loginscreen extension`
	- the extension can be found here - [Branding Extension](https://github.com/Zer0CoolX/guacamole-customize-loginscreen-extension)
- we download the `.jar` file (with the given command)
- extract the .jar file
	- the .jar file is a packaged file and can be extracted into a folder 
- the folder contains folders to hold different values
	- `images` for different images
	- `css` for different styling changes
	- `translations` for changing the text of the different texts
- we place the required files in the respective folders
- we then edit the manifest file to configure the different changes done to the folder

###### building the .jar file
- to create the required jar file. we run the following command in the directory that contains the extracted folder of the .jar
```bash
jar cf branding.jar -C ./branding_folder_name/ .
```

###### using the extension
- once built, we make use of the .jar file and place it in the `extensions` folder
- the .jar needs to be placed in the following location. this might require creating a new folder if required (`extesions` folder might not be created)
	- `/etc/guacamole/extension/branding.jar`
