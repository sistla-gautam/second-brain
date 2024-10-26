## User flow
- Add -> Add button -> do the POST -> redirect back to the list
- Edit -> the same .jsp as the Add -> prefill the values -> edit the values -> redirect back to list
- delete -> delete servlet -> redirect to the list

### comments
- only redirection 
	- no HTML flushed from the servlet
- every servlet
	- should only contain the `doGet`, `doPost`, `redirect` methods

---
# final servlets
###### functionality needed
- list -> find but with no conditions
- adding
- deleting
- finding
- editing

###### servlets needed
- find
- add
- edit
- search

---
# find servlet and the rendering page
#### how to pass the data from servlet to the front end
- JSON
- forwarding to JSP

###### forwarding to JSP
server code
```java
import javax.servlet.RequestDispatcher;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.util.List;

public class PersonServlet extends HttpServlet {
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        
        String id = request.getParameter("id");
        String number = request.getParameter("number");
        String firstName = request.getParameter("firstName");
        String lastName = request.getParameter("lastName");
        String address1 = request.getParameter("address1");
        String address2 = request.getParameter("address2");
        String city = request.getParameter("city");
        String state = request.getParameter("state");
        String country = request.getParameter("country");

        // Check if all parameters are empty
        if (id == null || number == null || firstName == null || lastName == null ||
            address1 == null || address2 == null || city == null || state == null || country == null) {
            
            // Call the list method to get the list of persons
            List<Person> list = DBMapping.list();

            // Set the list as a request attribute
            request.setAttribute("personList", list);

            // Forward the request to the JSP page
            RequestDispatcher dispatcher = request.getRequestDispatcher("list.jsp");
            dispatcher.forward(request, response);
        }
    }
}

```

JSP code
```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Person List</title>
</head>
<body>
<h2>Person List</h2>
<table border="1">
    <tr>
        <th>ID</th>
        <th>Number</th>
        <th>First Name</th>
        <th>Last Name</th>
        <!-- other columns as needed -->
    </tr>
    <c:forEach var="person" items="${personList}">
        <tr>
            <td>${person.id}</td>
            <td>${person.number}</td>
            <td>${person.firstName}</td>
            <td>${person.lastName}</td>
            <!-- other columns as needed -->
        </tr>
    </c:forEach>
</table>
</body>
</html>
```