# Java Core and Git - 1 week
## 1. Hello World in Java
**Objective:** Create your first Java application.

### Topics
- What is Java?
- Java program structure
- `main` method
- Printing output using `System.out.println`

### Exercise
- Create a simple **Hello World** Java application
- Run it from your IDE or command line

---

## 2. Data Types and Variables
**Objective:** Understand how Java stores data.

### Topics
- Primitive data types
  - `int`, `long`, `double`, `float`
  - `boolean`, `char`
- Wrapper classes
  - `Integer`, `Long`, `Double`
- Variables declaration and initialization
- Type conversion (implicit & explicit)

---

## 3. Java String
**Objective:** Learn how Java handles text.

### Topics
- `String` class
- String immutability
- Common methods
  - `length()`
  - `substring()`
  - `equals()` vs `==`
  - `toUpperCase()`, `toLowerCase()`

---

## 4. Java Operators
**Objective:** Perform operations on data.

### Topics
- Arithmetic operators (`+ - * / %`)
- Comparison operators (`== != > < >= <=`)
- Logical operators (`&& || !`)
- Assignment operators (`= += -=`)

---

## 5. Java Decision Making
**Objective:** Control program flow using conditions.

### Topics
- `if`
- `if-else`
- `else if`
- `switch`

---

## 6. Java Loops
**Objective:** Execute code repeatedly.

### Topics
- `for` loop
- `while` loop
- `do-while` loop
- `break` and `continue`

---

## 7. Java Collections
**Objective:** Store and manage groups of objects.

### Topics
- `List`
  - `ArrayList`
- `Set`
  - `HashSet`
- `Map`
  - `HashMap`
- Iteration using loops and `for-each`

---

## 8. Java Methods
**Objective:** Organize reusable code.

### Topics
- Method declaration
- Method parameters
- Return types
- `static` vs non-static methods

---

## 9. Exercise – Salary Calculator
**Using your Hello World project**

### Requirements
Create a **static method** with:
- **Input 1:** `hourlySalary` (type `BigDecimal`)
- **Input 2:** `monthlyWorkHours` (type `Integer`)
- **Output:** Monthly salary (`hourlySalary × monthlyWorkHours`)

---

## 10. Java Classes
**Objective:** Understand class structure.

### Topics
- Class definition
- Class attributes (fields)
- Class methods
- Constructors
- `this` keyword

---

## 11. Exercise – Student Profile
**Using your Hello World project**

### Requirements
Create a class named `StudentProfile` with the following attributes:
- First name
- Last name
- Expected year to graduate
- GPA

### Methods
- A method to increase the expected graduation year by **1**

### Constructor
- A constructor that initializes all attributes

### Tasks
- Create **two student profiles**
- Print all attributes
- Call the method to increase graduation year
- Print the updated expected graduation year for both students

---

### Algorithm Practice (NeetCode)
Solve the following problems:
- Buy and Sell Crypto  
  https://neetcode.io/problems/buy-and-sell-crypto
- Is Palindrome  
  https://neetcode.io/problems/is-palindrome
- Two Integer Sum  
  https://neetcode.io/problems/two-integer-sum
- Is Anagram  
  https://neetcode.io/problems/is-anagram
- Duplicate Integer  
  https://neetcode.io/problems/duplicate-integer

---

## 12. Object-Oriented Programming (OOP)
**Objective:** Learn core OOP principles.

### Topics
- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

---

## Git – 1 Day Crash Course
**Objective:** Learn essential Git commands.

### Must-Know Concepts
- Clone repository
- Commit code
- Pull changes
- Merge branches
- Rebase (basic understanding)

### Exercise
1. Create a repository on GitHub
2. Create a new branch named `exercise`
3. Add all Java Core code to the branch
4. Push the branch to GitHub
5. Create a Pull Request (or Merge Request) to `main`
6. Add **@aliasflurry** to the repository

---

## Final Outcome
By completing this plan, you will:
- Understand Java fundamentals
- Write structured Java programs
- Apply OOP concepts
- Solve basic algorithm problems
- Use Git in a real workflow

