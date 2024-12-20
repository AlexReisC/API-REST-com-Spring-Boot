# Spring Boot Notes

## How to create a Spring Boot project?
You must access [spring initializr](https://start.spring.io) and configure your project:
- Choose the project management dependency (Gradle, Maven)
- Choose the language (Java, Kotlin, or Groovy)
- Choose the Spring Boot version
- Customize the project group and artifact, and choose the Java version
- Select the dependencies

## Project Structure
- `main/`: contains the entire application code
  - `java/groupId/`: main code that makes the application run
  - `resources/application.properties`: configurations to connect to the database and more
- `test/`: classes to test your code
- `target/`: .class files and .jar
- `pom.xml`: Maven dependencies

## Mapping class to entity
To make a Java class an entity in the database, we use two Spring annotations: `@Entity` and `@Table()`. The `@Table` annotation requires a parameter, which is the name of the table in the database.

The class attributes are the columns in the table. The `@Id` annotation indicates that the attribute is the id of the table, and the `@GeneratedValue()` annotation auto-generates ids.

## Starting repository
Create an interface that extends the `JPARepository` interface. This interface provides most of the methods needed to save resources, query, delete, and more.

The `@Repository` annotation is used to indicate to Spring that this interface is a bean that will be managed.

## Creating API methods
The annotation `@RestController` is used to define a class as a controller REST in the Spring. This means a class can handle HTTP requests and return HTTP response.

`@Autowired` is used to automatic Dependecy Injection.

The `@PostMapping` is an annotation for mapping HTTP POST requests onto specific handler methods.

`@GetMapping` is an annotation for mapping HTTP GET requests onto specific handler methods.

`@RequestBody` is an annotation indicating a method parameter should be bound to the body of the web request.

