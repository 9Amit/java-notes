# Java and Spring Boot Notes

## Essential Java Interview Guide

When an interviewer asks you a question, they are not looking for a textbook definition.
They want to see if you understand why a concept exists and how to use it.

Here is the conversational strategy for the most important Java questions.

## Questions Index (Click to Jump)

1. [Why is Java platform independent?](#q1)
2. [What is the difference between an Abstract Class and an Interface?](#q2)
3. [Overloading vs. Overriding: What is the difference?](#q3)
4. [What is the difference between `==` and `.equals()`?](#q4)
5. [Why is the `String` class immutable?](#q5)
6. [Checked vs. Unchecked Exceptions?](#q6)
7. [List vs. Set vs. Map: When do you use which?](#q7)
8. [How do you choose between an ArrayList and a LinkedList?](#q8)
9. [HashMap vs. TreeMap?](#q9)
10. [Can you explain the Java 8 Stream API?](#q10)
11. [How does Garbage Collection work in Java?](#q11)
12. [What is the difference between JVM, JRE, and JDK?](#q12)
13. [What does the `final` keyword mean in Java?](#q13)
14. [Can static methods be overridden?](#q14)
15. [Why do `equals()` and `hashCode()` matter together, especially for `HashMap`?](#q15)
16. [What is the difference between `Comparable` and `Comparator`?](#q16)
17. [What is `try-with-resources` and `AutoCloseable`?](#q17)
18. [How do you create a thread in Java?](#q18)
19. [What is the difference between `synchronized` and `volatile`?](#q19)
20. [What is a lambda expression in Java 8?](#q20)
21. [What is `Optional` and when would you use it?](#q21)

---

<a id="q1"></a>
### 1) Why is Java platform independent?
**What you say:**  
"Java does not compile directly into machine code. Instead, the Java compiler converts your code into intermediate bytecode. As long as a system has a Java Virtual Machine (JVM) installed, that JVM can interpret and execute the bytecode. That is the secret behind Java's write once, run anywhere philosophy."

<a id="q2"></a>
### 2) What is the difference between an Abstract Class and an Interface?
**What you say:**  
"It comes down to state and purpose. An abstract class can hold state, meaning it has instance variables, and can share concrete implementation among its child classes. An interface is strictly a contract that defines capabilities. While Java 8 added default methods to interfaces, we still generally use interfaces to define what an object can do, and abstract classes to define what an object is."

<a id="q3"></a>
### 3) Overloading vs. Overriding: What is the difference?
**What you say:**  
"Overloading is a compile-time concept where multiple methods in the same class share the same name but have different parameters. Overriding is a runtime concept where a child class provides its own specific implementation for a method that already exists in its parent class, keeping the exact same signature."

<a id="q4"></a>
### 4) What is the difference between `==` and `.equals()`?
**What you say:**  
"`==` is a strict operator that checks memory addresses to see if two references point to the exact same object in memory. `.equals()`, on the other hand, is a method designed to compare the actual logical content of the objects. For instance, two distinct `String` objects can contain the exact same text. `==` will return false, but `.equals()` will return true."

<a id="q5"></a>
### 5) Why is the `String` class immutable?
**What you say:**  
"Strings are immutable primarily for security, thread safety, and memory optimization. Because a String's value can never change once created, it is inherently thread-safe. Furthermore, immutability allows the JVM to utilize the String Pool, saving significant memory by caching and reusing identical string literals."

<a id="q6"></a>
### 6) Checked vs. Unchecked Exceptions?
**What you say:**  
"Checked exceptions are verified by the compiler, like an `IOException`, meaning Java forces you to either catch them or declare them in your method signature. Unchecked exceptions occur at runtime, like a `NullPointerException`. These are not checked at compile-time because they generally represent programming logic errors rather than recoverable environmental issues."

<a id="q7"></a>
### 7) List vs. Set vs. Map: When do you use which?
**What you say:**  
"They serve three distinct data storage needs. I use a List when I care about maintaining insertion order and need to allow duplicate values. I use a Set when I need a collection of entirely unique elements. I use a Map when I need to store data in key-value pairs for quick lookups based on a unique key."

<a id="q8"></a>
### 8) How do you choose between an ArrayList and a LinkedList?
**What you say:**  
"It depends on how I am interacting with the data. `ArrayList` is backed by a dynamic array, so it is very fast for random access and reading data. However, if my application requires frequent insertions or deletions in the middle of the list, a `LinkedList` is often more efficient because it shifts pointers rather than resizing an entire array."

<a id="q9"></a>
### 9) HashMap vs. TreeMap?
**What you say:**  
"I default to a `HashMap` for pure speed. It gives O(1) average time complexity for inserts and lookups, but element order is not guaranteed. If I specifically need my keys to be sorted in natural or custom order, I use a `TreeMap`, with O(log n) operations."

<a id="q10"></a>
### 10) Can you explain the Java 8 Stream API?
**What you say:**  
"The Stream API lets us process collections of data in a functional, declarative way. Instead of writing verbose `for` loops with many `if` statements, we can chain operations like `.filter()`, `.map()`, and `.reduce()` to transform data. It improves readability and can make parallel processing easier."

Quick example to show on a whiteboard or screen:

```java
List<String> names = Arrays.asList("Alice", "Bob", "Anna");

// Getting all names starting with 'A' using Streams
names.stream()
     .filter(name -> name.startsWith("A"))
     .forEach(System.out::println);
```

<a id="q11"></a>
### 11) How does Garbage Collection work in Java?
**What you say:**  
"Garbage Collection is Java's way of handling automated memory management. The JVM runs background GC processes that identify objects in heap memory that no longer have active references pointing to them. Once it finds these unreachable objects, it reclaims that memory. We still need to avoid memory leaks by removing unnecessary references."

<a id="q12"></a>
### 12) What is the difference between JVM, JRE, and JDK?
**What you say:**  
"The JDK is the full development kit: it includes the compiler, tools like `javac`, and everything needed to build and run Java programs. The JRE is the runtime environment: enough to run Java applications but not necessarily to compile them. The JVM is the virtual machine that actually executes bytecode. I think of it as: JDK for development, JRE for running, JVM as the engine inside the JRE."

<a id="q13"></a>
### 13) What does the `final` keyword mean in Java?
**What you say:**  
"`final` has three common meanings. A `final` variable cannot be reassigned after initialization. A `final` method cannot be overridden by subclasses. A `final` class cannot be extended. I use it when I want to lock down behavior or values for safety and clarity."

<a id="q14"></a>
### 14) Can static methods be overridden?
**What you say:**  
"No, not in the true sense of overriding. Static methods belong to the class, not an instance, so what happens in a subclass is method hiding, not polymorphic override. At compile time, the call is resolved by the reference type, which is why it is easy to get surprised if you expect runtime polymorphism."

<a id="q15"></a>
### 15) Why do `equals()` and `hashCode()` matter together, especially for `HashMap`?
**What you say:**  
"`HashMap` uses the hash code to pick a bucket and `equals()` to compare keys inside that bucket. If two objects are equal according to `equals()`, they must have the same `hashCode()`, or the map will break lookups. If I override `equals()`, I override `hashCode()` too, using the same fields, so collections behave correctly."

<a id="q16"></a>
### 16) What is the difference between `Comparable` and `Comparator`?
**What you say:**  
"`Comparable` defines the natural ordering inside the class itself via `compareTo()`. `Comparator` is separate: I use it when I want multiple sorting strategies or cannot change the original class. Natural order versus custom or external order is the mental split."

<a id="q17"></a>
### 17) What is `try-with-resources` and `AutoCloseable`?
**What you say:**  
"`try-with-resources` automatically closes resources like files or connections at the end of the block. Anything that implements `AutoCloseable` can be used in the try parentheses. It is safer than manual `finally` cleanup because the compiler handles closing order and exception handling more reliably."

<a id="q18"></a>
### 18) How do you create a thread in Java?
**What you say:**  
"The classic ways are extending `Thread` or implementing `Runnable` and passing it to a `Thread`. In real applications I prefer an `ExecutorService` from the concurrency API because it manages a pool of threads, queues work, and avoids creating too many raw threads. For simple learning examples, `Runnable` plus an executor is the sweet spot."

<a id="q19"></a>
### 19) What is the difference between `synchronized` and `volatile`?
**What you say:**  
"`synchronized` provides mutual exclusion: only one thread at a time can enter a block or method on the same monitor, which also gives visibility of changes. `volatile` only guarantees visibility of a variable's updates across threads, not atomicity of compound operations. I use `volatile` for simple flags, and `synchronized` or locks when I need to protect a critical section."

<a id="q20"></a>
### 20) What is a lambda expression in Java 8?
**What you say:**  
"A lambda is a short way to pass behavior as data: an anonymous function that implements a functional interface. It removes boilerplate compared to anonymous classes. I pair it with streams and APIs like `Comparator` and `Runnable` where the interface has a single abstract method."

<a id="q21"></a>
### 21) What is `Optional` and when would you use it?
**What you say:**  
"`Optional` is a container that may or may not hold a non-null value. I use it to make absence explicit in return types instead of returning null and forcing every caller to guess. In interviews I also mention not to use `Optional` for fields or method parameters everywhere—mainly for return values where a value might be missing."