# Spring Framework - 1 week

## Day 1 – Java & Spring Basics (Foundation)

### Concepts
- Java basics
  - OOP (Inheritance, Polymorphism, Interfaces)
  - Annotations
  - Packages
- Maven basics
  - `pom.xml`
  - Dependencies
- What is Spring Framework?
  - Problems Spring solves
  - Inversion of Control (IoC)
  - Dependency Injection (DI)

### Spring Core
- Spring vs Spring Boot
- Spring Container
- Bean lifecycle (high-level)

### Hands-on
- Install JDK & IDE (IntelliJ / Eclipse)
- Create a Maven project
- Run a basic Java application

---

## Day 2 – Spring Core & Dependency Injection

### Concepts
- Spring Beans
- Bean scopes
  - `singleton`
  - `prototype`
- Dependency Injection
  - Constructor Injection (recommended)
  - Setter Injection

### Annotations
- `@Component`
- `@Service`
- `@Repository`
- `@Autowired`
- `@Qualifier`

### Configuration
- Java-based configuration
  - `@Configuration`
  - `@Bean`
- Component scanning
  - `@ComponentScan`

### Hands-on
- Create:
  - `UserService`
  - `UserRepository`
- Inject dependencies
- Run using Spring ApplicationContext

---

## Day 3 – Spring Boot Fundamentals

### Concepts
- Why Spring Boot?
  - Auto-configuration
  - Starter dependencies
- Project structure
- `@SpringBootApplication`

### Configuration
- `application.properties`
- `application.yml`
- Profiles (`dev`, `test`)

### Web Basics
- Embedded Tomcat
- REST API basics

### Hands-on
- Create a Spring Boot project
- Create REST endpoint:
  - `GET /hello`

---

## Day 4 – Spring MVC (REST APIs)

### Concepts
- MVC Architecture
- Controllers
  - `@RestController`
  - `@RequestMapping`
  - `@GetMapping`
  - `@PostMapping`

### Request Handling
- `@PathVariable`
- `@RequestParam`
- `@RequestBody`

### Response
- HTTP status codes
- `ResponseEntity`

### Hands-on
- Build in-memory CRUD APIs:
  - `POST /users`
  - `GET /users`
  - `GET /users/{id}`

---

## Day 5 – Database & Spring Data JPA

### Concepts
- ORM basics
- JPA & Hibernate
- Entity annotations
  - `@Entity`
  - `@Id`
  - `@GeneratedValue`
  - `@Table`
  - `@Column`

### Repositories
- `JpaRepository`
- Common CRUD methods

### Database
- H2 (in-memory) or PostgreSQL

### Hands-on
- Connect DB to Spring Boot
- Create `User` entity
- Implement DB-backed CRUD APIs

---

## Day 6 – Validation, Exception Handling & Security Basics

### Validation
- Bean Validation
  - `@NotNull`
  - `@Size`
  - `@Email`
- `@Valid`

### Exception Handling
- Custom exceptions
- `@ExceptionHandler`
- `@ControllerAdvice`

### Spring Security (Intro)
- What Spring Security is
- Authentication vs Authorization
- Basic Authentication
- Security filter chain (concept)

### Hands-on
- Add validation to APIs
- Global exception handling
- Secure one endpoint with Basic Auth

---

## Day 7 – Testing, Best Practices & Mini Project

### Testing
- Unit testing basics
- `@SpringBootTest`
- `@WebMvcTest`
- Mockito basics

### Best Practices
- Layered architecture
  - Controller → Service → Repository
- DTO vs Entity
- Logging with SLF4J
- Basic performance tips

### Mini Project
**User Management REST API**
- CRUD operations
- Validation
- Global exception handling
- H2 or PostgreSQL
- Basic authentication

---

## Outcome After 1 Week
You should be able to:
- Explain IoC & Dependency Injection
- Build REST APIs with Spring Boot
- Use Spring Data JPA with a database
- Handle validation & exceptions
- Write basic tests
- Understand real-world Spring project structure

