# Ecommerce App 

This repository serves as a monorepo for three distinct microservices that collectively form the backbone of our application. The goal of this architecture is to simplify the management of dependencies, streamline development processes, and enhance collaboration among teams. Each microservice operates independently but is organized within a single repository to promote consistency and ease of integration.

## Microservices Included

1. [User Service](https://github.com/abhishekY2401/user-service)
The User Service manages user-related functionalities, including user registration, authentication, and profile management. It leverages JWT authentication for secure access and provides endpoints for CRUD operations on user data.

2. [Product Service](https://github.com/abhishekY2401/product-service)
The Product Service handles the catalog of products, managing inventory, product details, and pricing. It communicates with the User Service to fetch user information and updates its inventory based on orders placed through the Order Service.

3. [Order Service](https://github.com/abhishekY2401/order-service)
The Order Service processes user orders, managing the lifecycle of an order from placement to fulfillment. It emits events to other services (e.g., Order Placed) using RabbitMQ for event-driven communication, ensuring consistent state management across the microservices.

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

## Getting Started

### Clone the Repository

```
git clone https://github.com/abhishekY2401/ecommerce-app.git
cd ecommerce-app
```

### Environment Variables

Make sure to update the sensitive environment variables in a .env file for security purpose. The following environment variables are used:

DATABASE_URL: Connection string for PostgreSQL (for an example)
``` 
postgresql://{postgres_user}:{postgres_password}@{database_container_name}:5432/{postgres_db_name}
```
RABBITMQ_URI: Connection string for RabbitMQ.
JWT_SECRET_KEY: Secret key for JWT authentication.

## Running the Application

1. Build and Start Services: Use Docker Compose to build and start all services defined in the docker-compose.yml file.

```
docker-compose up --build
```

    This will build the docker images for each service
    Start all the services in the background

2. Accessing Services: Once the services are up and running, you can access them through the following ports:

    User Service -> http://localhost:8000
    
    Product Service -> http://localhost:7000
    
    Order Service -> http://localhost:5000

### Stopping Services

To stop all running services, use:

```
docker-compose down
```

## Lastly, very important to merge all the microservice folder into this repository in local, as this will be able to smoothly bring up and running all services.
