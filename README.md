# Library Management System

A web-based Library Management System built using **Spring Boot Microservices, MongoDB, and Docker**. The system provides functionality for managing library users, books, borrowing and returning operations, and notifications through independently developed microservices.

## Project Overview

The project follows a microservices architecture, with an API Gateway handling requests between the frontend and backend services. Each major service uses a separate MongoDB database for data storage.

The application is containerized using Docker and Docker Compose for simplified deployment and service management.

## Features

- User registration and login
- User management and authentication
- Book creation, viewing, updating, and deletion
- Book availability and quantity management
- Book borrowing and returning
- Borrowing record management
- Notification creation and retrieval
- API Gateway routing
- REST API documentation with Swagger / OpenAPI
- Containerized deployment using Docker Compose

## System Architecture

The system consists of five main backend services and a web frontend.

```text
                  Web Frontend
               (HTML, CSS, JavaScript)
                         |
                         v
                    API Gateway
                    Port 8085
                         |
          +--------------+--------------+
          |              |              |
          v              v              v
     User Service   Book Service   Borrow Service
      Port 8081      Port 8080       Port 8083
          |              |              |
          v              v              v
       MongoDB        MongoDB        MongoDB

                         |
                         v
                Notification Service
                     Port 8084
                         |
                         v
                      MongoDB
```

## Microservices

| Service | Responsibility | Port |
|---|---|---:|
| API Gateway | Request routing | 8085 |
| User Service | User management and authentication | 8081 |
| Book Service | Book and availability management | 8080 |
| Borrow Service | Borrowing, returning, and records | 8083 |
| Notification Service | Notification management | 8084 |

## Technologies Used

- **Backend:** Java, Spring Boot, Spring Cloud Gateway
- **Database:** MongoDB, Spring Data MongoDB
- **Frontend:** HTML, CSS, JavaScript
- **Containerization:** Docker, Docker Compose
- **API Documentation:** Swagger UI, OpenAPI
- **API Testing:** Postman
- **Build Tool:** Maven
- **Development Tools:** Visual Studio Code, Git, GitHub

## Getting Started

### Prerequisites

Make sure the following tools are installed:

- Java Development Kit (JDK)
- Maven
- Docker Desktop
- Git
- Visual Studio Code (optional)

### Installation and Setup

**1. Clone the repository**

```bash
git clone https://github.com/dilkiishari/LibraryManagementSystem.git
```

**2. Navigate to the project directory**

```bash
cd LibraryManagementSystem
```

**3. Start Docker Desktop**

Ensure Docker Desktop is running.

**4. Start all services**

Run the following command from the project root directory:

```bash
docker compose up -d
```

**5. Verify the running containers**

```bash
docker compose ps
```

### Stopping the Application

Stop the containers using:

```bash
docker compose down
```

## API Documentation

Swagger UI is available for each backend service.

| Service | Swagger UI |
|---|---|
| User Service | [Open Swagger UI](http://localhost:8081/swagger-ui/index.html) |
| Book Service | [Open Swagger UI](http://localhost:8080/swagger-ui/index.html) |
| Borrow Service | [Open Swagger UI](http://localhost:8083/swagger-ui/index.html) |
| Notification Service | [Open Swagger UI](http://localhost:8084/swagger-ui/index.html) |

The API Gateway health endpoint is available at:

`http://localhost:8085/actuator/health`

## Frontend

The frontend is developed using HTML, CSS, and JavaScript.

- **Development URL:** `http://localhost:5500`
- **API Gateway:** `http://localhost:8085`

The frontend communicates with backend services through the API Gateway.

## Project Structure

```text
LibraryManagementSystem/
├── api-gateway/
├── user-service/
├── book-service/
├── borrow-service/
├── notification-service/
├── frontend/
│   ├── index.html
│   ├── style.css
│   └── app.js
├── docker-compose.yml
├── pom.xml
└── README.md
```

Each microservice contains its own source code, Dockerfile, and Maven configuration.

## Future Improvements

- OAuth 2.0 authentication and authorization
- API rate limiting
- Automated testing
- Centralized logging and monitoring
- Cloud deployment
- Enhanced notification functionality

## License

This project was developed for educational purposes.
