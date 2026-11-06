# Java Backend Developer - Beginner Learning Plan

**Audience:** Java freshers, including learners with no programming experience.

**Estimated core effort:** 144-180 focused hours, organized by task rather than calendar week.

**Project:** Student Management REST API, developed after smaller Java exercises.

**Goal:** Independently build, test, explain, and run a small Java backend with guidance and code review.

This repository is a learning plan. It does not yet contain a completed application. The task deliverables below are work for the learner to create.

## How to complete and submit the work

1. Start with Stage 1 and work in order. Stages 1-5 build Java and database foundations; Stages 6-12 build and finish the same REST API.
2. Read the stage objective and task bullets. Use the estimates to plan your work, and record the actual time spent on each task in your milestone notes.
3. Follow the numbered deliverable steps. Save source code, tests, and supporting files in your learner repository. Keep this learning plan separate from your application's setup README.
4. Run the checks in the stage milestone. Capture the commands, inputs, and results so another person can repeat them. For debugging exercises, ask a reviewer to introduce a small bug; if working alone, deliberately introduce and document one before repairing it.
5. Commit the completed work. From Stage 4 onward, submit a pull request that states what you built, how you checked it, and any remaining issues. Link the evidence named under **Submit** in the pull request or milestone notes.
6. Demonstrate the milestone and address corrections before moving on. Without a mentor, record a short walkthrough and check each milestone requirement yourself.

Each **Submit** line identifies the files or evidence to hand in. Each **Milestone** defines the pass criteria. The final project contract below is the source of truth for the capstone's fields, endpoints, and error behavior.

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

- **Set up Java and run your first program (2-3 hours).** Install the JDK and one IDE, confirm that `java` and `javac` are available, and create Hello World. Compile and run it from the terminal as well as the IDE. Explain that the JDK provides development tools and the JVM executes compiled Java bytecode.
- **Practice values and console input (3 hours).** Write small examples using primitive types, strings, arithmetic, comparisons, and printed output. Read a name and a score from the console, then display them in a sentence. Explain integer division and how converting input into a number can fail.
- **Control program flow (2-3 hours).** Use `if/else`, `switch`, and loops to select actions and repeat work. Practice checking a score's range before using it. Trace examples on paper to see which branch runs and when a loop stops; include nonnumeric input and boundary values.
- **Organize and track the project (2 hours).** Learn the purpose of `pom.xml`, `src/main/java`, and `src/test/java`. Clone a repository and practice Git status, diff, add, commit, and push. Add a `.gitignore` so generated build files and IDE-specific files do not clutter commits.
- **Build the grade calculator (2-3 hours).** Translate your documented grading scale into conditions, connect it to console input, and print either a grade or a useful input error. Record results for an ordinary score, every grade boundary, and invalid values so you can check the logic systematically.
- **Debug and demonstrate M1 (1 hour).** Introduce and fix one compiler error and one logic error. Explain how the compiler message differs from an incorrect runtime result, review the Git diff, and demonstrate both programs using your recorded commands.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** Hello World plus a console grade calculator that accepts a score and prints a grade.

1. Create a Maven Java project, add a `.gitignore`, and write a Hello World entry point. Run it in your IDE and from the terminal; record both procedures.
2. Define and document a grading scale for scores from 0 to 100, including the exact score at each grade boundary.
3. Write a console program that reads a score, checks that it is numeric and within range, and prints the matching grade. Show a clear message for invalid input.
4. Try a normal score, each grade boundary, values below 0 and above 100, and nonnumeric input. Fix one intentional compiler error and one logic error, then record what changed.

**Submit:** Java source, the grading scale, run instructions, sample results, and the commit containing the fixes.

**Milestone M1:** Run from the IDE and terminal; demonstrate valid, boundary, and invalid scores; commit the work and explain the diff. Fix one intentional compiler error and one logic error.

### Stage 2 - Methods, arrays, debugging, and first tests

**Objective:** Break a problem into reusable methods and verify their behavior.

**Tasks and estimated hours:**

