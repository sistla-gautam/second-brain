- need to create a new button that will replace the current upload button
- essential idea is to split the upload into 2 different buttons - one for file selection and one for upload

### cases to handle

- when the user uploads a file then hits the upload
- when the user does not upload a file, then hits the upload
- when the user uploads a file, but does not hit upload
- how the upload button will function if the file has some sort of error in it - script tag and event handlers

### user flow

- user will upload the file
- the checks of if this file is allowed to go to server is shown here
- if the file is valid, then the user should click on the upload button for the SVG to render in the dashboard
    - the button should be inactive until the user has chosen a file and is validated - the error message is displayed next to the choose SVG button until the upload SVG is become active
    - if the file is valid is when the button will be active