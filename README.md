# Ecommerce App 

This repository serves as a monorepo for three distinct microservices that collectively form the backbone of our application. The goal of this architecture is to simplify the management of dependencies, streamline development processes, and enhance collaboration among teams. Each microservice operates independently but is organized within a single repository to promote consistency and ease of integration.

## Microservices Included

1. [User Service](https://github.com/abhishekY2401/user-service)
The User Service manages user-related functionalities, including user registration, authentication, and profile management. It leverages JWT authentication for secure access and provides endpoints for CRUD operations on user data.

2. [Product Service](https://github.com/abhishekY2401/product-service)
The Product Service handles the catalog of products, managing inventory, product details, and pricing. It communicates with the User Service to fetch user information and updates its inventory based on orders placed through the Order Service.

3. [Order Service](https://github.com/abhishekY2401/order-service)
The Order Service processes user orders, managing the lifecycle of an order from placement to fulfillment. It emits events to other services (e.g., Order Placed, Order Shipped) using RabbitMQ for event-driven communication, ensuring consistent state management across the microservices.

## 🛠️ Technologies Used

- Language: Python
- Framework & Libraries:
    - Flask
    - SQLAlchemy (Database ORM)
    - Pika (RabbitMQ client)
    - Alembic (for Database Migrations)
- Database: PostgreSQL
- Message Queue: RabbitMQ
- GraphQL: Ariadne (for GraphQL implementation)
- Authentication: JWT (JSON Web Tokens)

## 📋 Prerequisites

Before setting up the microservice, ensure the following are installed:
- [Python 3.8+](https://www.python.org/downloads/)
- [Docker](https://www.docker.com/products/docker-desktop/)
- [PostgreSQL](https://www.postgresql.org/download/)
- [RabbitMQ](https://www.cloudamqp.com/)
