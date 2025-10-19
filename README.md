# Airbnb Clone Project

## Overview

This project is a clone of the popular short-let booking website AirBnb. It is designed to help me develop professional level skills in Software engineering specifically in Backend development.

## Project Goals

- User Management: Secure user registration, authentication, and profile management.
- Property Management: Features for property listing creation, updates, and retrieval.
- Booking System: Allow users to reserve properties and manage booking details.
- Payment Processing: Integrate payments and record transactions.
- Review System: Users can leave reviews and ratings for properties.
- Data Optimization: Efficient data retrieval and storage through database optimizations.

## Tech Stack

- **Django** — high-level Python web framework.  
- **Django REST Framework** — REST API tooling.  
- **PostgreSQL** — relational database.  
- **GraphQL** — flexible data querying.  
- **Celery** — background/asynchronous tasks.  
- **Redis** — caching and session store.  
- **Docker** — containerization.  
- **CI/CD Pipelines** — automated tests & deployments.

## Team Roles

- Backend Developer: Responsible for designing and building the various API endpoints, buisiness logic, and database models in the project.
- Database Administrator: Responsible for designing, indexing, and performance of the database.
- DevOps Engineer: Responsible for designing and implementing the CI/CD process of the project.
- QA Engineer: Responsible for the individual and wholistic testing of the developed system, ensuring it meets the expected quality of the client.

## Technology Stack

- Django: Python framework for building web applications.
- PostgreSQL: Relational database management system.
- GraphQL: Database querying engine
- Celery: Manages background tasks asynchronously.
- Redis: Database management system for caching and session storage.
- Docker: Containerization system for easy deployment.
- CI/CD Pipelines: For automated testing and deployment of the application.

## Database Design

### Users

| Entity Name | Description |
| ----------- | ----------- |
| id          | primary key of user |
| firstname   | user first name |
| lastname    | user last name |
| date of birth | user date of birth |
| email        | user personal email address |
| password    | user password |

### Properties

| Entity Name | Description |
| ----------- | ----------- |
| id          | primary key of property |
| address   | property address |
| postcode    | property postcode |
| number_of_bedrooms  | number of bedrooms in the property |
| number of bathrooms        | number of bathrooms in the property |
| property_type    | Type of property e.g. studio, maisonette, semi-detached, etc. |

### Bookings

| Entity Name | Description |
| ----------- | ----------- |
| id          | primary key of booking |
| owner   | id of user who booked the property |
| start_date    | Date that booking will begin |
| end_date | Date when booking will end |
| price        | Price paid for booking |
| booking_date    | Date when booking was created |

### Reviews

| Entity Name | Description |
| ----------- | ----------- |
| id          | primary key of review |
| customer_id   | id of customer who wrote review |
| property_id    | id of propert which received review |
| cleanliness | 1 to 5 rating of how clean the property was. |
| owner_responsiveness        | 1 to 5 rating of how responsive the property owner was to resolving concerns |
| review_date    | Date when review was created. |

### Payments

| Entity Name | Description |
| ----------- | ----------- |
| id          | primary key of payment |
| transaction_id   | unique transaction id |
| transaction type    | ENUM (Completed, Failed, Refund, Partial-Refund, etc.) |
| date of transaction | date when transaction took place |
| customer_id        | customer who created the transaction |
| booking_id    | booking transaction is related to. |

## Feature Breakdown

### User Management

- **Endpoints:** `/users/`, `/users/{user_id}/`  
- **Features:** Register, authenticate, and manage user profiles.

### Property Management

- **Endpoints:** `/properties/`, `/properties/{property_id}/`  
- **Features:** Create, update, retrieve, and delete property listings.

### Booking System

- **Endpoints:** `/bookings/`, `/bookings/{booking_id}/`  
- **Features:** Make, update, and manage bookings, including check-in and check-out details.

## API Security

Ensuring the security of our API is a top priority. The following measures are implemented to protect user data, maintain system integrity, and prevent unauthorized access.

### Key Security Measures

| Security Measure | Description | Purpose |
|------------------|-------------|----------|
| **Authentication** | All API endpoints require valid authentication tokens (e.g., JWT or OAuth 2.0). | Ensures that only verified users and systems can access the API. |
| **Authorization** | Role-based access control (RBAC) defines what actions users can perform. | Prevents unauthorized users from accessing restricted resources. |
| **Rate Limiting** | Limits the number of requests per user/IP in a given time period. | Protects against abuse, denial-of-service (DoS) attacks, and API overload. |
| **Input Validation & Sanitization** | All incoming data is validated and sanitized before processing. | Prevents injection attacks and data corruption. |
| **Encryption (HTTPS & Data-at-Rest)** | All communication occurs over HTTPS; sensitive data is encrypted in storage. | Protects user credentials and sensitive information from interception. |
| **Logging & Monitoring** | API activity is logged and monitored for suspicious behavior. | Enables early detection of potential security threats. |

---

### 🧠 Why Security Is Crucial

- **Protecting User Data:**  
  Sensitive information such as personal details, emails, and passwords must be protected from unauthorized access and data breaches.

- **Securing Payments:**  
  If financial transactions are involved, proper encryption and authentication prevent fraud and ensure trust between users and the system.

- **Maintaining System Integrity:**  
  Security controls like rate limiting and input validation prevent malicious users from exploiting vulnerabilities or overloading the system.

- **Compliance with Regulations:**  
  Following best security practices helps meet data protection regulations (e.g., GDPR, CCPA), reducing legal and reputational risks.

## CI/CD Pipeline

### What is a CI/CD Pipeline?

A **CI/CD (Continuous Integration and Continuous Deployment)** pipeline automates the process of integrating code changes, testing, and deploying applications. It ensures that new features or bug fixes are continuously tested and delivered to production with minimal manual intervention.

### Why It’s Important

Implementing a CI/CD pipeline helps maintain code quality, speed up development, and reduce human error. Key benefits include:

- **Faster Development Cycles:** Automates building, testing, and deployment processes.
- **Early Bug Detection:** Continuous testing helps identify issues before they reach production.
- **Consistent Deployments:** Ensures the same deployment process is used across all environments.
- **Improved Collaboration:** Allows developers to integrate their work frequently and confidently.
- **Higher Reliability:** Reduces downtime and deployment-related issues.

### Tools Commonly Used

| Tool | Purpose |
|------|----------|
| **GitHub Actions** | Automates CI/CD workflows directly within GitHub. |
| **Docker** | Packages applications into containers for consistent deployment. |
| **Jenkins** | Open-source automation server for managing CI/CD pipelines. |
| **CircleCI** | Cloud-based CI/CD service for automating builds and tests. |
| **Kubernetes** | Orchestrates containerized applications for scalable deployment. |