- **Break problems into methods (3 hours).** Practice parameters, return values, local scope, arrays, and common string operations. Extract repeated logic into small methods and call them with different inputs. Compare string contents with `equals` and explain why `==` checks a different property for objects.
- **Handle numbers and missing values (2 hours).** Compare primitive values with wrapper types such as `Integer`, including what happens when a null wrapper is unboxed. Construct `BigDecimal` values from strings and practice multiplication and numeric comparison. Explain why decimal pay calculations should avoid floating-point inputs.
- **Investigate failures with the debugger (2-3 hours).** Trigger a small exception and locate the relevant source line in its stack trace. Set a breakpoint, step into and over a method, and inspect arguments and local variables. Write down the first point where the actual value differs from the expected value.
- **Implement and test salary calculation (3-4 hours).** Separate salary calculation from console input so tests can call the method directly. Add JUnit tests with clear arrange, act, and assert sections for normal pay, zero values, negative inputs, and null arguments. Run tests from the build tool as well as the IDE.
- **Solve an array or string exercise (1 hour).** Choose a small task such as finding the largest array value or counting a character. State expected behavior for empty input and explain the algorithm with a worked example before coding it.
- **Repair a bug and demonstrate M2 (1-2 hours).** Use the debugger to locate a seeded calculation error, add a regression test, and confirm that it fails before the repair and passes afterward. Explain how the new test prevents the same mistake from returning.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** Salary calculator with a method accepting `BigDecimal hourlySalary` and `Integer monthlyWorkHours`. Reject null and negative inputs; allow zero. Construct decimal values from strings rather than floating-point values.

1. Write a method that returns `hourlySalary` multiplied by `monthlyWorkHours` as a `BigDecimal`. For example, `"25.50"` and `160` should produce `4080.00`.
2. Check both inputs before calculating. Throw a clear `IllegalArgumentException` for null or negative values; accept zero pay and zero hours.
3. Add JUnit tests for normal pay, zero pay, zero hours, and null/negative values for each argument. Use string-based decimal values in the tests.
4. Introduce a calculation bug, inspect it with a breakpoint, repair it, and add a test that would fail if the bug returned.

**Submit:** Calculator method, passing tests, test command, and a short note describing the bug and debugger findings.

**Milestone M2:** Tests cover a normal salary, zero hours, negative values, and null inputs. Find and repair a seeded calculation bug with the debugger, then add a regression test.

### Stage 3 - Objects and maintainable Java

**Objective:** Model student data and behavior using small, understandable classes.

**Tasks and estimated hours:**

- **Create and organize classes (3 hours).** Practice fields, constructors, packages, access modifiers, and `this`. Create two instances and observe that instance fields belong to each object, while static members belong to the class. Choose instance fields for each student's individual data.
- **Protect behavior through object design (2-3 hours).** Keep fields private and expose methods that preserve valid state. Create an interface and two implementations, then call them through the interface to demonstrate polymorphism. Compare a small inheritance example with composition and explain when an object should contain another object.
- **Write readable methods and explicit failures (2-3 hours).** Practice throwing and handling exceptions, representing a date with `LocalDate`, and using `BigDecimal` for GPA. Give classes and methods descriptive names and keep each method focused on one operation. Explain why rejecting invalid data is better than silently accepting it.
- **Build StudentProfile and its tests (3 hours).** Implement the fields, constructor validation, and graduation-year increment. Test GPA boundaries and verify that changing one student does not change another. Add tests or runnable examples for both interface implementations.
- **Solve a string exercise (1 hour).** Implement a short task such as reversing a string or counting vowels. State how empty input and letter case are handled, and show examples that verify your decisions.
- **Review and demonstrate M3 (1-2 hours).** Explain the responsibilities of each class and why fields are private. Demonstrate a valid student, a rejected GPA, and the year change; address review comments and rerun the relevant tests.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** `StudentProfile` with first name, last name, expected graduation year, and GPA; create two students and implement a method that increases graduation year by one.

1. Create `StudentProfile` with private fields and a constructor. Provide methods for reading data without exposing unrestricted field changes.
2. Reject GPA values outside 0.0-4.0. Add a method that increases the expected graduation year by exactly one.
3. Create two student objects and show that changing one student's graduation year leaves the other unchanged. Test the year change and valid/invalid GPA boundaries.
4. Create a small interface with two implementations, such as two ways to format a student summary. Call both through the interface and explain the different results.

**Submit:** Classes, interface and implementations, tests, and a runnable example showing both students.

**Milestone M3:** Keep fields private, validate GPA in the 0.0-4.0 range, test the graduation-year change, and demonstrate a small interface with two implementations. Explain why a failure should be rejected rather than silently ignored.

### Stage 4 - Collections, file I/O, and a console mini-project

