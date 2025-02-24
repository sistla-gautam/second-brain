## functional spec
- Allows the user to make use of SVGs to represent data.
    
- SVGs can be placed into the dashboard either by uploading a new one from the file system or by choosing from one of the pre-existing ones.
    
- File size cannot be greater than 5MB.
    
- File names should be unique when uploading to MinIO. If a file with the same filename exists in MinIO, the file will not be uploaded. Update the filename to a unique name and continue with the upload process.
    
- Once the SVG is selected, the different elements of the SVG can be targeted and manipulated based on hardcoded values or tag values.
    
- Multiple such values containing the element and the attribute to be changed can be chained together.
    
- Listing of elements is done in one of the following ways:
    
    - If the SVG contains elements that have the attribute `YdxDataTarget` set to `true`, only those elements will be displayed for selection.
        
    - If the SVG does not contain any such elements, then all elements will be displayed.
        
- The element list will contain one of the two values:
    
    - The ID of the element.
        
    - The relative path to the element based on a parent that contains an ID.
        
- The elements can be manipulated based on the following attributes:
    
    - **Stroke**: Changes the color of the stroke of the particular element. Accepts String, `rgb()`, and hex values.
        
    - **Stroke-width**: Changes the width of the stroke. Accepts float values.
        
    - **Fill**: Changes the fill color of the element. Accepts String, `rgb()`, and hex values.
        
    - **Opacity**: Changes the opacity of the element. Accepts float values from 0 to 1.
        
    - **Text**: Sets the text of that particular element to the input text. Accepts String values.

## Resizing
- the widget also allows the SVG to resize the SVG to fit the container size
- Once the SVG is loaded (uploaded or selected from existing ones), the user should have the option to select a checkbox that will fit the SVG to the container size
- The checkbox will scale the SVG appropriately such that it will fit the entire SVG into the widget
- This is either scale up or scale down based on the size of the SVG and the widget

---
## basic features and run through
#### Naming convention and things to keep in mind

- When a file is uploaded (lets say *xyz.svg*) this file is uploaded to MINIO.
- In order to maintain unique filenames, another file with the same name cannot be uploaded once again.
- In order to upload the same file again, make sure that the file name is changed before uploading once again.

## Resizing
- When a SVG is loaded, the user is presented with the option to scale the SVG to the widget size.
- The properties section will contain a checkbox below the file name which says "Fit SVG to widget"
- Clicking this checkbox will scale the SVG to the size of the widget
- This also includes scaling up smaller SVGs and scaling down bigger SVGs to the widget size