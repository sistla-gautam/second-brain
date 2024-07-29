- statements that are run by the SQL that will reduce the execution time
- this is because the statements are executed before hand and are much more efficient

#### how not to prepared statements
- most common type of query is to hard code the value to look for into the statement
```java
String sql = "SELECT * FROM phone_book WHERE id = " + person.getId();
```
- this is not the best approach, as it can lead to worse performance 

#### how to use prepared statements
- we can use the following method to execute a prepared statement
	- notice the usage of placeholder values and how they are set later in the function (?)
```java
String sql = "SELECT * FROM phone_book WHERE id = ?";
PreparedStatement pstmt = conn.prepareStatement(sql);
pstmt.setInt(1, personId); // Set the parameter value
```

#### benefits
- reduce execution time. performance overload is reduced and the statement can be executed multiple times with different parameters
- increases security and is not prone to sql injection attacks