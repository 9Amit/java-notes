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

## Essential Java Interview Guide

When an interviewer asks you a question, they are not looking for a textbook definition.
They want to see if you understand why a concept exists and how to use it.

Here is the conversational strategy for the most important Java questions.

### 1) Why is Java platform independent?
**What you say:**  
"Java does not compile directly into machine code. Instead, the Java compiler converts your code into intermediate bytecode. As long as a system has a Java Virtual Machine (JVM) installed, that JVM can interpret and execute the bytecode. That is the secret behind Java's write once, run anywhere philosophy."

### 2) What is the difference between an Abstract Class and an Interface?
**What you say:**  
"It comes down to state and purpose. An abstract class can hold state, meaning it has instance variables, and can share concrete implementation among its child classes. An interface is strictly a contract that defines capabilities. While Java 8 added default methods to interfaces, we still generally use interfaces to define what an object can do, and abstract classes to define what an object is."

### 3) Overloading vs. Overriding: What is the difference?
**What you say:**  
"Overloading is a compile-time concept where multiple methods in the same class share the same name but have different parameters. Overriding is a runtime concept where a child class provides its own specific implementation for a method that already exists in its parent class, keeping the exact same signature."

### 4) What is the difference between `==` and `.equals()`?
**What you say:**  
"`==` is a strict operator that checks memory addresses to see if two references point to the exact same object in memory. `.equals()`, on the other hand, is a method designed to compare the actual logical content of the objects. For instance, two distinct `String` objects can contain the exact same text. `==` will return false, but `.equals()` will return true."

### 5) Why is the `String` class immutable?
**What you say:**  
"Strings are immutable primarily for security, thread safety, and memory optimization. Because a String's value can never change once created, it is inherently thread-safe. Furthermore, immutability allows the JVM to utilize the String Pool, saving significant memory by caching and reusing identical string literals."

### 6) Checked vs. Unchecked Exceptions?
**What you say:**  
"Checked exceptions are verified by the compiler, like an `IOException`, meaning Java forces you to either catch them or declare them in your method signature. Unchecked exceptions occur at runtime, like a `NullPointerException`. These are not checked at compile-time because they generally represent programming logic errors rather than recoverable environmental issues."

### 7) List vs. Set vs. Map: When do you use which?
**What you say:**  
"They serve three distinct data storage needs. I use a List when I care about maintaining insertion order and need to allow duplicate values. I use a Set when I need a collection of entirely unique elements. I use a Map when I need to store data in key-value pairs for quick lookups based on a unique key."

### 8) How do you choose between an ArrayList and a LinkedList?
**What you say:**  
"It depends on how I am interacting with the data. `ArrayList` is backed by a dynamic array, so it is very fast for random access and reading data. However, if my application requires frequent insertions or deletions in the middle of the list, a `LinkedList` is often more efficient because it shifts pointers rather than resizing an entire array."

### 9) HashMap vs. TreeMap?
**What you say:**  
"I default to a `HashMap` for pure speed. It gives O(1) average time complexity for inserts and lookups, but element order is not guaranteed. If I specifically need my keys to be sorted in natural or custom order, I use a `TreeMap`, with O(log n) operations."

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

### 11) How does Garbage Collection work in Java?
**What you say:**  
"Garbage Collection is Java's way of handling automated memory management. The JVM runs background GC processes that identify objects in heap memory that no longer have active references pointing to them. Once it finds these unreachable objects, it reclaims that memory. We still need to avoid memory leaks by removing unnecessary references."

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
