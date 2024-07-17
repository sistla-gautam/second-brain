### static var
- used to reduce the usage of the memory    
- only a single instance of the memory is created and the others simply refer to this instance    
    - new instances are not created for every object    
    ```java
    class random{
    	static int randomInt = 1;
    }
    ```
    here the randomInt variable is only assigned once in the memory regardless of the number of objects created  
### static method
- static methods are used to call the function without the need of creating an instance of the class