# Java and Spring Boot Notes

This repository contains beginner-to-intermediate notes for **Java** and **Spring Boot**.
The goal is to keep everything simple, practical, and easy to revise from GitHub.

## Topics

### Java
- Basics: variables, data types, operators
- OOP concepts: class, object, inheritance, polymorphism
- Collections: List, Set, Map
- Exception handling
- Java 8 features (Lambda, Stream API)

### Spring Boot
- What Spring Boot is and why to use it
- Project structure
- Dependency Injection
- REST API basics
- JPA and database basics
- Profiles and configuration

## Notes Files

- [Java Notes](notes/java-notes.md)
- [Spring Boot Notes](notes/springboot-notes.md)

## Java Interview: 50 Questions with Answer Strategy

Use this format in interviews:
- **Direct Answer** -> 1-2 lines
- **Why/How** -> 1 line
- **Example** -> 1 short practical example

1) **What is Java?**  
**Answer:** Java is an object-oriented, class-based language that runs on the JVM.  
**How to answer interviewer:** Mention portability ("write once, run anywhere"), OOP support, and strong ecosystem.

2) **Why is Java platform independent?**  
**Answer:** Java code compiles to bytecode, and bytecode runs on any OS with a JVM.  
**How to answer interviewer:** Explain source code -> bytecode -> JVM flow clearly.

3) **What is JVM, JRE, and JDK?**  
**Answer:** JVM executes bytecode, JRE provides runtime environment, JDK includes tools like `javac`.  
**How to answer interviewer:** Keep distinction short and precise.

4) **What is OOP?**  
**Answer:** OOP organizes code using objects and classes with encapsulation, inheritance, polymorphism, abstraction.  
**How to answer interviewer:** Define OOP and quickly list the 4 pillars.

5) **What is a class and object?**  
**Answer:** A class is a blueprint; an object is an instance of that class.  
**How to answer interviewer:** Give a simple real-world example like Car class and car object.

6) **What is encapsulation?**  
**Answer:** Binding data and methods together and restricting direct data access.  
**How to answer interviewer:** Mention private fields + public getters/setters.

7) **What is inheritance?**  
**Answer:** Inheritance lets one class acquire properties and behavior of another class using `extends`.  
**How to answer interviewer:** Add benefit: code reuse and hierarchy modeling.

8) **What is polymorphism?**  
**Answer:** Same method name can behave differently based on object/type.  
**How to answer interviewer:** Mention method overloading (compile-time) and overriding (runtime).

9) **What is abstraction?**  
**Answer:** Hiding implementation details and showing only essential behavior.  
**How to answer interviewer:** Mention abstract classes and interfaces.

10) **Difference between abstract class and interface?**  
**Answer:** Abstract class can have state and concrete methods; interface defines contract (plus default/static methods).  
**How to answer interviewer:** Say "use interface for capability contract, abstract class for shared base behavior."

11) **What is method overloading?**  
**Answer:** Same method name with different parameters in same class.  
**How to answer interviewer:** Mention compile-time polymorphism.

12) **What is method overriding?**  
**Answer:** Child class redefines parent method with same signature.  
**How to answer interviewer:** Mention runtime polymorphism and `@Override`.

13) **Can we override static methods?**  
**Answer:** No, static methods are hidden, not overridden.  
**How to answer interviewer:** Use the term "method hiding."

14) **Can we override private methods?**  
**Answer:** No, private methods are not visible in subclass.  
**How to answer interviewer:** Short and direct: "No visibility, so no override."

15) **What is constructor?**  
**Answer:** A special method used to initialize objects; it has same name as class and no return type.  
**How to answer interviewer:** Mention default and parameterized constructors.

16) **What is `this` keyword?**  
**Answer:** `this` refers to current object instance.  
**How to answer interviewer:** Mention constructor chaining using `this()`.

17) **What is `super` keyword?**  
**Answer:** `super` refers to parent class members and constructor.  
**How to answer interviewer:** Mention `super()` call in child constructor.

18) **What is `final` keyword?**  
**Answer:** `final` variable cannot be reassigned, method cannot be overridden, class cannot be inherited.  
**How to answer interviewer:** Cover all three usages (variable/method/class).

19) **Difference between `==` and `.equals()`?**  
**Answer:** `==` compares references (or primitive values), `.equals()` compares logical content.  
**How to answer interviewer:** Give String example.

20) **Why is String immutable?**  
**Answer:** For security, thread safety, and string pool optimization.  
**How to answer interviewer:** Mention performance and safe reuse.

21) **String vs StringBuilder vs StringBuffer?**  
**Answer:** String immutable; StringBuilder mutable and faster (not synchronized); StringBuffer mutable and thread-safe.  
**How to answer interviewer:** State when to use each in one line.

22) **What is String pool?**  
**Answer:** A JVM memory area where literal strings are reused to save memory.  
**How to answer interviewer:** Mention interned literals.

23) **What are wrapper classes?**  
**Answer:** They wrap primitive types as objects, e.g., `int` -> `Integer`.  
**How to answer interviewer:** Mention collections require objects, not primitives.

24) **What is autoboxing and unboxing?**  
**Answer:** Automatic conversion between primitive and wrapper types.  
**How to answer interviewer:** Example: `Integer a = 10; int b = a;`

