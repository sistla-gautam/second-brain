_useful while testing for print functions_

---
### steps
1. take the current system.out output stream and keep it in a variable
2. create a new bytearrayoutputstream
    
    ```java
        PrintStream originalOut = System.out;
        ByteArrayOutputStream testOut = new ByteArrayOutputStream();
    ```
3. change the output streams of the program before and after the tests
    
    ```java
        @Before
        public void setUpStreams() {
            System.setOut(new PrintStream(testOut));
        }
    
        @After
        public void setDownStreams() {
            System.setOut(originalOut);
        }
    ```
    
4. now we can use the testout to test the values. anything printed into testout can be converted into string values and hence compared
    
    ```java
            assertEquals(<expected output>, testOut.toString().trim());
    
    ```