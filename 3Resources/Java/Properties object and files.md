- it performs similar to the hashmap, except it only accepts a <String, Sting> configuration
- it stores the data into a .properties file in the form of key = value format
    key1 = value1
    key2 = value2
- creating a new properties object
    
    ```java
    Properties prop = new Properties()
    ```
    
- reading a properties file
    
    - create a reader object to read the properties file
        
        ```java
        FileReader propreader = new FileReader(<pathToPropFile>);
        ```
        
    - create a bufferedreader object to read the properties file
        
        ```java
        BufferedReader br = new BufferedReader(propreader)
        ```
        
    - create a new properties file
        
        ```java
        Properties prop = new Properties();
        ```
        
    - load the properties file to the properties object
        
        ```java
        prop.load(propReader)
        prop.load(br);
        ```
        
- reading values from the prop object
    
    ```java
    prop.getProperties(<key>);
    ```
    
- iterating through the different keys and values of the properties
    
    ```java
    for(String key : properties.stringPropertyNames()) {
      String value = properties.getProperty(key);
      System.out.println(key + " => " + value);
    }
    ```
    
- writing values to a properties object
    
    - inserting values into the properties object
        
        ```jsx
        Properties prop = new Properties();
        prop.putAll(<hashmap_name>);
        ```
        
    - writing this properties object into a file
        
        ```jsx
        FileOutputStream outputStream = new FileOutputStream();
        prop.store(outputStream, "<comments>")
        ```