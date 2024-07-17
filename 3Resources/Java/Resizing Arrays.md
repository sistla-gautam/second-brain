- Arrays.copyOf
	[https://stackoverflow.com/questions/13197702/resize-an-array-while-keeping-current-elements-in-java](https://stackoverflow.com/questions/13197702/resize-an-array-while-keeping-current-elements-in-java)
	
	[https://www.tutorialspoint.com/How-to-create-a-subarray-from-another-array-in-Java](https://www.tutorialspoint.com/How-to-create-a-subarray-from-another-array-in-Java)
	
	- done with the help of copyOf method of Arrays class
	
	1. create a new array of the required size
	    
	2. once we create the new array, use the copyOf method to fill the array with the values inside the array
	    
	    ```java
	    int[] array = new int[] {1, 2, 3, 4, 5};
	    int[] subArray = Arrays.copyOfRange(array, 0, 2);
	    ```
	    
	    function parameters
	    
	    - source array - from where the array needs to read from
	    - starting index - index from which to start the copy (inclusive)
	    - ending index - index to which the copy takes place (exclusive)
- System.arraycopy
	[https://stackoverflow.com/questions/13197702/resize-an-array-while-keeping-current-elements-in-java](https://stackoverflow.com/questions/13197702/resize-an-array-while-keeping-current-elements-in-java)
	
	similar approach to the Arrays.copyOf method
	
	```java
	System.arraycopy(sourceArray, sourcePosition, destinationArray, destinationPosition, lenght);
	```
	
	- source array - array from which the data is copied
	- source position - position in the source array from which the value will be read
	- destination array - array to which the data will be copied
	- destination position - position in the destination array from which the copy will be passed to
	- length - length of characters which will be copied