- pass the type of class to be created also to a constructor?
```java
if (type == 'S') {  
  
    SimpleInterest simpleInterest = new SimpleInterest(principal, rate, period);  
    System.out.println(simpleInterest);  
    System.out.println("Final amount: " + String.format("%.2f", simpleInterest.getFinalAmount()));  
} else if (type == 'C') {  
  
    CompoundInterest compoundInterest = new CompoundInterest(principal, rate, period);  
    System.out.println(compoundInterest);  
    System.out.println("Final amount: " + String.format("%.2f", compoundInterest.getFinalAmount()));  
}
```

maybe switch this to
```java
Interest iinterest = new Interest(priincipal,  rate,  period, type
 <char>)
```