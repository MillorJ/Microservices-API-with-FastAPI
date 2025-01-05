# Microservices API with FastAPI

## Overview

This project demonstrates a simple microservices architecture using FastAPI. It includes three independent microservices:

1. **Product Service**: Handles product-related data.
2. **Customer Service**: Handles customer-related data.
3. **Order Service**: Handles order-related data and communicates with the other services to validate customers and products.

## API Endpoints

### Product Service

- **POST /products**: Add a new product.
- **GET /products/{product_id}**: Get product details by ID.
- **PUT /products/{product_id}**: Update a product.
- **DELETE /products/{product_id}**: Delete a product.

### Customer Service

- **POST /customers**: Add a new customer.
- **GET /customers/{customer_id}**: Get customer details by ID.
- **PUT /customers/{customer_id}**: Update customer information.
- **DELETE /customers/{customer_id}**: Delete a customer.

### Order Service

- **POST /orders**: Create a new order. This service will:
  - Verify that the customer exists by communicating with the Customer Service.
  - Verify that the product exists by communicating with the Product Service.
  - Create the order only if the customer and product are valid.
- **GET /orders/{order_id}**: Get order details.
- **PUT /orders/{order_id}**: Update an order.
- **DELETE /orders/{order_id}**: Delete an order.

## Project Setup

### Prerequisites

Make sure you have Python 3.7 or later installed on your system.

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/yourusername/your-repository.git
   cd your-repository


# Install FastAPI and other dependencies:

   command: pip install "fastapi[all]"

# If you have additional dependencies listed in a requirements.txt file, install them as follows:

    command: pip install -r requirements.txt


# Running the Services:

# Start Product Service:
  command: uvicorn product_service:app --reload --port 3004

# Start Customer Service:
  command: uvicorn customer_service:app --reload --port 3005

# Start Order Service:
  command: uvicorn orderservice:app --reload --port 3006


# Testing the API with Postman


 Product Service:

# POST /products

Set URL: http://127.0.0.1:3004/products
Method: POST
Body: Choose raw and JSON format
Sample JSON:

{
  "name": "Sample Product",
  "price": 19.99,
  "description": "This is a sample product."
}


# GET /products/{product_id}

Set URL: http://127.0.0.1:3004/products/{product_id}
Method: GET


  Customer Service:
  
  POST /customers


# Set URL: http://127.0.0.1:3005/customers
Method: POST
Body: Choose raw and JSON format
Sample JSON

{
  "name": "John Doe",
  "email": "johndoe@example.com"
}


# GET /customers/{customer_id}

Set URL: http://127.0.0.1:3005/customers/{customer_id}
Method: GET


Order Service: 


# POST /orders

Set URL: http://127.0.0.1:3006/orders
Method: POST
Body: Choose raw and JSON format
Sample JSON:

{
  "customer_id": 1,
  "product_id": 1,
  "quantity": 2
}


# GET /orders/{order_id}

Set URL: http://127.0.0.1:3006/orders/{order_id}
Method: GET



I’ve been exploring how FastAPI works recently, and I’m happy to report that I’ve achieved success in understanding it.

# EXTRA
pip install python-jose[cryptography] passlib[bcrypt] fastapi

....






