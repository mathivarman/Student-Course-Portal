# Student Course Portal — Multi-service Project

This repository contains five Spring Boot services:
- course-service
- enrollment-service
- notification-service
- result-service
- student-service

Each service includes a HELP.md with service-specific configuration and defaults:
- course-service/HELP.md
- enrollment-service/HELP.md
- notification-service/HELP.md
- result-service/HELP.md
- student-service/HELP.md

Prerequisites
- JDK (version required is in each service pom.xml)
- Git
- Windows: use included Maven wrapper `mvnw.cmd` (Unix: `./mvnw`)

Build (per service)
- From repo root (Windows):
  ```
  .\<service>\mvnw.cmd -f .\<service>\pom.xml clean package -DskipTests
  ```
- Example:
  ```
  .\course-service\mvnw.cmd -f .\course-service\pom.xml clean package -DskipTests
  ```

Run (per service)
- From service folder using Maven wrapper (recommended for development):
  ```
  cd <service>
  .\mvnw.cmd spring-boot:run
  ```
- Or run the packaged JAR:
  ```
  java -jar <service>\target\<artifact>.jar
  ```

Recommended workflow to run all services locally
1. Open one terminal per service.
2. Build each service once (optional if running via `spring-boot:run`).
3. Start each service with `.\mvnw.cmd spring-boot:run` in its folder.
4. Check each service's HELP.md for default ports and env vars; adjust application.properties or environment variables if ports conflict.

Common troubleshooting
- Port in use: change server.port in application.properties or set environment variable (see HELP.md).
- Missing Java version: install JDK matching the pom.xml.
- Build failures: run the build command and inspect the terminal output; check each service's pom.xml for plugin/config requirements.

Useful commands (Windows PowerShell / CMD)
- Build one service:
  ```
  .\student-service\mvnw.cmd -f .\student-service\pom.xml clean package -DskipTests
  ```
- Run one service:
  ```
  cd student-service
  .\mvnw.cmd spring-boot:run
  ```
- Run packaged jar:
  ```
  java -jar student-service\target\*.jar
  ```

Notes
- See each service HELP.md for environment variables, database settings, or mock data.
- Run services concurrently to test interactions (notifications, enrollment, results).