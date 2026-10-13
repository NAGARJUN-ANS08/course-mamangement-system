Course Registration Service
Project Overview

This project manages student course registrations using Java and Maven. It includes registration validation and JUnit 5 automated tests.

Project Structure
pom.xml — Parent POM containing shared properties, dependency management, plugin management, and the child module declaration.
course-registration-app/pom.xml — Child POM inheriting from the parent.
course-registration-app/src/main/java/ — Application source code.
course-registration-app/src/test/java/ — JUnit 5 test classes.
course-registration-app/target/ — Generated build output; not committed to Git.
Prerequisites
A compatible JDK (Java 17 for the supplied POM configuration).
Apache Maven.
Git.

Verify the installed tools:

java -version
mvn -version

Build and Test

Run these commands from the repository root.

Run the clean test lifecycle:

mvn clean test


Package the application:

mvn package


Inspect the effective child POM:

mvn -f course-registration-app/pom.xml help:effective-pom


The root POM uses Maven's reactor to build the parent and the course-registration-app module.

Test Reports

JUnit/Surefire XML reports are generated under:

course-registration-app/target/surefire-reports/

Text reports are generated in the same directory.

Use the actual Maven output and Surefire reports to record the number of tests, failures, errors, and skipped tests.

Generated Files

Do not commit target/ directories or generated build output.