**Objective:** Manage multiple students and persist a small local dataset without Spring.

**Tasks and estimated hours:**

- **Choose collections deliberately (2-3 hours).** Store and iterate over example students using `List`, `Set`, and `Map`. Explain ordering, duplicate handling, and lookup by key. Practice generics and sorting, then check how `equals` and `hashCode` affect membership and duplicate detection.
- **Practice collection transformations (2 hours).** Write a loop, then a simple lambda or stream that filters or sorts students. Use `Optional` for a lookup that may find nothing and handle that case explicitly. Prefer the version you can explain clearly rather than forcing every operation into a stream.
- **Read and write a documented file format (2 hours).** Use `Files` to save and load sample records. Define field separators, date/number formats, and how unsupported characters or malformed rows are handled. Close resources when necessary and report file paths and useful failure details.
- **Assemble and test the console registry (3-4 hours).** Connect add, list, find, remove, save, and reload operations to a console menu. Preserve unique IDs and reject duplicate emails. Test unknown IDs, bad files, and a save/restart/reload sequence to verify that persistence works.
- **Collaborate through Git and demonstrate M4 (2-3 hours).** Create a branch and pull request with a description and verification results. Practice a small merge conflict, inspect the resolved file, and run checks afterward. Address feedback and demonstrate the registry from a fresh start.
- **Solve a map or duplicate exercise (1 hour).** Count word occurrences with a frequency map or detect repeated values with a set. Explain the chosen collection and test empty input, repeated values, and an input with no duplicates.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** Console student registry: add, list, find, remove, save, and reload students. Use a unique ID and reject duplicate emails.

1. Store students in a collection keyed by a unique ID. Add an email field and reject an email already used by another student.
2. Add console choices to add, list, find by ID, and remove by ID. Show clear messages for unknown IDs and duplicate emails.
3. Choose and document a text file format. Implement save and reload, explain how IDs remain unique after reload, and report malformed rows with useful details.
4. Save several students, close the program, restart it, and reload the file. Test duplicate records, missing records, and malformed input.
5. Open a pull request, practice resolving a small merge conflict, and address review feedback.

**Submit:** Registry source and tests, a sample data file, save/reload instructions, restart evidence, and the pull request.

**Milestone M4:** Data survives an application restart; tests cover duplicate and missing records; malformed file input is reported clearly. Submit a pull request and address review feedback. If this is a mentored course, add **@aliasflurry** as a repository collaborator for review.

### Stage 5 - SQL and relational database foundations

**Objective:** Explain and query the data before adding an ORM.

**Tasks and estimated hours:**

- **Set up and model PostgreSQL data (3 hours).** Create a learning database and sketch student and department tables. Choose column types, primary and foreign keys, required fields, a unique email constraint, and one useful index. Explain which invalid states each constraint prevents.
- **Write reproducible SQL scripts (3-4 hours).** Save schema creation and sample data in separate files. Write labeled examples of CRUD, filtering, ordering, aggregates, and a join, using sample rows that make each result easy to verify. Inspect results rather than only checking that a query executes.
- **Explore transactions and constraints (1-2 hours).** Group changes in a transaction and compare commit with rollback. Attempt a duplicate email and observe uniqueness enforcement. Verify the final stored data after both successful and rejected operations.
- **Connect Java through JDBC (3 hours).** Open a connection using external configuration, bind a lookup value with a prepared statement, and map the result into Java data. Use try-with-resources for cleanup. Explain that JDBC executes SQL directly, while JPA maps objects to relational data.
- **Solve a palindrome or anagram exercise (1 hour).** Define how spaces, case, and empty strings affect the answer before implementing it. Test both matching and nonmatching inputs and explain your comparisons or character counts.
- **Recreate and demonstrate M5 (1-2 hours).** Run the scripts against an empty learning database and demonstrate at least eight queries, rollback, and the Java lookup. Correct undocumented dependencies or script-order problems so another person can repeat the exercise.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** SQL scripts for a student table and sample data, plus a small department table solely for the foreign-key/join exercise. The final API can remain a single student resource.

1. Draw the student and department tables with their columns, primary keys, and foreign key. Explain the purpose of each constraint and index.
2. Write `schema.sql` and `sample-data.sql`. Include a unique student email constraint and enough sample rows to demonstrate joins and grouping.
3. Write `queries.sql` with at least eight labeled examples covering insert, read, update, delete, filtering, ordering, an aggregate, and a join. Add a transaction example that changes data and rolls it back.
4. Write a Java JDBC lookup that accepts a value through a prepared statement and closes resources with try-with-resources. Keep connection credentials outside committed code.
5. Run the scripts against an empty learning database, execute the queries, and verify that rollback restores the original data.

