- the function needs to be split into 2 functions which do the following things
    - first function will allow the user to choose the file that is uploaded and will run the following test
        - check if it is a valid SVG
        - check if the SVG does not contain any type of script tags
        - check if the SVG does not contain any type of event handlers
        - also needs to check if the file already exists in the minIO

### choose SVG button - function

- choose a file
- check for valid SVG
    - raise a toast message
    - set the error message in the error field
- check for script tags
    - raise a toast message
    - set the error message in the error field
- check for event handlers
    - raise a toast message
    - set the error message in the error field
- check if the file is already there in the minIO
    - raise a toast message
    - set the error message in the error field
- make the upload button visible

### upload SVG button - function

- dispatch to the storage that the file is uploaded
- make the upload svg button inactive
    - clear the error field