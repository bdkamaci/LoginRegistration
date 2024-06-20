# Login Registration System

A simple login and registration system using Spring Boot, Spring Security, PostgreSQL, and SMTP email integration.

## Overview

This project implements a basic login and registration system where users can sign up, receive a confirmation email, and activate their accounts. It uses Spring Boot for backend development, Spring Security for authentication and authorization, PostgreSQL for database storage, and SMTP for sending confirmation emails.

### Features

- User registration with email confirmation.
- Account activation via email link.
- Role-based access control (user and admin roles).
- Secure password storage using BCrypt encryption.
- Error handling and validation for registration inputs.

## Dependencies

- Java 8 or higher
- Spring Boot 2.5.0
- Spring Security
- Spring Data JPA
- Lombok
- PostgreSQL
- BCryptPasswordEncoder
- Jakarta Mail (for email sending)

## Setup

### Database Configuration

1. Ensure PostgreSQL is installed and running.
2. Create a database named `registration`.
3. Update `application.yml` with your PostgreSQL database username and password:

   ```yaml
   spring:
     datasource:
       url: jdbc:postgresql://localhost:5432/registration
       username: your_username
       password: your_password


### SMTP Configuration
Configure SMTP settings in application.yml for sending confirmation emails:

    ```spring:
        mail:
            host: localhost
            port: 1025
            username: hello
            password: hello
            properties:
                mail:
                    smtp:
                        ssl:
                            trust: "*"
                        auth: true
                        starttls:
                            enable: true
                        connectiontimeout: 5000
                        timeout: 3000
                        writetimeout: 5000

### Running the Application
1. Clone the repository.
2. Build the project using Maven or your preferred IDE.
3. Run the application. The server will start on http://localhost:8080.

### Usage

#### Registration

Use POST request to /api/v1/registration with JSON body:

``` 
    {
    "firstName": "John",
    "lastName": "Doe",
    "email": "john.doe@example.com",
    "password": "securePassword"
    }
```


Upon successful registration, a confirmation email will be sent.

#### Confirm Email

Use GET request to /api/v1/registration/confirm?token=confirmation_token.
The account will be activated upon valid token confirmation.

### Contributors

Burcu Doga KAMACI

### Inspired By

Amigoscode
