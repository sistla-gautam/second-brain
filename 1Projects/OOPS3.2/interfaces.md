### understanding
- classes that have methods
	- these methods define what the implemented classes need to have
- if a class implements a interface, it needs to have a way to say what these methods do
	- the class needs to have the implementation of inherited methods


### example
- Animal interface consists of what an `Animal` is supposed to do
	- it can consist of stuff like `eat`, `move` and `call`
- `Pig` class will implement the `Animal` class
	- `Pig` will implement the different methods
	- `eat` can be `Eats the plants`
	- `move` can be `Walks around the field`
	- `call` can be `Oinks`


---
# multiple interfaces
- A class an pick up different interfaces at the same time

```java
interface FirstInterface {
  public void myMethod(); // interface method
}

interface SecondInterface {
  public void myOtherMethod(); // interface method
}

class DemoClass implements FirstInterface, SecondInterface {
  public void myMethod() {
    System.out.println("Some text..");
  }
  public void myOtherMethod() {
    System.out.println("Some other text...");
  }
}

class Main {
  public static void main(String[] args) {
    DemoClass myObj = new DemoClass();
    myObj.myMethod();
    myObj.myOtherMethod();
  }
}
```


---
# interfaces vs base class
- interface is generally for a "can-do" type of relation
- base class is generally for a "is-a" type of relation