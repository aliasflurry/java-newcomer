# Java Backend Developer - Beginner Learning Plan

**Audience:** Java freshers, including learners with no programming experience.

**Core duration:** 12 weeks at 12-15 focused hours per week (144-180 hours total).

**Project:** Student Management REST API, developed after smaller Java exercises.

**Goal:** Independently build, test, explain, and run a small Java backend with guidance and code review.

This repository is a learning plan. It does not yet contain a completed application. The weekly deliverables below are work for the learner to create.

## Review of the original plan

The original plan has a useful foundation: Java, OOP, Git, Spring Boot, persistence, validation, testing, and a concrete project. Its three-week schedule is too compressed for an absolute beginner to practice these skills and retain them.

The revised plan makes these changes:

| Gap or difficulty | Revision | Why it matters for a fresher |
| --- | --- | --- |
| No environment, build, or debugging practice | Add JDK/IDE setup, Maven, stack traces, and debugger exercises | Learners must be able to run and fix their own programs |
| Collections appear before methods and classes | Teach methods, arrays, classes, and generics first | Each topic builds on concepts already practiced |
| Exceptions, file handling, and modern Java basics are missing | Add exceptions, file I/O, dates, lambdas, streams, and basic `Optional` use | These occur in ordinary Java work |
| Persistence begins with JPA without SQL | Teach relational modeling, SQL, and a small JDBC exercise first | Learners should understand what repositories do to a database |
| Testing arrives late | Start JUnit with Java exercises and expand it with the API | Correctness becomes part of the normal workflow |
| DTOs and logging are optional | Make simple DTOs, manual mapping, and useful logging required | API boundaries and troubleshooting are basic backend skills |
| CRUD is incomplete | Require list and delete endpoints; defer PATCH | A small complete API is easier to finish and assess |
| Delivery and completion criteria are unclear | Add weekly evidence, a repeatable build, basic CI, and a final demonstration | Progress is measured through working software |
| Too much abstraction too early | Teach practical separation of responsibilities; defer design-pattern catalogs and mandatory service interfaces | Beginners can explain a small design before adding abstractions |

The time estimates below are planning judgments, not a promise of job readiness. Completion gives a practical foundation for an internship or junior project; independent practice and feedback remain necessary.

## Timeline and working routine

- **Default:** 12 weeks at 12-15 hours per week.
- **Lighter schedule:** 18 weeks at 8-10 hours per week, keeping the same deliverables.
- **Full-time study:** Approximately 6-8 weeks at 25-30 hours per week, provided the learner passes each milestone. Do not assume extra hours eliminate the need for practice and review.
- A sample 12-hour week: 3 hours learning, 6 hours coding, 2 hours debugging/testing, and 1 hour reviewing and documenting. Extra time up to 15 hours is a buffer for setup problems and rework.
- Use five study sessions per week and retain rest days. Limit an unfamiliar algorithm exercise to about 45 minutes before seeking a hint.
- End each week with a short demonstration and review. Use the following week's buffer to fix small gaps; repeat a week if its core milestone is still incomplete. Move the finish date rather than skipping prerequisites.

## Overall learning objectives

By completion, the learner should be able to:

1. Write small Java programs using methods, classes, collections, exceptions, and common standard-library APIs.
2. Diagnose a failure using a stack trace, debugger, and an automated regression test.
3. Use Git branches and pull requests, explain a diff, and resolve a simple merge conflict.
4. Model a small relational database and write SQL without relying on JPA to generate it.
5. Build a layered Spring Boot REST API with DTOs, validation, persistence, and consistent errors.
6. Test normal behavior and failure cases at the unit, HTTP, and database levels.
7. Apply basic authentication, handle configuration without committing secrets, and explain the learning project's security limitations.
8. Hand the project to another person with working setup instructions and explain one request from HTTP input to database result.

## Tools and scope

Use one IDE, one build tool, and one database to reduce setup overhead:

- A JDK supported by the selected Spring Boot release; Java 21 is a reasonable course baseline. Confirm compatibility before generating the Spring project.
- IntelliJ IDEA, Eclipse, or VS Code with Java support: choose one.
- Maven and the Maven Wrapper; learn dependency management, the project layout, and the `test`, `package`, and `verify` lifecycle phases.
- Git and GitHub for version control and review.
- PostgreSQL as the final database. H2 is optional for initial exploration, not the final persistence demonstration.
- An HTTP client such as curl or Postman; a browser alone is insufficient for the API exercises.
- Spring Boot with Spring Web, Validation, Spring Data JPA, Spring Security, the PostgreSQL driver, and compatible test dependencies.
- JUnit Jupiter and Mockito, using versions compatible with the chosen Spring Boot release.

