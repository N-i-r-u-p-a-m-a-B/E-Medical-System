## E-Medical System (Spring Boot, Security, JPA, Thymeleaf)

A hospital/e‑medical management web app built with Spring Boot. It includes authentication/authorization, appointment management, and role‑based dashboards rendered with Thymeleaf.

### Features
- Role‑based authentication (Admin, Doctor, User) with Spring Security (JDBC)
- User registration and email confirmation scaffold
- Appointments (sample data provided)
- Admin/Doctor/User pages with Thymeleaf templates
- MySQL persistence via Spring Data JPA (Hibernate)

### Tech Stack
- Backend: Spring Boot, Spring Security, Spring Data JPA (Hibernate)
- View layer: Thymeleaf (LEGACYHTML5 via NekoHTML)
- Database: MySQL (Connector/J 5.1.49)
- Build/Runtime: Java 8, Maven, Embedded Tomcat
- Frontend assets: Bootstrap, jQuery, Chart.js, DataTables, Font Awesome, Select2, Slick, Lightbox2, AOS/animate.css, SweetAlert, etc.

### Prerequisites
- Java 8 (JDK 1.8)
- Maven (or use the included Maven Wrapper)
- MySQL 5.7/8.x

### Setup
1) Database
- Create a database/schema named `userauth`.
- Option A: Import the seed SQL at project root: `Biomedical.sql` (creates `user`, `app` and seeds data).
- Option B: Start with an empty schema and let JPA create tables (uncomment `spring.jpa.hibernate.ddl-auto` in `application.properties`).

2) Configure application properties
- File: `bioMedical/src/main/resources/application.properties`
- Update MySQL credentials:
  - `spring.datasource.url=jdbc:mysql://localhost:3306/userauth`
  - `spring.datasource.username=YOUR_USERNAME`
  - `spring.datasource.password=YOUR_PASSWORD`
- Optional: Configure SMTP if using email.

3) Run the application
- Windows (PowerShell/CMD):
  - `cd E-Medical-System-Web-Project-Using-Spring-Boot-Security-JPA-Rest-Thymeleaf-HQL/bioMedical`
  - `mvnw.cmd spring-boot:run`
- macOS/Linux:
  - `cd E-Medical-System-Web-Project-Using-Spring-Boot-Security-JPA-Rest-Thymeleaf-HQL/bioMedical`
  - `./mvnw spring-boot:run`
- App URL: `http://localhost:8080`
- Login page: `/showMyLoginPage`
- Seeded users are in `Biomedical.sql` (`user` table rows).

### Build a WAR
- From `bioMedical` module:
  - Windows: `mvnw.cmd clean package`
  - macOS/Linux: `./mvnw clean package`
- Output: `bioMedical/target/bioMedical-0.0.1-SNAPSHOT.war`

### Project Structure
- Module: `bioMedical/`
  - `src/main/java/com/spring/bioMedical/` – Spring Boot app, controllers, config, services, entities
  - `src/main/resources/templates/` – Thymeleaf views (admin, doctor, user, login, register)
  - `src/main/resources/static/` – CSS/JS/fonts/images and vendor assets
  - `src/main/resources/application.properties` – App configuration
- Seed SQL: `Biomedical.sql` (project root)

### Notes
- Thymeleaf uses LEGACYHTML5; NekoHTML is declared in `pom.xml`.
- Security uses a simple password encoder for demo data. Replace with BCrypt in production and store hashed passwords.


