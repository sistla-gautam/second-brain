### step in
used to go inside the next function and its implementation
### step out
used to step out of the implementation of the current function and return back to the caller of the function
### step into
used to step execute the function without worrying about the execution of the function

---
### resources
- chatgpt
    In debugging, "step in," "step out," and "step into" are different debugging commands used to control the flow of execution during debugging sessions. Here's an explanation of each:
    1. **Step into (or Step in)**:
        - When you use "step into," the debugger moves the execution point to the next line of code to be executed, including function or method calls. If the next line of code is a function or method call, the debugger will enter the called function or method and pause execution at its first line. This allows you to debug into the called function or method, inspecting its behavior and variables.
        - Use "step into" when you want to dive into the details of how a particular function or method is implemented, or when you want to trace the flow of execution through multiple function calls.
    2. **Step out**:
        - When you use "step out," the debugger continues executing the current function or method until it returns, and then pauses execution at the caller's location. This allows you to quickly exit from the current function or method and return to its caller, without stepping through each line of code within the function or method.
        - Use "step out" when you've stepped into a function or method but realize you want to return to the caller and inspect the behavior of the calling code instead.
    3. **Step over**:
        - "Step over" is similar to "step into," but it treats function or method calls as single steps. When you use "step over," the debugger executes the entire called function or method without stepping into its implementation. The debugger pauses execution at the line of code immediately after the function or method call.
        - Use "step over" when you're not interested in diving into the details of how a function or method is implemented, but you want to continue executing the code and inspect the behavior of the caller.
    
    In summary, "step in" allows you to enter into the implementation of a function or method, "step out" allows you to quickly exit from the current function or method and return to its caller, and "step over" allows you to execute a function or method without diving into its implementation. Each command is useful for different debugging scenarios, depending on whether you want to trace the flow of execution, inspect specific functions or methods, or quickly navigate through the code.