**Submit:** Table diagram, SQL scripts, JDBC lookup, execution instructions, and query/rollback results.

**Milestone M5:** Recreate the database from scripts, run at least eight useful queries including a join and aggregate, demonstrate rollback, and run a Java lookup using a prepared statement. No string concatenation of user input into SQL.

### Stage 6 - HTTP and Spring Boot foundations

**Objective:** Build an in-memory API and explain how a request reaches application code.

**Tasks and estimated hours:**

- **Understand an HTTP exchange (2-3 hours).** Inspect a JSON request and response with an HTTP client. Identify the method, URL, headers, body, and status. Compare path parameters with query parameters, use resource-based names, and explain PUT replacement and idempotency with a repeated-request example.
- **Create and explore Spring Boot (3 hours).** Generate the project and inspect its Maven dependencies, application entry point, and configuration. Explain a bean as an object managed by Spring and dependency injection as supplying the objects a class needs. Use constructor injection to make dependencies explicit.
- **Implement controller and service responsibilities (3-4 hours).** Build create, list, and find-by-ID using in-memory storage. Keep HTTP concerns in the controller and student operations in the service. Use this separation to explain the single-responsibility principle with a concrete change that belongs in only one layer.
- **Verify HTTP and service behavior (2-3 hours).** Add a service unit test and a basic HTTP test. Send requests that produce `201`, `200`, and `404`, checking bodies and the create response's `Location` header. Save repeatable requests for later stages.
- **Solve a two-sum exercise (1 hour).** Find two distinct array positions whose values add to a target. Define the no-match result, try a straightforward approach, and test duplicate values so one position is not reused incorrectly.
- **Trace and demonstrate M6 (1 hour).** Follow one request from JSON conversion through controller and service to the response. Explain where Spring supplies dependencies and show passing tests alongside your HTTP examples.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** Generate the Spring Boot project and implement in-memory `POST /students`, `GET /students`, and `GET /students/{id}` using a controller and service.

1. Generate a Maven Spring Boot project with Spring Web and test support. Record the selected versions and confirm that the application starts.
2. Use the student fields in the final contract below. Create a service that stores students in memory and assigns IDs; inject it into a controller through the constructor.
3. Implement create, list, and find-by-ID. Return `201` with a `Location` header for create, `200` for reads, and `404` for an unknown ID.
4. Save HTTP client examples for each endpoint. Add a service unit test and a basic HTTP test, and trace one request from JSON through the controller to the service.

**Submit:** Running Spring project, passing tests, HTTP examples/results, and startup instructions. In-memory records may disappear on restart at this stage.

**Milestone M6:** Demonstrate `201`, `200`, and `404` responses with an HTTP client. Explain JSON-to-Java conversion and constructor injection. Verify a basic HTTP test and a service unit test.

### Stage 7 - Complete CRUD, DTOs, and validation

**Objective:** Define a predictable API contract and handle bad requests consistently.

**Tasks and estimated hours:**

- **Define DTOs and mapping (2 hours).** Create request types containing editable fields and response types containing returned fields, including the server-generated ID. Map explicitly between these types and the internal model. Explain how this keeps the public API independent of storage details.
- **Validate input and standardize errors (3-4 hours).** Apply required-value checks together with format and range checks from the contract. Create a not-found exception and a central handler for application errors. Return field-specific validation details and verify that malformed JSON produces a useful `400` response.
- **Finish and document CRUD (3-4 hours).** Implement PUT replacement and DELETE with the required status codes. Document all five endpoints with request and response examples, including an empty list and a missing record. Ensure an update cannot silently create a new student.
- **Test the HTTP contract with MockMvc (2-3 hours).** Mock the service to focus on routing, JSON, validation, and error handling. Cover successful CRUD, malformed JSON, invalid fields, and missing records. Check response content as well as status codes.
- **Solve a collections exercise (1 hour).** Choose a task such as grouping names by first letter. Explain the collection choice, test empty and repeated inputs, and describe how processing time and memory grow with input size.
- **Review replacement behavior and demonstrate M7 (1 hour).** Show that PUT requires all editable fields and replaces their prior values. Demonstrate successful CRUD and representative `400`/`404` errors, address feedback, and rerun the affected tests.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** All five required endpoints in the contract below, initially using in-memory storage. Include request/response examples and a consistent error body.

