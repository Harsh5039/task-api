# Task Management API

This is a simple Task Management API built with Spring Boot. It supports basic CRUD operations for managing tasks and users and includes JWT authentication and pagination.

## Technologies Used

- Java
- Spring Boot
- Spring Data JPA
- Spring Security
- H2 Database (for development and testing)
- Maven

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Harsh5039/task-api.git
   ```
2. Build the project with Maven:
   ```bash
   mvn clean install
   ```
3. Run the application:
   ```bash
   mvn spring-boot:run
   ```
   The application will start on [http://localhost:8080](http://localhost:8080).

## API Testing Using Postman

### 1. Register a User

- **Method:** POST
- **URL:** `http://localhost:8080/users/register`
- **Headers:** 
  - `Content-Type: application/json`
- **Body:** JSON
  ```json
  {
    "username": "user1",
    "password": "password",
    "role": "USER"
  }
  ```

### 2. Get User by Username

- **Method:** GET
- **URL:** `http://localhost:8080/users/{username}`
  - Replace `{username}` with the actual username. Example: `http://localhost:8080/users/user1`
- **Authorization:** 
  - **Type:** Basic Auth
  - **Username:** user1
  - **Password:** password

### 3. Create a Task

- **Method:** POST
- **URL:** `http://localhost:8080/tasks`
- **Headers:**
  - `Content-Type: application/json`
- **Authorization:** 
  - **Type:** Basic Auth
  - **Username:** user1
  - **Password:** password
- **Body:** JSON
  ```json
  {
    "title": "Complete Internship Assignment",
    "description": "Solve the given problem and submit the code",
    "status": "PENDING"
  }
  ```

### 4. Get All Tasks

- **Method:** GET
- **URL:** `http://localhost:8080/tasks`
- **Authorization:** 
  - **Type:** Basic Auth
  - **Username:** user1
  - **Password:** password

### 5. Update a Task

- **Method:** PUT
- **URL:** `http://localhost:8080/tasks/{id}`
  - Replace `{id}` with the ID of the task you want to update. Example: `http://localhost:8080/tasks/1`
- **Headers:**
  - `Content-Type: application/json`
- **Authorization:** 
  - **Type:** Basic Auth
  - **Username:** user1
  - **Password:** password
- **Body:** JSON
  ```json
  {
    "status": "COMPLETED"
  }
  ```

### 6. Delete a Task

- **Method:** DELETE
- **URL:** `http://localhost:8080/tasks/{id}`
  - Replace `{id}` with the ID of the task you want to delete. Example: `http://localhost:8080/tasks/1`
- **Authorization:** 
  - **Type:** Basic Auth
  - **Username:** user1
  - **Password:** password

---

For additional information and to explore the API further, you can use Postman to test each endpoint as described above.
