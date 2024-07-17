- checking if a file path exists
    
    ```java
    File f = new File(filePathString);
    if(f.exists() && !f.isDirectory()) {
        // do something
    }
    ```
    
- file reading options
    
    - BufferedReader
        
        - reads a set of characters, places it in a buffer
        - subsequent calls, will be done by reading the buffer and not the actual file itself
    - InputStreamReader
        
        - reads the file, character by character
        - subsequent calls, will directly read from the file directly
    - Scanner class
        
        - mainly used for accepting input from the user
        - this input can also be in the form of file
        
        ```java
        File file = new File("<path>")
        Scanner scanner = new Scanner(file)
        ```
        
        - reading the data
            
            we can read the data with the scanner.next<type>()
            
            ```java
            while(scanner.hasNext()){
            	String value = scanner.nextLine();
            	int number = scanner.nextInt();
            	float floatValue = scanner.nextFloat();
            }
            ```
            
        - using a delimiter
            
            ```java
            scanner.useDelimiter("<delimiter>")
            while(scanner.hasNext()){
            	String value  = scanner.next();
            }
            ```
            
- file writing options
    
    - Looking at the common usage practices, we can see, for example, that **PrintWriter is used to write formatted text, FileOutputStream to write binary data, DataOutputStream to write primitive data types, RandomAccessFile to write to a specific position, and FileChannel to write faster in larger files.**
        
    - buffered writer (uses buffer)
        
        - writing
            
            ```java
            String str = "hello";
            Bufferedwriter writer = new BufferedWriter(new FIleWriter(filename));
            writer.write(str);
            
            writer.close();
            ```
            
        - appending
            
            - in order to append, we need to call the FileWriter with an optional parameter
            - the second parameter represents if we want to append the file or not append
                - the default is set to false and hence rewrites the entire file
                - when set to true, the file will append the file with the new data
            
            ```java
            String str = " world"
            BufferedWriter writer = new BufferedWriter(new FileWriter(filename, true));
            writer.write();
            
            writer.close();
            ```
            
    - print writer (used for formatted text)
        
        - accepts a filewriter, bufferedwriter or even a System.out as the input parameter
        
        ```java
        PrintWriter writer = new PrintWriter(new FileWriter(filename));
        writer.print("Some random string");
        writer.printf("This is also some %s value", "random");
        
        writer.close();
        ```
        
    - file output stream (writes byte data)