1. Create separate request and response DTOs using the final contract. Map them manually and add required-value, format, and range validation.
2. Implement `PUT /students/{id}` as replacement of every editable field, and `DELETE /students/{id}`. Return `404` when the target does not exist; PUT must not create it.
3. Add a central exception handler that returns `status`, `message`, `path`, and field errors when relevant. Handle invalid input, malformed JSON, and missing records consistently.
4. Write MockMvc tests with a mocked service for the five endpoints, empty lists, validation failures, malformed requests, and missing IDs. Verify PUT replacement behavior.
5. Document a request and expected response for each endpoint, plus representative error responses.

**Submit:** DTOs, mappings, CRUD handlers, exception handler, passing HTTP tests, and API examples. Database duplicate-email handling is completed in Stage 8.

**Milestone M7:** Demonstrate successful create/read/update/delete, an empty list, invalid input returning `400`, and a missing record returning `404`. Tests verify that PUT replaces all editable fields and cannot create a missing student.

### Stage 8 - PostgreSQL, JPA, and data integrity

**Objective:** Replace in-memory storage with a database while preserving API behavior.

**Tasks and estimated hours:**

- **Map and persist students (3-4 hours).** Define the JPA entity, generated ID, column mappings, and repository. Replace in-memory operations with PostgreSQL persistence while keeping DTOs and endpoint behavior stable. Explain how a repository lookup becomes a database query.
- **Manage transactions and configuration (2 hours).** Place transaction boundaries around changes that must succeed or fail together. Inspect generated SQL to understand reads and writes. Supply database settings through environment variables and a development profile without committing credentials.
- **Create a migration and enforce integrity (2-3 hours).** Write a Flyway migration that initializes an empty database with constraints matching the contract. Trim and lowercase email consistently before storage, and enforce uniqueness on that stored value so the database also rejects duplicates.
- **Test database failures and conflict responses (3-4 hours).** Use an isolated PostgreSQL test database for repository behavior. Verify duplicate creates and updates, map conflicts to `409`, and confirm that a rejected update preserves existing data. Explain why an application-side existence check alone does not enforce uniqueness.
- **Solve a maximum-profit exercise (1 hour).** Given prices in order, find the largest profit from buying once and selling later, allowing no trade when profit is unavailable. Track the lowest price seen in one pass and test falling prices, one value, and repeated prices.
- **Verify persistence and demonstrate M8 (1 hour).** Initialize a fresh database from the migration, create a student, restart the API, and fetch the same record. Show repository test results and document the separation between development and test databases.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** Persist the API's student records in PostgreSQL, with a migration that can initialize an empty database.

1. Map the student entity and repository, then replace the in-memory store with repository calls. Keep the existing HTTP contract.
2. Create a Flyway migration for the student table, generated ID, and constraints matching the contract. Normalize email before storage and enforce uniqueness in PostgreSQL.
3. Configure database access through environment variables and a development profile. Use transactions for changes, and map duplicate-email conflicts to `409`.
4. Run repository tests against a dedicated PostgreSQL test database. Verify duplicate create and update failures, including preservation of the original record after a rejected update.
5. Initialize an empty database using the migration. Create a student, restart the application, and fetch the same student again.

**Submit:** Entity/repository code, migration, configuration instructions without credentials, repository tests, and fresh-database/restart evidence.

**Milestone M8:** Restart the API and retrieve an existing student. Initialize a fresh database from the migration. An attempted duplicate create or update returns `409` without changing existing data. Demonstrate a repository test against a dedicated PostgreSQL test database; do not run it against development data.

### Stage 9 - Basic security, logging, and configuration

**Objective:** Protect the learning API and investigate failures without exposing sensitive information.

**Tasks and estimated hours:**

