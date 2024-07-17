**code coverage is a metric used to measure the extent to which the code is executed**
1. **Line coverage**: Measures the percentage of lines of code that have been executed by the test suite. A line of code is considered covered if it has been executed at least once during testing.
2. **Branch coverage**: Measures the percentage of decision points (branches) in the code that have been exercised by the test suite. A branch is considered covered if both its true and false outcomes have been executed at least once during testing.
3. **Statement coverage**: Similar to line coverage, but it measures the percentage of executable statements that have been executed by the test suite. This metric may include multiple statements on a single line of code.
4. **Function coverage**: Measures the percentage of functions or methods that have been called by the test suite. A function or method is considered covered if it has been invoked at least once during testing.
5. **Path coverage**: Measures the percentage of possible execution paths through the code that have been traversed by the test suite. This is a more advanced metric that considers all possible combinations of branches and decisions in the code.

We also try to reduce the return statement to only one return statement for this very reason. 
	a function is usually expected to only have a single return statement
	this is to increase the code coverage of the code