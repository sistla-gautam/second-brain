This is done using **JUNIT** package

---

## Steps to create a test file

The test file is used to run the tests of the required class

1. A new public class is created with the required class name
2. Every test case is written with a @Test
3. Following the @Test is public void function that will test certain tests of the code
4. Each test in a test case can be written by using the

```java
assertEquals(expected, actual);
```

1. A sample code would look as follows

```java
	public void largerNumberTest() {
		Basics assignm0 = new Basics();
		assertEquals(2, assignm0.getLargerNumber(1, 2));

		assignm0 = new Basics();
		assertEquals(-1, assignm0.getLargerNumber(-1, -3));

		assignm0 = new Basics();
		assertEquals(3, assignm0.getLargerNumber(0, 3));
	}
```

Where _**Basics**_ is the class that needs to be tested

<aside> 💡 A new object is created for every new test that needs to be written. This is done so as to ensure that the object is always in a fresh state before running a test

</aside>

1. Running this test file will run all the test cases. Depending on the output of the tests, the test cases will return either a pass or a fail

---

### Resources

[https://www.jetbrains.com/help/idea/performing-tests.html](https://www.jetbrains.com/help/idea/performing-tests.html)