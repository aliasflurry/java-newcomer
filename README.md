# Java Backend Developer – Complete Beginner Course Plan  
**Duration:** 3 Weeks  
**Audience:** Absolute beginners / Freshers  
**Goal:** Build strong Java fundamentals and a real Spring Boot backend application

---

# Week 1 – Java Core Fundamentals + Git

## 1. Hello World in Java
**Objective:** Create your first Java application.

### Topics
- What is Java
- Java program structure
- `main` method
- `System.out.println`

### Exercise
- Create and run a **Hello World** Java program

---

## 2. Data Types and Variables
**Objective:** Understand how Java stores and handles data.

### Topics
- Primitive data types  
  `int`, `long`, `double`, `float`, `boolean`, `char`
- Wrapper classes  
  `Integer`, `Long`, `Double`
- Variables declaration and initialization
- Type casting (implicit & explicit)

---

## 3. Java String
**Objective:** Learn how Java handles text.

### Topics
- `String` class
- Immutability
- Common methods  
  `length()`, `substring()`, `equals()`, `toUpperCase()`, `toLowerCase()`

---

## 4. Java Operators
**Objective:** Perform operations on data.

### Topics
- Arithmetic operators
- Comparison operators
- Logical operators
- Assignment operators

---

## 5. Java Decision Making
**Objective:** Control program flow.

### Topics
- `if`
- `if-else`
- `else-if`
- `switch`

---

## 6. Java Loops
**Objective:** Execute repeated logic.

### Topics
- `for`
- `while`
- `do-while`
- `break`, `continue`

---

## 7. Java Collections
**Objective:** Store and manipulate groups of data.

### Topics
- `List` → `ArrayList`
- `Set` → `HashSet`
- `Map` → `HashMap`
- Iteration techniques

---

## 8. Java Methods
**Objective:** Write reusable code.

### Topics
- Method declaration
- Parameters
- Return types
- `static` vs instance methods

---

## 9. Exercise – Salary Calculator
**Using your Hello World project**

### Requirements
Create a **static method**:
- Input 1: `hourlySalary` (`BigDecimal`)
- Input 2: `monthlyWorkHours` (`Integer`)
- Output: Monthly salary (`hourlySalary × monthlyWorkHours`)

---

## 10. Java Classes
**Objective:** Understand object structure.

### Topics
- Class definition
- Attributes
- Methods
- Constructors
- `this` keyword

---

## 11. Exercise – Student Profile

### Requirements
Create a `StudentProfile` class with:
- First name
- Last name
- Expected year to graduate
- GPA

### Tasks
- Create constructor with all attributes
- Create method to increase graduation year by **1**
- Create two students
- Print attributes
- Call method and print updated graduation year

---

## 12. Algorithm Practice (NeetCode)
Solve:
- Buy and Sell Crypto  
- Is Palindrome  
- Two Integer Sum  
- Is Anagram  
- Duplicate Integer  

---

## 13. Object-Oriented Programming (OOP)

### Topics
- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

---

## Git – 1 Day Crash Course

### Must Know
- Clone repository
- Commit code
- Pull
- Merge
- Rebase (basic)

### Exercise
1. Create GitHub repository  
2. Create branch `exercise`  
3. Add Java Core code  
4. Push to GitHub  
5. Create Pull Request to `main`  
6. Add **@aliasflurry** to repository  

---

# Week 2 – Spring Framework & Spring Boot Basics

## 1. Spring Framework Introduction
- Problems Spring solves
- Inversion of Control (IoC)
- Dependency Injection (DI)
- Spring vs Spring Boot

---

## 2. Spring Core & Dependency Injection
- Beans and scopes
- Constructor vs Setter injection
- Annotations  
  `@Component`, `@Service`, `@Repository`, `@Autowired`

---

## 3. Spring Boot Fundamentals
- `@SpringBootApplication`
- Auto-configuration
- Starter dependencies
- Project structure

---

## 4. Spring MVC Basics
- `@RestController`
- `@RequestMapping`
- `@GetMapping`, `@PostMapping`
- `@PathVariable`, `@RequestBody`

---

## 5. REST API Basics
- HTTP methods
- Status codes
- `ResponseEntity`

---

## 6. Spring Data JPA Introduction
- ORM concept
- Entities
- Repositories
- H2 database

---

## 7. Validation & Exception Handling
- Bean Validation
- `@Valid`
- `@ControllerAdvice`
- `@ExceptionHandler`

---

## 8. Testing Basics
- JUnit 5
- Mockito
- `@SpringBootTest`
- `@WebMvcTest`

---

# Week 3 – Java Backend Essentials + Mini Project

## Mini Project – Student Management REST API

### Objective
Build a **Spring Boot REST API** using clean layered architecture:
- Controller
- Service (interface + implementation)
- Repository

Include validation, database persistence, and unit testing.

---

## 1. Project Setup
Dependencies:
- Spring Web
- Spring Data JPA
- Validation
- H2 **or** PostgreSQL
- Spring Boot Test

---

## 2. Architecture
Controller - Service - Repository

---

## 3. Student Entity
Attributes:
- `id` (Long)
- `firstName` (String)
- `lastName` (String)
- `email` (String)
- `dateOfBirth` (LocalDate)
- `gpa` (BigDecimal)
- `enrollmentYear` (Integer)

---

## 4. Validation
- `@NotBlank` → firstName, lastName
- `@Email` → email
- `@NotNull` → dateOfBirth, enrollmentYear
- `@DecimalMin("0.0")`
- `@DecimalMax("4.0")` → gpa

---

## 5. Repository Layer
- Extend `JpaRepository<Student, Long>`

---

## 6. Service Layer

### Interface
- `createStudent`
- `getStudentById`
- `updateStudent`
- `patchStudent`

### Implementation
- Business logic
- Throw custom exception if student not found

---

## 7. Controller Layer (REST APIs)

### Endpoints
- POST /students
- GET /students/{id}
- PUT /students/{id}
- PATCH /students/{id}

  
---

## 8. Global Exception Handling
- `@ControllerAdvice`
- `@ExceptionHandler`

Handle:
- Student not found
- Validation errors
- Generic errors

---

## 9. Unit Testing

### Service Tests
- JUnit 5
- Mockito
- Mock repository

### Controller Tests
- `@WebMvcTest`
- Mock service
- Validate HTTP responses

---

## 10. No Authentication
### Authentication Type
- **Basic Authentication** (Required)

### Requirements
- Protect all `/students/**` endpoints
- Only authenticated users can access APIs
- Configure in-memory user for simplicity

### Roles (Optional)
- `ROLE_USER`
- `ROLE_ADMIN`

---

## Optional Enhancements
- DTO pattern
- Pagination & sorting
- Auditing fields
- Logging (SLF4J)
- Swagger / OpenAPI

---

## Final Outcome
After 3 weeks, students will be able to:
- Write clean Java code
- Apply OOP principles
- Use Git professionally
- Build Spring Boot REST APIs
- Persist data using JPA
- Write unit tests
- Understand real-world backend architecture
