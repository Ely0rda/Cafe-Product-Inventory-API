# Cafe Product Inventory API

![Go](https://img.shields.io/badge/Go-1.19-blue)
![REST API](https://img.shields.io/badge/REST-API-green)
![Swagger](https://img.shields.io/badge/Swagger-Documented-orange)

A RESTful API for managing cafe product inventory, built with Go and documented with Swagger.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [API Documentation](#api-documentation)
- [Installation](#installation)
- [Usage](#usage)
- [Testing](#testing)
- [Folder Structure](#folder-structure)
- [Skills Demonstrated](#skills-demonstrated)
- [License](#license)

## Overview

The Cafe Product Inventory API is a robust RESTful service that enables cafe owners to manage their product inventory efficiently. This API supports creating, reading, updating, and deleting (CRUD) operations for cafe products such as coffee, tea, and other beverages.

## Features

1. **Complete CRUD Operations**: Manage products with full create, read, update, and delete capabilities
2. **Robust Validation**: Data validation for product fields using regex patterns and value constraints
3. **Swagger Documentation**: Auto-generated API documentation with Swagger
4. **Graceful Shutdown**: Properly handles server shutdown with timeout for ongoing operations
5. **Middleware Implementation**: Validation middleware for request processing pipeline

## Architecture

This project follows a clean architecture pattern with clear separation of concerns:

- **Handlers Layer**: HTTP request handlers that manage API routes
- **Data Layer**: Business logic and data models
- **Validation Layer**: Input validation and error handling

The API is designed as a RESTful service that adheres to REST principles with proper HTTP methods and status codes.

## Tech Stack

- **Language**: Go 1.19
- **Web Framework**: Gorilla Mux for routing
- **API Documentation**: Go-Swagger
- **Validation**: go-playground/validator
- **Testing**: Standard Go testing package with testify assertions

## API Documentation

The API is documented using Swagger, which can be accessed at `/docs` when the server is running. Here are the available endpoints:

| Method | Endpoint         | Description               |
|--------|------------------|---------------------------|
| GET    | /products        | Get all products          |
| GET    | /products/{id}   | Get a specific product    |
| POST   | /products        | Create a new product      |
| PUT    | /products        | Update an existing product|
| DELETE | /products/{id}   | Delete a product          |

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Ely0rda/Cafe-Product-Inventory-API.git
   ```

2. Navigate to the project directory:
   ```bash
   cd Cafe-Product-Inventory-API/product_api
   ```

3. Install dependencies:
   ```bash
   go mod download
   ```

## Usage

1. Start the server:
   ```bash
   go run main.go
   ```

2. The server will start on port 9090 by default (configurable via BIND_ADDRESS environment variable)

3. Example API calls:

   **GET all products**
   ```bash
   curl localhost:9090/products | jq
   ```

   **Create a product**
   ```bash
   curl localhost:9090/products -XPOST -d '{"name":"warm chocola","description":"warm cup of chocola","price":7,"sku":"abc-agc-ahu"}'
   ```

   **Update a product**
   ```bash
   curl localhost:9090/products -XPUT -d '{"id":3,"name":"tea","description":"warm cup of tea","price":4,"sku":"abc-agc-ahu"}'
   ```

   **Delete a product**
   ```bash
   curl localhost:9090/products/3 -XDELETE
   ```

## Testing

Run the tests using the Go test command:

```bash
go test ./...
```

The project includes tests for data validation and JSON serialization/deserialization.

## Folder Structure

```
product_api/
├── data/            # Data models and business logic
├── handlers/        # HTTP request handlers
├── go.mod           # Go module dependencies
├── main.go          # Application entry point
├── Makefile         # Build and utility commands
└── swagger.yaml     # API documentation
```

## Skills Demonstrated

- **Go Programming**: Leveraging Go's strong typing, concurrency model, and standard library
- **RESTful API Design**: Proper implementation of REST principles and HTTP status codes
- **API Documentation**: Swagger integration for automatic API documentation
- **Input Validation**: Robust validation with custom validation rules
- **Error Handling**: Comprehensive error handling with appropriate HTTP responses
- **Middleware Development**: Custom middleware for request processing
- **Testing**: Unit tests for critical components
- **Project Structure**: Clean architecture with separation of concerns

## License

This project is licensed under the MIT License - see the LICENSE file for details.