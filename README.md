# 🌱 Spring Boot JWT Authentication API

A complete Spring Boot application with JWT authentication, role-based authorization, and token refresh functionality.

## ✨ Features

- ✅ User registration and login with JWT
- 🔑 Role-based authorization (USER & ADMIN)
- ♻️ Token refresh mechanism
- 🐘 PostgreSQL or 🐱‍💻 H2 database support
- 🐳 Docker-ready configuration
- 📊 Pre-loaded sample data for easy testing
- 🔒 Secure password hashing with BCrypt

## 🛠️ Technologies

- Java 17
- Spring Boot 3.1
- Spring Security
- JWT (JSON Web Tokens)
- PostgreSQL / H2 Database
- Lombok
- Docker

## 📊 Pre-loaded Sample Data

The application comes with two pre-configured users:

| Username | Password | Role  |
|----------|----------|-------|
| admin    | admin123 | ADMIN |
| user     | user123  | USER  |

## 🚀 Getting Started

### 📌 Prerequisites

- Java 17 JDK
- Maven 3.8+
- Docker (optional)
- PostgreSQL (optional if using H2)

### 🔧 Running Locally

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/spring-jwt-auth-pro.git
   cd spring-jwt-auth-pro

Choose your database:

🐱‍💻 H2 (in-memory, default): No additional setup needed.

🐘 PostgreSQL: Update application.yml:

yaml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/jwt_auth
    username: postgres
    password: postgres
Build and Run:

bash
./mvnw spring-boot:run
🐳 Running with Docker
Build and start containers:

bash
docker-compose up --build
Application available at: 👉 http://localhost:8080

🖥️ Accessing H2 Console (if using H2)
Visit: http://localhost:8080/h2-console

Use these credentials:

JDBC URL: jdbc:h2:mem:testdb

Username: sa

Password: (leave empty)

📚 API Endpoints
Method	Endpoint	Description	Access
POST	/api/auth/register	Register new user	Public
POST	/api/auth/login	Login and get JWT tokens	Public
POST	/api/auth/refresh	Refresh access token	Public
GET	/api/user	Test user endpoint	USER or ADMIN
GET	/api/admin	Test admin endpoint	ADMIN only
📦 Request Examples
📌 Register
POST /api/auth/register

json
{
  "username": "newuser",
  "password": "password123",
  "role": "USER"
}
📌 Login
POST /api/auth/login

json
{
  "username": "user",
  "password": "user123"
}
📌 Refresh Token
POST /api/auth/refresh

json
{
  "refreshToken": "your.refresh.token.here"
}
📤 Response Structure
json
{
  "accessToken": "eyJhbGciOi...",
  "refreshToken": "eyJhbGciOi..."
}
⚙️ Configuration
Key configuration options in application.yml:

yaml
application:
  security:
    jwt:
      secret-key: your-secret-key-here  # ⚠️ Change this in production!
      expiration: 86400000              # 24 hours
      refresh-token:
        expiration: 604800000           # 7 days
📝 License
MIT License — see LICENSE for details.

📑 Summary
This project includes:

📚 Clear setup instructions for both local and Docker deployments

👥 Documentation of pre-loaded sample users

📖 Complete API reference with real request/response examples

⚙️ Configuration details for both H2 and PostgreSQL

📦 Response structure and token management documentation

👏 Credits
Built by Arav Baboolal & Forage — 2025 🔥

For practice and educational use.
