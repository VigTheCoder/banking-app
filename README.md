# Banking Application

This project is a **Banking Application** built using **Spring Boot** and connected to a **MySQL database**. It provides RESTful APIs for creating accounts, viewing balances, depositing and withdrawing funds, and more. It is designed to simulate basic banking operations with a secure and efficient backend.

## Table of Contents:
- [Overview](#overview)
- [Features](#features)
- [Setup and Requirements](#setup-and-requirements)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Screenshots](#screenshots)
- [Troubleshooting](#troubleshooting)
- [References](#references)

## Overview
The Banking Application simulates basic banking operations and provides CRUD (Create, Read, Update, Delete) functionalities for account management. The application interacts with a MySQL database for storing account information and transactions. Users can manage bank accounts, view balances, deposit or withdraw funds, and delete accounts via simple REST APIs.

The goal is to build a secure and scalable banking application that mimics real-world banking features.

## Features
- **Account Creation**: Allows users to create new bank accounts.
- **Account Details**: Fetches account details, including balance and transactions.
- **Funds Deposit**: Enables users to deposit funds into their accounts.
- **Funds Withdrawal**: Allows users to withdraw funds from their accounts.
- **Account Deletion**: Lets users delete bank accounts.
- **Get All Accounts**: Retrieves a list of all bank accounts.
- **CRUD APIs**: Exposes account operations through RESTful endpoints.
- **Error Handling**: Provides clear error responses for invalid requests.

## Setup and Requirements

### Prerequisites
To get started, you need to have the following installed:
- **Java 17+**
- **MySQL** (for the database)
- **Maven** (for project management)
- **IntelliJ IDEA** (or your preferred IDE)

### Project Directory Layout

    .
    ├── src
    │   ├── main
    │   │   ├── java
    │   │   │   ├── net
    │   │   │   │   ├── javaguides
    │   │   │   │   │   ├── banking
    │   │   │   │   │   │   ├── BankingAppApplication.java  # Main Application file
    │   │   │   │   │   │   ├── controller                  # API controllers
    │   │   │   │   │   │   ├── dto                         # Data Transfer Objects
    │   │   │   │   │   │   ├── entity                      # Entity classes (e.g., Account)
    │   │   │   │   │   │   └── mapper                       # Mapper for DTOs and Entities
    │   │   ├── resources
    │   │   │   └── application.properties                    # Database configurations
    ├── pom.xml                                                # Project configuration (Maven)
    ├── LICENSE
    └── README.md

### Running the Application
To run the application:

1. Clone the repository:
    ```bash
    git clone https://github.com/VigTheCoder/banking-app.git
    ```

2. Set up the database:
    - Create a database `banking_app` in MySQL.
    - Update the database connection details in `src/main/resources/application.properties`:
      ```properties
      spring.application.name=banking-app
      spring.datasource.url=jdbc:mysql://localhost:3306/banking_app
      spring.datasource.username=root
      spring.datasource.password=root
      spring.jpa.hibernate.ddl-auto=update
      ```

3. Build the project and run the application using Maven:
    ```bash
    mvn clean install
    mvn spring-boot:run
    ```

The application will be available at **localhost:8080** by default.

## API Endpoints
The application exposes the following API endpoints:

- **POST /api/accounts** - Create a new bank account.
- **GET /api/accounts/{id}** - Get details of a specific account.
- **PUT /api/accounts/{id}/deposit** - Deposit funds into a bank account.
- **PUT /api/accounts/{id}/withdraw** - Withdraw funds from a bank account.
- **GET /api/accounts** - Get a list of all accounts.
- **DELETE /api/accounts/{id}** - Delete a specific bank account.

### Screenshots

Below is a screenshot showing the database created in MySQL Workbench named banking_app:
- Database Screenshot
![Alt text](/images/database.png)

Postman CRUD Operations
- Create Account
![Alt text](/images/post2.png)


- Get Account Details by ID
![Get](/images/GetMapping.png)

- Get All Account Details in the Database
![getAllAccounts](/images/getAllAccounts.png)

- Deposit Funds
![deposit](/images/deposit.png)

- Withdraw Funds
![withdraw](/images/withdraw.png)

- Delete Account
![delete](/images/delete.png)

### Troubleshooting
- If you encounter database connection issues, make sure your MySQL server is running and the database credentials are correct.
- For any errors related to Maven or dependencies, try running mvn clean install to resolve the issues.
- Ensure that your MySQL database has the necessary permissions for the user you have configured in application.properties.

### References
- Spring Boot: https://spring.io/projects/spring-boot
- Spring Data JPA: https://spring.io/projects/spring-data-jpa
- MySQL: https://www.mysql.com/
- Postman: https://www.postman.com/