Record the exact Java, Spring Boot, Maven, and PostgreSQL versions in the learner's project README. Keep the chosen versions stable during the course and use matching documentation.

## Weekly objectives and milestones

Each week takes 12-15 hours, including practice, tests, review, and corrections. A milestone is complete only when the learner can demonstrate the deliverable and explain it without reading a tutorial line by line.

### Week 1 - Setup, Java syntax, and daily Git use

**Objective:** Create, run, change, and commit a small Java program independently.

**Learn and practice:**

- JDK vs JVM, compilation vs execution, IDE project setup, terminal navigation, and basic Maven layout.
- `main`, printing, variables, primitive types, strings, operators, and basic console input.
- `if`, `switch`, loops, and simple input checking.
- Git `clone`, `status`, `diff`, `add`, `commit`, and `push`; `.gitignore` for generated files and local configuration.

**Deliverable:** Hello World plus a console grade calculator that accepts a score and prints a grade.

**Milestone M1:** Run from the IDE and terminal; demonstrate valid, boundary, and invalid scores; commit the work and explain the diff. Fix one intentional compiler error and one logic error.

### Week 2 - Methods, arrays, debugging, and first tests

**Objective:** Break a problem into reusable methods and verify their behavior.

**Learn and practice:**

- Parameters, return values, method scope, arrays, and string operations; `equals` vs `==`.
- Wrapper types, `null`, and basic `BigDecimal` arithmetic for money.
- Reading a stack trace; breakpoints, stepping, and inspecting variables.
- JUnit assertions and normal, boundary, and invalid-input cases.

**Deliverable:** Salary calculator with a method accepting `BigDecimal hourlySalary` and `Integer monthlyWorkHours`. Reject null and negative inputs; allow zero. Construct decimal values from strings rather than floating-point values.

**Milestone M2:** Tests cover a normal salary, zero hours, negative values, and null inputs. Find and repair a seeded calculation bug with the debugger, then add a regression test.

### Week 3 - Objects and maintainable Java

**Objective:** Model student data and behavior using small, understandable classes.

**Learn and practice:**

- Classes, fields, constructors, access modifiers, packages, `this`, and static vs instance members.
- Encapsulation, interfaces, polymorphism, and basic inheritance; prefer composition when it keeps the design simpler.
- Exceptions: `try`/`catch`, throwing meaningful exceptions, and checked vs unchecked exceptions.
- `LocalDate` and `BigDecimal`; naming, formatting, and single-responsibility methods.

**Deliverable:** `StudentProfile` with first name, last name, expected graduation year, and GPA; create two students and implement a method that increases graduation year by one.

**Milestone M3:** Keep fields private, validate GPA in the 0.0-4.0 range, test the graduation-year change, and demonstrate a small interface with two implementations. Explain why a failure should be rejected rather than silently ignored.

### Week 4 - Collections, file I/O, and a console mini-project

**Objective:** Manage multiple students and persist a small local dataset without Spring.

**Learn and practice:**

- Generics; `List`/`ArrayList`, `Set`/`HashSet`, and `Map`/`HashMap`; iteration and sorting.
- `equals`/`hashCode` at a practical level and how they affect sets and map keys.
- Lambdas and simple stream `filter`, `map`, and `collect` operations; use a loop when clearer.
- Basic `Optional` use for a missing lookup result.
- Reading/writing a simple documented text format with `Files`; resource management and try-with-resources where needed. CSV quoting is outside this exercise.
- Git branches, pull requests, review feedback, and resolving one small merge conflict.

**Deliverable:** Console student registry: add, list, find, remove, save, and reload students. Use a unique ID and reject duplicate emails.

**Milestone M4:** Data survives an application restart; tests cover duplicate and missing records; malformed file input is reported clearly. Submit a pull request and address review feedback. If this is a mentored course, add **@aliasflurry** as a repository collaborator for review.

### Week 5 - SQL and relational database foundations

**Objective:** Explain and query the data before adding an ORM.

**Learn and practice:**

