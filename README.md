# Java Backend Developer - Beginner Learning Plan

**Audience:** Java freshers, including learners with no programming experience.

**Estimated core effort:** 144-180 focused hours, organized by task rather than calendar week.

**Project:** Student Management REST API, developed after smaller Java exercises.

**Goal:** Independently build, test, explain, and run a small Java backend with guidance and code review.

This repository is a learning plan. It does not yet contain a completed application. The task deliverables below are work for the learner to create.

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

## Task estimates, objectives, and milestones

Each stage groups related tasks and retains a clear completion milestone. The task estimates add up to 12-15 hours per stage and 144-180 hours overall. A milestone is complete only when the learner can demonstrate the deliverable and explain it without reading a tutorial line by line.

### Stage 1 - Setup, Java syntax, and daily Git use

**Objective:** Create, run, change, and commit a small Java program independently.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Install the JDK and IDE; run Hello World from the IDE and terminal; explain JDK/JVM and compilation/execution | 2-3 | - |
| Practice variables, primitive types, strings, operators, printing, and console input | 3 | - |
| Practice conditions, switch, loops, and input checks | 2-3 | - |
| Learn basic Maven layout and Git clone/status/diff/add/commit/push; configure .gitignore | 2 | - |
| Build the grade calculator and check normal, boundary, and invalid scores | 2-3 | - |
| Fix intentional compiler/logic errors, review the diff, and demonstrate M1 | 1 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** Hello World plus a console grade calculator that accepts a score and prints a grade.

**Milestone M1:** Run from the IDE and terminal; demonstrate valid, boundary, and invalid scores; commit the work and explain the diff. Fix one intentional compiler error and one logic error.

### Stage 2 - Methods, arrays, debugging, and first tests

**Objective:** Break a problem into reusable methods and verify their behavior.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Practice methods, scope, arrays, string operations, and equals vs == | 3 | - |
| Practice wrapper types, null handling, and BigDecimal arithmetic | 2 | - |
| Read a stack trace and use breakpoints, stepping, and variable inspection | 2-3 | - |
| Build the salary calculator and write JUnit normal, boundary, and invalid-input tests | 3-4 | - |
| Solve one short array/string exercise and explain its edge cases | 1 | - |
| Repair the seeded bug, add a regression test, and demonstrate M2 | 1-2 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** Salary calculator with a method accepting `BigDecimal hourlySalary` and `Integer monthlyWorkHours`. Reject null and negative inputs; allow zero. Construct decimal values from strings rather than floating-point values.

**Milestone M2:** Tests cover a normal salary, zero hours, negative values, and null inputs. Find and repair a seeded calculation bug with the debugger, then add a regression test.

### Stage 3 - Objects and maintainable Java

**Objective:** Model student data and behavior using small, understandable classes.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Practice classes, fields, constructors, packages, access modifiers, this, and static vs instance members | 3 | - |
| Practice encapsulation, interfaces, polymorphism, inheritance, and composition | 2-3 | - |
| Practice exceptions, LocalDate, BigDecimal, naming, and small methods | 2-3 | - |
| Build and test StudentProfile and the two interface implementations | 3 | - |
| Solve one short string exercise and explain its edge cases | 1 | - |
| Review validation and design choices; demonstrate M3 and address corrections | 1-2 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** `StudentProfile` with first name, last name, expected graduation year, and GPA; create two students and implement a method that increases graduation year by one.

**Milestone M3:** Keep fields private, validate GPA in the 0.0-4.0 range, test the graduation-year change, and demonstrate a small interface with two implementations. Explain why a failure should be rejected rather than silently ignored.

### Stage 4 - Collections, file I/O, and a console mini-project

**Objective:** Manage multiple students and persist a small local dataset without Spring.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Practice generics, List/Set/Map, iteration, sorting, and equals/hashCode behavior | 2-3 | - |
| Practice simple lambdas, stream operations, and Optional lookups | 2 | - |
| Practice Files, a simple text format, and resource/error handling | 2 | - |
| Build and test registry add/list/find/remove/save/reload, duplicate checks, and malformed-file behavior | 3-4 | - |
| Practice branching, a pull request, and a small merge conflict; address feedback and demonstrate M4 | 2-3 | - |
| Solve one short frequency-map or duplicate-detection exercise | 1 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** Console student registry: add, list, find, remove, save, and reload students. Use a unique ID and reject duplicate emails.

