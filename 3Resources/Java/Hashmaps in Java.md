- creating a new hashmap
    
    ```java
    HashMap <String, String> hashName = new HashMap<String, String>();
    ```
    
- adding values to the hashmap
    
    ```java
    hashmap.add(<Stringvalue>,  <Stringvalue>);
    ```
    
- accessing the different values in the hashmap
    
    ```java
    hashmap.get(key)
    ```
    
- removing a particular key
    
    ```java
    hashmap.remove(key)
    ```
    
    to remove a certain value of a hashmap, we can
    
    ```java
    hashmap.values.remove(value)
    ```
    
- accessing certain values
    
    - keys
        
        ```java
        hashmap.keySet()
        ```
        
    - values
        
        ```java
        hashmap.values()
        ```
        
- iterating through the hashmap
    
    - required if we have to find the key of a given value
    - the better approach would be to do bidirectional mapping, but it is not required in case of a small sized hashmaps
    - we create a iterator that iterates through a set of the mapped values
    
    ```java
    Iterator<Map.Entry<String,String>> iter = map.entrySet().iterator();
    while (iter.hasNext()) {
        Map.Entry<String,String> entry = iter.next();
        if (entry.getValue().equals(value_you_look_for)) {
            String key_you_look_for = entry.getKey();
        }
    }
    ```