25) **What is exception handling?**  
**Answer:** Mechanism to handle runtime errors using `try-catch-finally`, `throw`, `throws`.  
**How to answer interviewer:** Say it keeps program flow controlled.

26) **Checked vs unchecked exceptions?**  
**Answer:** Checked are compile-time checked (`IOException`), unchecked are runtime (`NullPointerException`).  
**How to answer interviewer:** Mention `RuntimeException` hierarchy.

27) **Difference between `throw` and `throws`?**  
**Answer:** `throw` actually throws exception; `throws` declares possible exceptions in method signature.  
**How to answer interviewer:** Use one quick custom exception example.

28) **What is finally block?**  
**Answer:** Block that executes usually regardless of exception, used for cleanup.  
**How to answer interviewer:** Mention closing resources.

29) **What is `try-with-resources`?**  
**Answer:** Automatically closes resources that implement `AutoCloseable`.  
**How to answer interviewer:** Say it avoids manual cleanup bugs.

30) **What are Java Collections?**  
**Answer:** Framework of interfaces and classes to store/manipulate groups of objects.  
**How to answer interviewer:** Mention List, Set, Map.

31) **List vs Set vs Map?**  
**Answer:** List ordered with duplicates; Set unique elements; Map key-value pairs.  
**How to answer interviewer:** Compare all three in one compact sentence.

32) **ArrayList vs LinkedList?**  
**Answer:** ArrayList is faster for random access; LinkedList better for frequent insert/delete in middle.  
**How to answer interviewer:** Mention underlying data structure (array vs doubly linked list).

33) **HashMap vs TreeMap?**  
**Answer:** HashMap unordered (average O(1)); TreeMap sorted by keys (O(log n)).  
**How to answer interviewer:** Mention use case: speed vs sorted order.

34) **HashSet vs TreeSet?**  
**Answer:** HashSet stores unique unordered values; TreeSet stores unique sorted values.  
**How to answer interviewer:** Mention performance difference.

35) **What is Comparable vs Comparator?**  
**Answer:** Comparable gives natural ordering inside class; Comparator defines custom ordering outside class.  
**How to answer interviewer:** Mention `compareTo()` vs `compare()`.

36) **What is an Iterator?**  
**Answer:** Interface to traverse collections one element at a time.  
**How to answer interviewer:** Mention safe removal during iteration using iterator methods.

37) **What is multithreading?**  
**Answer:** Running multiple threads concurrently to improve responsiveness and utilization.  
**How to answer interviewer:** Mention process vs thread briefly.

38) **How to create a thread in Java?**  
**Answer:** By extending `Thread`, implementing `Runnable`, or using executors.  
**How to answer interviewer:** Say modern preferred way is `ExecutorService`.

39) **What is synchronization?**  
**Answer:** Technique to control access to shared resources to avoid race conditions.  
**How to answer interviewer:** Mention `synchronized` keyword and critical section.

40) **What is deadlock?**  
**Answer:** Situation where threads wait forever for each other’s locks.  
**How to answer interviewer:** Mention lock ordering as prevention.

41) **What is volatile keyword?**  
**Answer:** Ensures visibility of variable updates across threads.  
**How to answer interviewer:** Clarify it does not provide atomicity.

42) **What is Java 8 Stream API?**  
**Answer:** API for functional-style processing of collections (filter/map/reduce).  
**How to answer interviewer:** Give one concise stream pipeline example verbally.

43) **What is a lambda expression?**  
**Answer:** A concise way to represent anonymous functions.  
**How to answer interviewer:** Mention functional interfaces.

44) **What is functional interface?**  
**Answer:** Interface with exactly one abstract method, e.g., `Runnable`, `Predicate`.  
**How to answer interviewer:** Mention `@FunctionalInterface`.

45) **What is Optional?**  
**Answer:** Container object that may or may not hold a non-null value.  
**How to answer interviewer:** Say it helps avoid NullPointerException with explicit handling.

46) **What is serialization?**  
**Answer:** Converting object state into byte stream for storage or transfer.  
**How to answer interviewer:** Mention `Serializable` and `serialVersionUID`.

47) **What is transient keyword?**  
**Answer:** `transient` fields are skipped during serialization.  
**How to answer interviewer:** Mention use for sensitive/non-persistent fields.

48) **What is garbage collection in Java?**  
**Answer:** Automatic memory management that removes unreachable objects.  
**How to answer interviewer:** Mention memory leak can still happen via unwanted references.

49) **What are access modifiers in Java?**  
**Answer:** `private`, default, `protected`, `public` control visibility scope.  
**How to answer interviewer:** Explain scope from narrowest to widest.

50) **Why do you prefer Java for backend development?**  
**Answer:** Java offers stability, performance, strong ecosystem, great frameworks (Spring Boot), and easy maintainability.  
**How to answer interviewer:** Close with practical value: enterprise support, tooling, and long-term reliability.

## Quick Start (for local run)

1. Install Java (17+ recommended)
2. Install Maven
3. Create a Spring Boot app from [Spring Initializr](https://start.spring.io/)
4. Run:

```bash
mvn spring-boot:run
```

## Suggested Repository Structure

```text
Notes_Git/
  README.md
  notes/
    java-notes.md
    springboot-notes.md
```

## Contribution

You can keep updating these files as your learning grows:
- Add examples you practiced
- Add interview questions
- Add common errors and fixes

