# Hi, This is Priya Kushwaha! 👋

Welcome to my repository! 🎉

I'm **Priya Kushwaha**, a software developer interested in building full-stack applications using **Java, Spring Boot, Spring Security, Spring Data JPA, Microservices, Spring Cloud, React.js, and MySQL**.

Thank you for visiting my repository! Feel free to explore the project.

# 🎨 ReactJS + Spring Boot Full-Stack Application

A service-oriented platform that connects consumers with small businesses in the **Arts, Entertainment, and Recreation** sector. Users can discover and save hobbies, while businesses can manage their offers.


## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Applications](#-applications)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Prerequisites](#-prerequisites)
- [Getting Started](#-getting-started)
- [Frontend Setup](#-frontend-setup)
- [Backend Setup](#-backend-setup)
- [API Documentation](#-api-documentation)
- [Email Configuration](#-email-configuration)
- [Troubleshooting](#-troubleshooting)
- [Author](#-author)

## 📖 Project Overview

This project consists of two applications:

1. **Spring Boot Backend (`spring-backend`)** — A REST API that manages hobbies and provides secured endpoints using JSON Web Token (JWT) authentication.
2. **React.js Frontend (`react-frontend`)** — A web application where consumers can discover and save hobbies, and businesses can manage their offers.

The backend stores application data in a MySQL database. The frontend communicates with the backend through REST API requests.

## 🧩 Applications

### 1. Spring Boot Backend

The backend is a Java-based REST API responsible for managing hobbies and handling authenticated requests.

**Key details:**
- Built with Spring Boot and Java.
- Exposes REST API endpoints.
- Uses MySQL for data storage.
- Implements JWT-based authentication.
- Provides API documentation through Swagger UI and OpenAPI.
- Supports email notifications when valid mail credentials are configured.

### 2. React.js Frontend

The frontend provides the user interface for consumers and businesses.

**Key details:**
- Built with React.js.
- Uses Semantic UI React for UI components and styling.
- Allows users to discover and save hobbies.
- Allows businesses to manage their offers.
- Sends JWT access tokens with requests to secured backend endpoints.
- Requires users or businesses to log in to access authenticated functionality.

## ✨ Features

- 🔐 User and business authentication
- 🪪 JWT-based authorization
- 🎨 Discover and save hobbies
- 🏢 Business offer management
- 🔗 REST API integration
- 🗄️ MySQL database integration
- 📚 Swagger API documentation
- 📧 Email notifications with configured SMTP credentials

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Java 11+ | Backend programming |
| Spring Boot | Backend framework |
| Spring REST API | Client-server communication |
| JWT | Authentication and authorization |
| MySQL | Database |
| React.js | Frontend development |
| Semantic UI React | UI components and styling |
| Node.js and npm | Frontend runtime and package management |
| Docker and Docker Compose | Backend containerization and startup |
| Swagger / OpenAPI | API documentation |

## 📋 Prerequisites

Before running the project, install the following tools:

- Java Development Kit (JDK) 11 or a compatible version required by the project
- Node.js and npm
- Docker
- Docker Compose
- MySQL, if the database is not configured to run through Docker

**Recommended versions:** The original setup instructions specify Node.js 16.13.1, npm 8.3.0, JDK 11.0.11, Docker 20.10.7, and Docker Compose 1.8.0. These are the project's documented versions; compatibility with newer versions should be verified.

## 🚀 Getting Started

### Step 1: Clone the Repository

Open a terminal and run:


### Step 2: Navigate to the Project Directory

```bash
cd ReactJS-Spring-Boot-Full-Stack-App
```

The project contains two main directories:

```text
ReactJS-Spring-Boot-Full-Stack-App/
├── react-frontend/
└── spring-backend/
```

## 💻 Frontend Setup

### Step 1: Navigate to the Frontend

From the root project directory, run:

```bash
cd react-frontend
```

### Step 2: Install Dependencies

```bash
npm install
```

### Step 3: Start the Frontend

```bash
npm start
```

The frontend should be available at:

**http://localhost:4200**

The repository's start script uses port `4200`. If you encounter a startup error, check the `start` script in `react-frontend/package.json` and verify that your installed Node.js version is compatible.

## ⚙️ Backend Setup

### Step 1: Navigate to the Backend

Open a new terminal from the project root and run:

```bash
cd spring-backend
```

### Step 2: Configure the Application

Before starting the backend, review the `application.properties` file and configure the required database credentials and other application settings.

If the project uses environment variables or a Docker Compose configuration for its database, ensure those settings match your local environment.

### Step 3: Start the Backend

Make sure Docker is installed and running, then execute:

```bash
docker-compose up --build
```

This command builds the required images and starts the services defined in the Docker Compose configuration.

The backend API should be available at:

**http://localhost:8080**

To stop the containers, press `Ctrl + C`. You can also run the following command from the directory containing the Compose file:

```bash
docker-compose down
```

## 📚 API Documentation

Once the backend is running, explore the API using Swagger UI:

🔗 **Swagger UI:** [http://localhost:8080/swagger-ui/index.html](http://localhost:8080/swagger-ui/index.html)

🔗 **OpenAPI JSON:** [http://localhost:8080/v3/api-docs](http://localhost:8080/v3/api-docs)

### Authentication and API Testing

Use Swagger UI to test the API endpoints.

**1. Register a user**

- `/signup` — Register a client user.
- `/register` — Register a business user.

**2. Authenticate**

Send a request to:

```text
/authenticate
```

Provide the credentials expected by the endpoint. The response should contain a JWT authentication token if authentication succeeds.

**3. Authorize requests**

1. Copy the JWT token from the authentication response.
2. Open Swagger UI.
3. Click the **Authorize** button or the lock icon.
4. Enter the token in the format expected by the API's security configuration.
5. Execute the secured endpoints.

**Important:** The exact request bodies and authorization format depend on the backend implementation. Check the Swagger documentation and security configuration if a request fails.

## 📧 Email Configuration

The backend supports email notifications, including confirmation emails when user entries are updated.

To enable email functionality, configure valid credentials in the backend's `application.properties` file.

For example:

```properties
spring.mail.username=${MAIL_USERNAME}
spring.mail.password=${MAIL_PASSWORD}
```

Configure the appropriate SMTP host, port, and authentication settings for your email provider as required by the application.

Set the corresponding environment variables before starting the backend.

**Security note:** Never commit real email passwords, database credentials, JWT secrets, or other sensitive configuration values to GitHub.

If mail credentials are not configured, the `/notification` endpoint may return an internal server error, and email-related operations may fail with an authentication exception. Other application features should continue to work if they do not depend on email functionality.

## 🐛 Troubleshooting

| Problem | What to check |
|---|---|
| Frontend fails to start | Verify Node.js and npm versions, install dependencies, and check `package.json`. |
| Port 4200 is already in use | Stop the other process using the port or configure a different port. |
| Backend fails to start | Check Docker status, Compose configuration, application logs, and required environment variables. |
| Database connection fails | Verify MySQL availability, database credentials, hostname, port, and database configuration. |
| API returns `401 Unauthorized` | Check the JWT token and authentication requirements. |
| API returns `403 Forbidden` | Check user permissions and Spring Security configuration. |
| Email notification fails | Verify SMTP configuration and email credentials. |

## 👩‍💻 Author

**Priya Kushwaha**

Welcome to my GitHub profile and repository! I enjoy learning new technologies and building practical applications that solve real-world problems.

- **GitHub:** [Visit my GitHub profile](https://github.com/)
- **Project Repository:** [ReactJS-Spring-Boot-Full-Stack-App]


If you find this project interesting, feel free to explore the code and learn more about full-stack application development.

---

⭐ **Thank you for visiting my repository!**

*Happy Coding!* 💻