- Tables, rows, primary/foreign keys, `NOT NULL`, unique constraints, and simple indexes.
- `CREATE TABLE`, `INSERT`, `SELECT`, `UPDATE`, `DELETE`, filtering, ordering, aggregates, and a simple join.
- Transactions, commit/rollback, and why a unique constraint is needed even when Java checks for duplicates.
- One small JDBC exercise using a parameterized query and try-with-resources; distinguish JDBC from JPA.

**Deliverable:** SQL scripts for a student table and sample data, plus a small department table solely for the foreign-key/join exercise. The final API can remain a single student resource.

**Milestone M5:** Recreate the database from scripts, run at least eight useful queries including a join and aggregate, demonstrate rollback, and run a Java lookup using a prepared statement. No string concatenation of user input into SQL.

### Week 6 - HTTP and Spring Boot foundations

**Objective:** Build an in-memory API and explain how a request reaches application code.

**Learn and practice:**

- HTTP requests/responses, JSON, headers, methods, status codes, and path vs query parameters.
- REST resource naming, PUT replacement semantics, and idempotency at an introductory level.
- Spring vs Spring Boot, IoC/DI, beans, constructor injection, starters, and configuration.
- Controller/service separation and Maven dependencies. Introduce SOLID through small examples rather than memorizing all principles.

**Deliverable:** Generate the Spring Boot project and implement in-memory `POST /students`, `GET /students`, and `GET /students/{id}` using a controller and service.

**Milestone M6:** Demonstrate `201`, `200`, and `404` responses with an HTTP client. Explain JSON-to-Java conversion and constructor injection. Verify a basic HTTP test and a service unit test.

### Week 7 - Complete CRUD, DTOs, and validation

**Objective:** Define a predictable API contract and handle bad requests consistently.

**Learn and practice:**

- Request/response DTOs with manual mapping; keep persistence entities out of the public API.
- Bean Validation, `@Valid`, custom not-found exceptions, and central exception handling.
- Complete CRUD with PUT and DELETE; required vs optional fields and useful error messages.
- Controller tests with MockMvc and a mocked service; malformed JSON and missing-resource cases.

**Deliverable:** All five required endpoints in the contract below, initially using in-memory storage. Include request/response examples and a consistent error body.

**Milestone M7:** Demonstrate successful create/read/update/delete, an empty list, invalid input returning `400`, and a missing record returning `404`. Tests verify that PUT replaces all editable fields and cannot create a missing student.

### Week 8 - PostgreSQL, JPA, and data integrity

**Objective:** Replace in-memory storage with a database while preserving API behavior.

**Learn and practice:**

- Entity mapping, generated IDs, repositories, and the controller-service-repository flow.
- Transactions around changes and basic inspection of generated SQL.
- Database configuration through environment variables and a local development profile.
- A simple versioned schema migration using Flyway; do not rely on automatic schema updates for the final handoff.
- Unique email enforcement in both application behavior and a database constraint; map the expected duplicate-email conflict to `409`.

**Deliverable:** Persist the API's student records in PostgreSQL, with a migration that can initialize an empty database.

**Milestone M8:** Restart the API and retrieve an existing student. Initialize a fresh database from the migration. An attempted duplicate create or update returns `409` without changing existing data. Demonstrate a repository test against a dedicated PostgreSQL test database; do not run it against development data.

### Week 9 - Basic security, logging, and configuration

**Objective:** Protect the learning API and investigate failures without exposing sensitive information.

**Learn and practice:**

- Authentication vs authorization; HTTP Basic with Spring Security and a single in-memory user.
- Password encoding, environment-based credentials, and why Basic authentication requires HTTPS outside local development.
- CSRF and browser vs non-browser clients at a basic level; document the security configuration chosen for this API rather than copying unexplained settings.
- Useful SLF4J logs; avoid passwords, authorization headers, and unnecessary student personal data in logs.
- Separate development and test configuration; return safe error messages without stack traces.

**Deliverable:** Require authentication for every `/students` and `/students/**` endpoint, using credentials supplied outside source control.

**Milestone M9:** Automated HTTP tests prove missing/incorrect credentials return `401` and valid credentials can access the endpoints. Authenticated create/update/delete requests also work. Explain the credential setup and one diagnostic log. Roles and `403` behavior are optional unless role restrictions are added.

### Week 10 - Testing across layers and regression fixes

**Objective:** Prove the assembled application works beyond isolated mocked components.

