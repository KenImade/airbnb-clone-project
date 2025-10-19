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