**Milestone M4:** Data survives an application restart; tests cover duplicate and missing records; malformed file input is reported clearly. Submit a pull request and address review feedback. If this is a mentored course, add **@aliasflurry** as a repository collaborator for review.

### Stage 5 - SQL and relational database foundations

**Objective:** Explain and query the data before adding an ORM.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Set up PostgreSQL and model student/department tables with keys, constraints, and a simple index | 3 | - |
| Write schema/sample-data scripts and practice CRUD queries, filtering, ordering, aggregates, and a join | 3-4 | - |
| Practice transactions and demonstrate commit/rollback and uniqueness enforcement | 1-2 | - |
| Write a JDBC prepared-statement lookup with try-with-resources; explain JDBC vs JPA | 3 | - |
| Solve one short palindrome or anagram exercise | 1 | - |
| Recreate the database, demonstrate at least eight queries and M5, and correct issues | 1-2 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** SQL scripts for a student table and sample data, plus a small department table solely for the foreign-key/join exercise. The final API can remain a single student resource.

**Milestone M5:** Recreate the database from scripts, run at least eight useful queries including a join and aggregate, demonstrate rollback, and run a Java lookup using a prepared statement. No string concatenation of user input into SQL.

### Stage 6 - HTTP and Spring Boot foundations

**Objective:** Build an in-memory API and explain how a request reaches application code.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Practice HTTP, JSON, headers, methods/status codes, path/query parameters, REST naming, PUT, and idempotency | 2-3 | - |
| Generate Spring Boot project; learn IoC/DI, beans, constructor injection, starters, and configuration | 3 | - |
| Implement the three in-memory endpoints with controller/service separation and explain a small SOLID example | 3-4 | - |
| Write a basic HTTP test and service unit test; demonstrate 201/200/404 with an HTTP client | 2-3 | - |
| Solve one short two-sum exercise | 1 | - |
| Trace a request, review the design, and demonstrate M6 | 1 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** Generate the Spring Boot project and implement in-memory `POST /students`, `GET /students`, and `GET /students/{id}` using a controller and service.

**Milestone M6:** Demonstrate `201`, `200`, and `404` responses with an HTTP client. Explain JSON-to-Java conversion and constructor injection. Verify a basic HTTP test and a service unit test.

### Stage 7 - Complete CRUD, DTOs, and validation

**Objective:** Define a predictable API contract and handle bad requests consistently.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Create request/response DTOs and manual mapping | 2 | - |
| Add Bean Validation, custom not-found exceptions, central handling, and a consistent error body | 3-4 | - |
| Implement PUT and DELETE and document all five endpoint examples | 3-4 | - |
| Write MockMvc tests with a mocked service for CRUD, malformed JSON, validation, and missing records | 2-3 | - |
| Solve one short collections exercise and explain complexity | 1 | - |
| Verify full replacement semantics, demonstrate M7, and address review feedback | 1 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** All five required endpoints in the contract below, initially using in-memory storage. Include request/response examples and a consistent error body.

**Milestone M7:** Demonstrate successful create/read/update/delete, an empty list, invalid input returning `400`, and a missing record returning `404`. Tests verify that PUT replaces all editable fields and cannot create a missing student.

### Stage 8 - PostgreSQL, JPA, and data integrity

**Objective:** Replace in-memory storage with a database while preserving API behavior.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Map the student entity, generated ID, and repository; replace in-memory storage with PostgreSQL | 3-4 | - |
| Add transactional changes, inspect generated SQL, and configure environment variables and a development profile | 2 | - |
| Create a Flyway migration and enforce normalized unique email values in the database | 2-3 | - |
| Map duplicate-email conflicts to 409 and test repository behavior with an isolated PostgreSQL database | 3-4 | - |
| Solve one short single-pass maximum-profit exercise | 1 | - |
| Verify restart persistence and fresh-database setup; demonstrate M8 | 1 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** Persist the API's student records in PostgreSQL, with a migration that can initialize an empty database.

**Milestone M8:** Restart the API and retrieve an existing student. Initialize a fresh database from the migration. An attempted duplicate create or update returns `409` without changing existing data. Demonstrate a repository test against a dedicated PostgreSQL test database; do not run it against development data.

### Stage 9 - Basic security, logging, and configuration

