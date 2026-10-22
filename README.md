# User Management CRUD System

![Java](https://img.shields.io/badge/Java-17-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-REST_API-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-Frontend-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-Interface-E34F26?style=for-the-badge&logo=html5&logoColor=white)

**User Management CRUD System** is a simple web application for managing user records. It uses **Spring Boot** to provide a REST API, **PostgreSQL** to store data, and a lightweight HTML/CSS/JavaScript interface to create, view, update, and delete users.

---

## 📖 Overview

This project demonstrates the four basic CRUD operations:

- **Create** – add a user with a name and email address.
- **Read** – display all saved users in a table.
- **Update** – edit an existing user's details.
- **Delete** – remove a user after confirmation.

It is a small learning project for practising Java, REST APIs, database integration, and frontend-to-backend communication.

## 🛠 Technologies Used

- **Java 17** – application programming language
- **Spring Boot** – backend application and REST API
- **Spring Data JPA / Hibernate** – database access and ORM
- **PostgreSQL** – relational database
- **HTML, CSS, JavaScript** – user interface
- **Maven** – dependency management and build tool

## ✨ Key Features

- ➕ Add a user with a name and email
- 📋 View all users in a table
- ✏️ Edit existing user details
- 🗑️ Delete users with a confirmation prompt
- 🔄 Store user records in PostgreSQL
- 🌐 REST API endpoints for CRUD operations
- 📱 Simple, responsive-style interface

## 🧱 Project Structure

```text
CRUD-System/
└── demo 2/
    ├── pom.xml
    ├── mvnw
    └── src/
        └── main/
            ├── java/com/example/demo/
            │   ├── DemoApplication.java
            │   ├── User.java
            │   ├── UserController.java
            │   └── UserRepository.java
            └── resources/
                ├── application.properties
                └── static/index.html
```

## 🚀 Getting Started

### Prerequisites

Install the following before running the application:

- **Java JDK 17**
- **PostgreSQL**
- A terminal or IDE such as IntelliJ IDEA
- Git (optional, for cloning the repository)

### Step 1: Create the PostgreSQL Database

Start PostgreSQL and create a database named `my_crud_db`:

```sql
CREATE DATABASE my_crud_db;
```

Make sure you have a PostgreSQL user with permission to access this database.

### Step 2: Configure the Database Connection

Open:

```text
demo 2/src/main/resources/application.properties
```

Set the database URL, username, and password to match your local PostgreSQL setup:

```properties
server.port=8081

spring.datasource.url=jdbc:postgresql://localhost:5432/my_crud_db
spring.datasource.username=YOUR_POSTGRES_USERNAME
spring.datasource.password=YOUR_POSTGRES_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
```

Replace the placeholder username and password with your own local database credentials. **Do not commit real passwords or other secrets to GitHub.** For a shared or production deployment, use environment variables or a secret manager instead.

### Step 3: Run the Spring Boot Application

Open a terminal in the project folder, then enter the application directory:

```bash
cd "demo 2"
```

On macOS/Linux, run:

```bash
chmod +x mvnw
./mvnw spring-boot:run
```

On Windows, run:

```bat
mvnw.cmd spring-boot:run
```

The application uses port `8081` by default.

### Step 4: Open the Web Interface

When the application has started, open this address in your browser:

**http://localhost:8081**

The HTML interface is served by Spring Boot from `src/main/resources/static/index.html`. Use the form to add users, and the table's **Edit** and **Delete** actions to manage existing records.

## 🔌 REST API Endpoints

The API base URL is `http://localhost:8081/users`.

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/users` | Create a user |
| `GET` | `/users` | Retrieve all users |
| `PUT` | `/users/{id}` | Update a user by ID |
| `DELETE` | `/users/{id}` | Delete a user by ID |

### Example: Create a User

Send a `POST` request to `http://localhost:8081/users` with JSON:

```json
{
  "name": "Alex Perera",
  "email": "alex@example.com"
}
```

## 🗄️ Data Model

Each user record contains:

| Field | Type | Description |
|---|---|---|
| `id` | Long | Automatically generated primary key |
| `name` | String | User's name |
| `email` | String | User's email address |

The `User` entity maps to the PostgreSQL table named `users`. Hibernate is configured to update the schema automatically during development.

## 📝 Notes

- This project does **not** require a separate React or Node.js frontend; the interface is plain HTML, CSS, and JavaScript served by Spring Boot.
- There are no default test accounts because this application does not include a login system.
- Keep database credentials private and configure them for your own environment.
- `spring.jpa.hibernate.ddl-auto=update` is convenient for development; review database migration and schema-management practices before production use.

## 👨‍💻 Learning Outcomes

By working with this project, you can practise:

- Building REST endpoints with Spring Boot
- Implementing CRUD operations with Spring Data JPA
- Connecting a Java application to PostgreSQL
- Using JavaScript `fetch()` to call a backend API
- Displaying and editing database records through a web interface

---

If you find this project useful for learning, feel free to ⭐ the repository.
