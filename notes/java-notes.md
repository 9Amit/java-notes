# Java Notes

## 1) Java Basics

- Java is a high-level, object-oriented programming language.
- Java source file extension: `.java`
- Compiled to bytecode, runs on JVM.

### Example

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello Java");
    }
}
```

## 2) OOP Concepts

- **Class**: blueprint
- **Object**: instance of class
- **Encapsulation**: wrapping data + methods
- **Inheritance**: one class extends another
- **Polymorphism**: one interface, many implementations
- **Abstraction**: hide details, show behavior

## 3) Collections Framework

- `List`: ordered, allows duplicates (`ArrayList`, `LinkedList`)
- `Set`: unique elements (`HashSet`, `TreeSet`)
- `Map`: key-value pairs (`HashMap`, `TreeMap`)

## 4) Exception Handling

- `try`, `catch`, `finally`, `throw`, `throws`
- Checked vs Unchecked exceptions

```java
try {
    int a = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero");
}
```

## 5) Java 8 Features

- Lambda Expressions
- Functional Interfaces
- Stream API
- Optional

```java
List<String> names = List.of("A", "B", "C");
names.stream().filter(n -> n.startsWith("A")).forEach(System.out::println);
```

## 6) Important Interview Topics

- `final`, `finally`, `finalize`
- `==` vs `.equals()`
- `String`, `StringBuilder`, `StringBuffer`
- `HashMap` internal working (basic idea)