**Objective:** Protect the learning API and investigate failures without exposing sensitive information.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Learn authentication vs authorization and configure HTTP Basic for all student endpoints | 3-4 | - |
| Configure encoded credentials outside source control and separate development/test settings | 2 | - |
| Explain HTTPS and CSRF considerations; document the chosen security configuration | 2-3 | - |
| Add useful SLF4J logs, safe error responses, and authentication tests for read/write endpoints | 3-4 | - |
| Solve one short problem-solving exercise and explain edge cases | 1 | - |
| Inspect logs and credential handling; demonstrate M9 and address corrections | 1 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** Require authentication for every `/students` and `/students/**` endpoint, using credentials supplied outside source control.

**Milestone M9:** Automated HTTP tests prove missing/incorrect credentials return `401` and valid credentials can access the endpoints. Authenticated create/update/delete requests also work. Explain the credential setup and one diagnostic log. Roles and `403` behavior are optional unless role restrictions are added.

### Stage 10 - Testing across layers and regression fixes

**Objective:** Prove the assembled application works beyond isolated mocked components.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Review test boundaries and expand service/controller coverage for the acceptance scenarios | 2-3 | - |
| Build an authenticated HTTP-to-PostgreSQL CRUD integration test using real application layers | 3-4 | - |
| Isolate test data, run the suite twice, and repair a defect with a regression test | 3-4 | - |
| Implement and test case-insensitive exact last-name filtering, including empty results | 2 | - |
| Solve one short problem-solving exercise and explain complexity | 1 | - |
| Document the defect and demonstrate M10 | 1 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** A repeatable test suite, the filtering feature, and a short record of a discovered defect and its regression test.

**Milestone M10:** Tests cover the acceptance scenarios below. A full integration test creates, fetches, updates, and deletes a student with authentication enabled. Run the suite twice successfully without manual database cleanup. Do not replace scenario coverage with an arbitrary coverage percentage.

### Stage 11 - Packaging, documentation, and handoff rehearsal

**Objective:** Make the project build and run outside the author's IDE.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Verify Maven Wrapper commands and package/run an executable JAR outside the IDE | 2 | - |
| Configure GitHub Actions to run the required suite with a disposable PostgreSQL service | 3-4 | - |
| Write setup, migration, configuration, run/test, and authenticated-request instructions | 3-4 | - |
| Prepare reproducible HTTP examples and a simple architecture diagram | 2 | - |
| Rehearse setup from a fresh clone, fix instructions/CI failures, and demonstrate M11 | 2-3 | - |
| **Stage total** | **12-15** | - |

**Deliverable:** Runnable JAR, working CI configuration, API examples, and setup instructions.

**Milestone M11:** From a fresh clone in a separate directory, follow only the README to build, test, start, and call the API. Fix missing instructions. Include the Windows `mvnw.cmd` and Unix `./mvnw` command forms. CI must run database tests as well as unit tests.

### Stage 12 - Review, corrections, and final demonstration

**Objective:** Finish the agreed scope and explain the implementation independently.

**Tasks and estimated hours:**

| Task | Estimated hours | Actual hours |
| --- | --- | --- |
| Review the full acceptance checklist and collect evidence for each requirement | 4 | - |
| Fix review findings and run the relevant regression checks | 5-8 | - |
| Finalize the pull request, README, and known limitations | 1 | - |
| Prepare and deliver the demo, explain the design/tests/SQL, and make one small independent change for M12 | 2 | - |
| **Stage total** | **12-15** | - |

Keep this stage for review and completion; add no new major feature.

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
| `GET /students` | `200 OK`, JSON array; `[]` when empty | Optional `lastName` query filter added in Stage 10; define it as case-insensitive exact matching |
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

- Stages 2-10 each include one short problem-solving exercise in their task estimates. Additional exercises are optional extra effort. Start with arrays, strings, frequency maps, duplicate detection, palindrome checks, anagrams, two-sum, and a single-pass maximum-profit problem.
- Explain the approach, test edge cases, and describe basic time/space complexity. Do not turn this course into an advanced algorithm syllabus.
- Make small, meaningful commits. From Stage 4 onward, use a branch and pull request for each milestone; describe what changed and how it was checked.
- At each review, explain one design choice, one bug, and one test. With no mentor available, record a brief walkthrough and use the milestone criteria for self-review; seek external feedback when possible.
- Rebase and advanced Git history rewriting are optional. A safe branch/commit/pull/merge workflow is sufficient for this course.

## Optional work after the core project

Choose one extension at a time after M12. These estimates are additional to the core effort estimate.

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
