# Spring Boot Notes

## 1) What is Spring Boot?

Spring Boot is a framework that simplifies Spring application setup and development.

### Why use it?
- Auto-configuration
- Embedded server (Tomcat by default)
- Production-ready features (Actuator)
- Easy dependency management using starters

## 2) Common Starters

- `spring-boot-starter-web` -> REST APIs
- `spring-boot-starter-data-jpa` -> Database/JPA
- `spring-boot-starter-security` -> Authentication/Authorization
- `spring-boot-starter-test` -> Testing

## 3) Basic Project Structure

```text
src/
  main/
    java/
      com.example.demo/
        controller/
        service/
        repository/
        entity/
    resources/
      application.properties
```

## 4) Dependency Injection

Spring manages objects as beans and injects dependencies automatically.

```java
@Service
public class UserService {
}
```

```java
@RestController
@RequestMapping("/users")
public class UserController {
    private final UserService userService;

    public UserController(UserService userService) {
        this.userService = userService;
    }
}
```

## 5) REST API Basics

- `@RestController` for API controller
- `@GetMapping`, `@PostMapping`, `@PutMapping`, `@DeleteMapping`
- Use `ResponseEntity` for HTTP responses

## 6) JPA Basics

- `@Entity` for database table mapping
- `@Id` and `@GeneratedValue` for primary key
- Repository interfaces extend `JpaRepository`

```java
public interface UserRepository extends JpaRepository<User, Long> {
}
```

## 7) application.properties Examples

```properties
server.port=8080
spring.datasource.url=jdbc:mysql://localhost:3306/demo
spring.datasource.username=root
spring.datasource.password=pass
spring.jpa.hibernate.ddl-auto=update
```

## 8) Profiles

Use profiles for different environments:
- `application-dev.properties`
- `application-prod.properties`

Run with:

```bash
mvn spring-boot:run -Dspring-boot.run.profiles=dev
```

