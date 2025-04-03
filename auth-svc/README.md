# Auth Service - CodeVerse

The Auth Service is responsible for authentication and authorization in CodeVerse. It provides JWT-based authentication and acts as a middleware proxy for other services, ensuring all requests are validated before being forwarded.

GitHub: https://github.com/veeraj-k/codeverse-auth-service
Backend: https://codeverse-auth-svc.onrender.com/

## Features

- User authentication using JWT
- Role-based authorization
- Acts as a proxy to authenticate and forward requests to other services
- Built with Golang, Gin, and Gorm
- Uses PostgreSQL as the database

## Tech Stack

- **Language**: Golang
- **Framework**: Gin
- **Database**: PostgreSQL
- **ORM**: Gorm
- **Authentication**: JWT

## Architecture

1. Users authenticate using login credentials.
2. The service generates a JWT token upon successful authentication.
3. For every request, the service validates the JWT token before forwarding it to other services.
4. If authentication fails, the request is rejected.

## Endpoints

| Method | Endpoint | Description |
|--------|---------|-------------|
| POST | `/register` | Registers a new user |
| POST | `/login` | Authenticates a user and returns a JWT token |
| GET | `/validatetoken` | Validates the JWT token |
| POST | `/admin/users` | Registers a new admin user |
| GET/PUT/POST/PUT | `/` | ReReoutes the request to required services |


## Setup Instructions

### Prerequisites

- Go installed
- PostgreSQL database set up

### Steps

1. Clone the repository:
   ```sh
   git clone https://github.com/veeraj-k/codeverse-auth-service
   cd codeverse-auth-service
   ```
2. Set up environment variables and save it in a .env file:
   ```sh
    DB_HOST=
    DB_USER=
    DB_PASSWORD=
    DB_NAME=postgres
    DB_PORT=5432

    SECRET_KEY=
    ADMIN_USERNAME=admin
    ADMIN_PASSWORD=admin
    ADMIN_EMAIL=admin

    PMS_SERVICE_URL=https://codeverse-pms-svc.onrender.com
    SUBMISSION_SERVICE_URL=https://codeverse-submission-svc.onrender.com
    PORT=4000
   ```
3. Install dependencies:
   ```sh
   go mod tidy
   ```
4. Run the service:
   ```sh
   go run main.go
   ```