- **Add authentication to student endpoints (3-4 hours).** Explain authentication as proving identity and authorization as deciding permitted actions. Configure HTTP Basic for every student route and verify that missing or incorrect credentials return `401`. Confirm that valid credentials permit both reads and writes.
- **Separate credentials and environments (2 hours).** Configure an encoded password and supply credentials outside source control. Keep development and test settings separate, and explain which configuration values each environment needs. Document setup using placeholders rather than real secrets.
- **Explain HTTPS and CSRF decisions (2-3 hours).** Describe why HTTP Basic needs HTTPS when credentials cross a network. Explain how browsers can attach credentials automatically and why that affects cross-site request forgery (CSRF) protection. Document the chosen configuration and its assumptions about API clients.
- **Add diagnostics and authentication tests (3-4 hours).** Use SLF4J to log useful failure context while excluding passwords and authorization headers. Keep unexpected error responses generic. Test missing, incorrect, and valid credentials for every endpoint, including authenticated create, update, and delete.
- **Practice a small problem with edge cases (1 hour).** Revisit a previous array, string, or map problem with a new input rule. State the changed rule, update the implementation, and add examples that distinguish the old and new behavior.
- **Inspect and demonstrate M9 (1 hour).** Review tracked configuration and sample logs for exposed credentials. Demonstrate authentication failures and successful writes, explain one diagnostic entry, and address review findings.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** Require authentication for every `/students` and `/students/**` endpoint, using credentials supplied outside source control.

1. Configure Spring Security to require HTTP Basic authentication for all five student endpoints. Supply credentials outside source control and use password encoding.
2. Document how to supply local credentials, how HTTPS protects credentials in transit, and the reason for your chosen CSRF configuration.
3. Add useful logs for diagnosing failures. Keep passwords and authorization headers out of logs, and return a generic message for unexpected server errors.
4. Test each endpoint with missing, incorrect, and valid credentials. Verify authenticated create, update, and delete as well as reads, then inspect logs for accidental credential exposure.

**Submit:** Security configuration, credential setup instructions, authentication tests, and one sanitized log example with an explanation.

**Milestone M9:** Automated HTTP tests prove missing/incorrect credentials return `401` and valid credentials can access the endpoints. Authenticated create/update/delete requests also work. Explain the credential setup and one diagnostic log. Roles and `403` behavior are optional unless role restrictions are added.

### Stage 10 - Testing across layers and regression fixes

**Objective:** Prove the assembled application works beyond isolated mocked components.

**Tasks and estimated hours:**

- **Review coverage by behavior (2-3 hours).** Match acceptance scenarios to service, controller, repository, or integration tests. Add missing cases for boundaries and failures, and explain what each test layer proves. Avoid relying on a coverage percentage as evidence of correct behavior.
- **Exercise the full application (3-4 hours).** Build an authenticated HTTP-to-PostgreSQL integration test using real application layers. Create a student, fetch it, update it, delete it, and verify the final missing-record response. Check returned values and stored behavior throughout the workflow.
- **Make tests repeatable and fix a regression (3-4 hours).** Isolate database test data with a repeatable setup and cleanup strategy. Run the required suite twice without manual cleanup. Reproduce a defect, write a failing regression test, fix it, and verify the test passes.
- **Add exact last-name filtering (2 hours).** Implement the optional query parameter on the list endpoint using case-insensitive exact matching. Test matching names, case differences, partial names that must not match, no results, and listing without a filter.
- **Explain algorithm cost (1 hour).** Solve a short exercise or improve a previous solution. State how time and memory grow with input size and compare approaches using a small worked example.
- **Document and demonstrate M10 (1 hour).** Record the defect symptoms, reproduction steps, cause, fix, and regression test. Present two successful suite runs and demonstrate the filter alongside the full authenticated CRUD test.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** A repeatable test suite, the filtering feature, and a short record of a discovered defect and its regression test.

1. Map every scenario in the final acceptance checklist to a test or a manual demonstration. Add missing service and controller tests.
2. Add a full integration test that authenticates and creates, fetches, updates, and deletes a student through real application layers and PostgreSQL.
3. Add `GET /students?lastName=Smith` filtering with case-insensitive exact matching. Test a match, different letter case, a partial name that must not match, and no results.
4. Isolate test data and run the entire required suite twice without manual database cleanup.
5. Record one defect, its reproduction steps, the fix, and a regression test that fails before the fix and passes afterward.

**Submit:** Test suite, filter implementation/examples, two successful run results, and the defect record.

**Milestone M10:** Tests cover the acceptance scenarios below. A full integration test creates, fetches, updates, and deletes a student with authentication enabled. Run the suite twice successfully without manual database cleanup. Do not replace scenario coverage with an arbitrary coverage percentage.

### Stage 11 - Packaging, documentation, and handoff rehearsal