**Learn and practice:**

- Unit tests vs controller tests vs database/application integration tests; use Mockito only where isolation helps.
- A full HTTP-to-PostgreSQL flow using the real service and repository.
- Isolating test data and making repeated test runs reliable.
- One small change request: add optional last-name filtering to the student list and test both matching and empty results.

**Deliverable:** A repeatable test suite, the filtering feature, and a short record of a discovered defect and its regression test.

**Milestone M10:** Tests cover the acceptance scenarios below. A full integration test creates, fetches, updates, and deletes a student with authentication enabled. Run the suite twice successfully without manual database cleanup. Do not replace scenario coverage with an arbitrary coverage percentage.

### Week 11 - Packaging, documentation, and handoff rehearsal

**Objective:** Make the project build and run outside the author's IDE.

**Learn and practice:**

- Maven Wrapper, an executable JAR, required environment variables, and basic CI.
- A GitHub Actions workflow that builds and runs the required suite on pull requests; provision a disposable PostgreSQL service for database tests.
- A clear README with prerequisites, database creation, migrations, configuration, run/test commands, and sample authenticated HTTP calls using placeholders.
- An HTTP request collection or equivalent reproducible examples and a simple architecture diagram.

**Deliverable:** Runnable JAR, working CI configuration, API examples, and setup instructions.

**Milestone M11:** From a fresh clone in a separate directory, follow only the README to build, test, start, and call the API. Fix missing instructions. Include the Windows `mvnw.cmd` and Unix `./mvnw` command forms. CI must run database tests as well as unit tests.

### Week 12 - Review, corrections, and final demonstration

**Objective:** Finish the agreed scope and explain the implementation independently.

**Work allocation:** About 4 hours for final review, 5-8 hours for fixes and regression checks, and 3 hours for documentation and demonstration. Add no new major feature this week.

**Deliverable:** Final pull request, completed acceptance checklist, known limitations, and a 10-15 minute demo.

**Milestone M12:** Another person can run the project from the documented instructions; all required checks pass. Demonstrate one successful workflow and one failure workflow, trace a request through each layer, explain a SQL query and a test, and make one small change without following a tutorial.

## Final project contract - Student Management REST API

Keep the capstone to one student resource. A frontend, course enrollment workflow, and multiple services are outside the required scope.

### Architecture

`HTTP client -> Controller -> Service -> Repository -> PostgreSQL`

Use separate request/response DTOs and a central exception handler. A concrete service class with constructor injection is enough; introduce a service interface only when the learner can explain its benefit.

### Student fields and rules

| Field | Type | Required behavior |
| --- | --- | --- |
| `id` | `Long` | Generated by the server; absent from create/update request DTOs |
| `firstName` | `String` | Required, trimmed, nonblank, maximum 100 characters |
| `lastName` | `String` | Required, trimmed, nonblank, maximum 100 characters |
| `email` | `String` | Required, nonblank, valid format, maximum 254 characters; trim and normalize to lowercase consistently; unique database constraint on the stored value |
| `dateOfBirth` | `LocalDate` | Required and in the past; JSON format `YYYY-MM-DD` |
| `gpa` | `BigDecimal` | Required, inclusive range 0.0-4.0, at most two fractional digits; match database precision/scale |
| `enrollmentYear` | `Integer` | Required, between 1900 and the current year inclusive; use a testable year source |

The year and GPA limits are explicit learning-project business rules, not universal university rules. Bean validation must combine required-value checks with format/range checks; an email or range constraint alone does not make a field required.

### Required endpoints

All endpoints require authentication.

| Endpoint | Successful response | Required failure behavior |
| --- | --- | --- |
| `POST /students` | `201 Created`, response DTO, and `Location` header | `400` invalid input; `409` duplicate email |
| `GET /students` | `200 OK`, JSON array; `[]` when empty | Optional `lastName` query filter added in Week 10; define it as case-insensitive exact matching |
| `GET /students/{id}` | `200 OK`, response DTO | `404` missing student |
| `PUT /students/{id}` | `200 OK`, fully updated response DTO | `400` invalid/missing editable fields; `404` missing student; `409` duplicate email |
| `DELETE /students/{id}` | `204 No Content`, empty body | `404` missing student |

