# CompanyData – Employee Management System

A backend-focused Employee Management System built using **Java, Spring Boot, Spring Data JPA, Hibernate, and MySQL**.

The project provides REST APIs for managing employee records and demonstrates layered backend architecture, DTO-based request/response handling, validation, CRUD operations, partial updates, and database integration.

## 🚀 Technologies Used

* Java 21
* Spring Boot
* Spring Data JPA
* Hibernate
* REST APIs
* MySQL
* ModelMapper
* Jakarta Bean Validation
* Maven
* Lombok
* Postman

## 🏗️ Project Architecture

The application follows a layered architecture:

```text
Controller
    ↓
Service
    ↓
Repository
    ↓
MySQL Database
```

### Layers

**Controller**

* Handles HTTP requests and responses
* Defines REST API endpoints
* Performs request validation

**Service**

* Contains business logic
* Handles employee operations
* Converts entities to DTOs

**Repository**

* Uses Spring Data JPA
* Performs database operations

**Entity**

* Represents the Employee database table

**DTO**

* Separates API request/response data from the database entity

## ✨ Features

* Create employee
* Get all employees
* Get employee by ID
* Get employee by name
* Update employee
* Partially update employee using PATCH
* Delete employee
* Request validation using Jakarta Bean Validation
* DTO-based request and response handling
* ModelMapper integration
* MySQL database integration
* REST API testing using Postman

## 📂 Project Structure

```text
src/main/java/com/example/CompanyData

├── Controller
│   └── EmployeeController.java
│
├── DTO
│   ├── AddEmployeeDTO.java
│   └── EmployeeDTO.java
│
├── Employee
│   └── Employee.java
│
├── ModelMapper
│   └── MapperConfig.java
│
├── Repository
│   └── EmployeeRepository.java
│
└── Service
    ├── EmployeeService.java
    └── ServiceImple
        └── EmployeeServiceImple.java
```

## 🔗 REST API Endpoints

| Method | Endpoint                  | Description                  |
| ------ | ------------------------- | ---------------------------- |
| GET    | `/employees`              | Get all employees            |
| GET    | `/employees/ids/{id}`     | Get employee by ID           |
| GET    | `/employees/names/{name}` | Get employee by name         |
| POST   | `/employees`              | Create a new employee        |
| PUT    | `/employees/{id}`         | Update an employee           |
| PATCH  | `/employees/{id}`         | Partially update an employee |
| DELETE | `/employees/{id}`         | Delete an employee           |

## 📝 Example Request

### Create Employee

**POST**

```text
/employees
```

Request body:

```json
{
  "name": "Ajinkya",
  "department": "IT",
  "salary": 45000,
  "email": "ajinkya@example.com"
}
```

### Example Response

```json
{
  "id": 1,
  "name": "Ajinkya",
  "department": "IT",
  "salary": 45000
}
```

## 🔍 Validation

Employee creation and update requests use Jakarta Bean Validation.

Examples:

* Employee name cannot be blank
* Department cannot be blank
* Salary must be at least 10,000
* Email must have a valid email format

Example:

```java
@NotBlank(message = "Name cannot be empty")
private String name;

@Min(value = 10000)
private int salary;

@Email
@NotBlank(message = "email cannot be blank")
private String email;
```

## 🗄️ Database Configuration

The application uses MySQL.

Create the database before running the application:

```sql
CREATE DATABASE company;
```

Configure your local database credentials using environment variables:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/company?useSSL=false&serverTimezone=UTC
spring.datasource.username=${DB_USERNAME}
spring.datasource.password=${DB_PASSWORD}
```

Do not commit real database credentials to GitHub.

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/CompanyData-Employee-Management.git
```

### 2. Open the project

Open the project in IntelliJ IDEA or another Java IDE.

### 3. Configure MySQL

Create the database:

```sql
CREATE DATABASE company;
```

Set your local database username and password.

### 4. Run the application

Run the Spring Boot application.

The application runs on:

```text
http://localhost:8080
```

### 5. Test the APIs

Use Postman or another REST API client to test the endpoints.

## 🧪 API Testing

The REST APIs were tested using **Postman** for:

* GET requests
* POST requests
* PUT requests
* PATCH requests
* DELETE requests
* Request validation
* Database operations

## 🎯 Learning Outcomes

Through this project, I practiced:

* Building REST APIs using Spring Boot
* Layered backend architecture
* Spring Data JPA and Hibernate
* Entity and DTO design
* CRUD operations
* Request validation
* ModelMapper
* MySQL database integration
* HTTP methods and status codes
* API testing using Postman
* Maven-based project management