**Objective:** Make the project build and run outside the author's IDE.

**Tasks and estimated hours:**

- **Build and run outside the IDE (2 hours).** Verify the Maven Wrapper and document `test`, `package`, and `verify` commands for Windows and Unix. Package the executable JAR, start it from a terminal with the required configuration, and call an endpoint to confirm it works.
- **Run the required suite in CI (3-4 hours).** Configure GitHub Actions to build the project and run all required test layers with a disposable PostgreSQL service. Supply test configuration without real credentials and make test failures fail the workflow. Inspect results to confirm database tests actually executed.
- **Write setup instructions in execution order (3-4 hours).** Document exact prerequisites, database creation, environment variables, migration behavior, tests, packaging, startup, and authenticated requests. Include expected success signals and explain how to stop the application. Make every command usable without relying on IDE settings.
- **Prepare API examples and an architecture diagram (2 hours).** Save requests with placeholder credentials and sample JSON for the required workflows. Draw the controller, service, repository, and database path, and label each responsibility so a reviewer can connect the diagram to the code.
- **Rehearse the handoff and demonstrate M11 (2-3 hours).** Clone into a separate directory and follow only the application README. Correct missing prerequisites, commands, or configuration and investigate CI failures. Record a successful build, test run, JAR startup, and authenticated API call.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

**Deliverable:** Runnable JAR, working CI configuration, API examples, and setup instructions.

1. Include Maven Wrapper files and document Windows and Unix commands for testing, packaging, and running the executable JAR outside the IDE.
2. Configure GitHub Actions to run unit, controller, repository, and full integration tests with a disposable PostgreSQL service.
3. Write the application README in execution order: prerequisites and exact versions, clone, database creation, environment variables, migration, tests, packaging, startup, and authenticated API calls. Use placeholders for secrets.
4. Add reproducible HTTP examples and a diagram showing controller, service, repository, and database responsibilities.
5. Clone into a separate directory and follow only those instructions. Fix every missing step and verify that CI also passes.

**Submit:** Executable JAR, wrapper files, CI workflow and successful run link, application README, HTTP examples, diagram, and fresh-clone results.

**Milestone M11:** From a fresh clone in a separate directory, follow only the README to build, test, start, and call the API. Fix missing instructions. Include the Windows `mvnw.cmd` and Unix `./mvnw` command forms. CI must run database tests as well as unit tests.

### Stage 12 - Review, corrections, and final demonstration

**Objective:** Finish the agreed scope and explain the implementation independently.

**Tasks and estimated hours:**

- **Audit requirements and gather evidence (4 hours).** Work through the complete acceptance checklist. Link each item to code, tests, CI results, or a recorded demonstration, and identify any unmet requirement. Ask another person to try the documented setup when possible.
- **Resolve review findings (5-8 hours).** Reproduce each reported issue, make a focused correction, and run the checks that verify it. Add a regression test for a behavior defect where appropriate. Finish with the required suite and update the evidence after corrections.
- **Finalize the submission (1 hour).** Update the pull request and application README to describe the finished behavior and verified setup. List known limitations with their practical effects and ensure required acceptance items are complete before sign-off.
- **Deliver the demo and demonstrate M12 (2 hours).** Prepare and present a 10-15 minute walkthrough covering startup, successful CRUD, a failure, the request path, one SQL query, and one test. Make a small requested change independently, explain the affected code, and run the relevant checks.

**Stage total:** 12-15 hours. Record actual time for each task in your milestone notes.

Keep this stage for review and completion; add no new major feature.

**Deliverable:** Final pull request, completed acceptance checklist, known limitations, and a 10-15 minute demo.

1. Copy the final acceptance checklist into your submission notes. For each item, link the relevant file, test result, CI run, or recorded demonstration; mark it complete only after verification.
2. Resolve review findings and rerun the affected checks. Record remaining limitations with their practical effect; required acceptance items must be completed before sign-off.
3. Finalize the pull request with a description of the finished application, setup instructions, validation results, and known limitations.
4. Prepare a 10-15 minute demo: show startup and a successful CRUD workflow, demonstrate a failure, trace a request through the layers, and explain one SQL query and one test.
5. Have another person follow the setup instructions when possible. During review, make one small requested change independently and run the relevant checks.

**Submit:** Final pull request, evidence-linked checklist, limitations, and a demo recording or live walkthrough. Use M12 below for final sign-off.

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