Use `400` for malformed JSON, invalid ID types, and invalid query values where applicable. Missing or incorrect credentials return `401`. Consistently represent application errors with `status`, `message`, `path`, and field-specific validation errors when relevant. Unexpected failures return a generic `500` response and are logged internally.

Pagination is optional: the required list endpoint serves a small teaching dataset. If pagination is added later, update its response contract and tests. PATCH is optional because omitted fields, explicit nulls, and partial validation need a separate contract.

### Required acceptance checklist

- [ ] Salary calculator and console registry milestones are complete before the capstone.
- [ ] All five REST endpoints follow the contract and use DTOs.
- [ ] Tests cover all required fields, GPA/year boundaries, malformed requests, missing IDs, and invalid ID types.
- [ ] Duplicate-email create and update return `409`; the original record is preserved after a rejected update.
- [ ] Database constraints agree with validation rules; migrations initialize a fresh PostgreSQL database.
- [ ] Persisted data survives an application restart.
- [ ] Service unit tests cover business rules and failures; controller tests cover HTTP contracts.
- [ ] Repository tests use PostgreSQL; a full integration test covers authenticated CRUD through the real layers.
- [ ] Authentication tests cover all endpoints, including write requests; no credentials are committed.
- [ ] The list filter has documented semantics and tests for matching, case differences, and no results.
- [ ] Required tests pass locally and in CI, with isolated database test data.
- [ ] A fresh clone can be built and run using the README; the executable JAR works outside the IDE.
- [ ] The learner can explain the design, debug a failure, and address a review comment independently.

## Problem solving and collaboration throughout the course

- Weeks 2-10: solve one or two short exercises per week, within the weekly time budget. Start with arrays, strings, frequency maps, duplicate detection, palindrome checks, anagrams, two-sum, and a single-pass maximum-profit problem.
- Explain the approach, test edge cases, and describe basic time/space complexity. Do not turn this course into an advanced algorithm syllabus.
- Make small, meaningful commits. From Week 4 onward, use a branch and pull request for each milestone; describe what changed and how it was checked.
- At each review, explain one design choice, one bug, and one test. With no mentor available, record a brief walkthrough and use the milestone criteria for self-review; seek external feedback when possible.
- Rebase and advanced Git history rewriting are optional. A safe branch/commit/pull/merge workflow is sufficient for this course.

## Optional work after the core project

Choose one extension at a time after M12. These estimates are additional to the core timeline.

| Extension | Extra effort | Learning objective |
| --- | --- | --- |
| Pagination and sorting | 4-6 hours | Handle bounded lists and define a stable response contract |
| OpenAPI documentation | 3-5 hours | Describe and explore the API contract |
| Docker and Docker Compose | 6-10 hours | Run the application and database reproducibly |
| Audit timestamps | 3-5 hours | Track creation/update time and test the behavior |
| PATCH | 6-10 hours | Define omitted-vs-null behavior and validate partial updates |
| Role-based authorization | 6-10 hours | Separate read/write permissions and test `403` responses |
| Basic concurrency and JVM awareness | 6-10 hours | Explain shared mutable state, thread safety of singleton services, and stack/heap/GC basics |

Defer microservices, Kafka, Kubernetes, distributed caching, complex design patterns, advanced JVM tuning, and custom JWT/OAuth implementations until this foundation is comfortable. Cloud deployment is optional; the required outcome is a reproducible local application and build.

## Official learning references

Read the relevant section while implementing a milestone; completing a short guide alone does not satisfy a milestone.

- [Dev.java learning tutorials](https://dev.java/learn/) - language, OOP, exceptions, collections, streams, and standard-library foundations.
- [Git tutorial](https://git-scm.com/docs/gittutorial) - everyday version-control workflow.
- [Maven getting started](https://maven.apache.org/guides/getting-started/index.html) and [Maven Wrapper](https://maven.apache.org/tools/mavenwrapper.html) - project builds and repeatable commands.
- [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html) - relational concepts, SQL, joins, and transactions.
- [Spring guides](https://spring.io/guides/) - select REST, JPA, validation, and transaction guides as needed.
- [Spring: testing the web layer](https://spring.io/guides/gs/testing-web/) - HTTP-layer testing foundations; match examples to the chosen Spring version.
- [Spring: securing a web application](https://spring.io/guides/gs/securing-web/) - introductory authentication concepts. This guide uses form login; the capstone requires HTTP Basic, so adapt configuration using the matching Spring Security reference documentation.
