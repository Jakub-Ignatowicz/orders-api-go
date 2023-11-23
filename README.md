<p align="center">
  <img width="200" src="https://devopedia.org/images/article/135/5996.1544439861.png" alt="Go Logo">
  <img width="200" src="https://millionwebservices.com/wp-content/uploads/2022/05/Dispersed-Cache-Service-for-Redis1.png" alt="Reddis Logo">
</p>

# Orders API with Redis Database

This repository contains a simple Orders API built in Go that utilizes Redis as its primary database. The API is designed to handle basic CRUD operations for orders, and it is implemented using the Chi router.

## Setup

Before running the application, ensure that you have Go and Redis installed on your system.

1. Clone the repository:

   ```bash
   git clone https://github.com/Jakub-Ignatowicz/orders-api-go.git
   cd orders-api-redis
   ```

2. Install dependencies:

   ```bash
   go mod download
   ```

3. Configure Redis connection:
   Update the Redis connection details in the `config/config.go` file if needed.

4. Run the application:
   ```bash
   go run main.go
   ```

## API Routes

The API provides the following endpoints for managing orders:

1. List Orders: - `GET /orders`: Retrieve a list of all orders.

2. Get Order by ID: - `GET /orders/{id}`: Retrieve details of a specific order by ID.

3. Create Order: - `POST /orders`: Create a new order.

4. Update Order by ID: - `PUT /orders/{id}`: Update details of a specific order by ID.

5. Delete Order by ID: - `DELETE /orders/{id}`: Delete a specific order by ID.

## Example Usage

1.  ### List Orders

               curl -X GET http://localhost:8080/orders

2.  ### Get Order by ID

               curl -X GET http://localhost:8080/orders/{id}

3.  ### Create Order

               curl -X POST http://localhost:8080/orders -d '{"name": "Product Name", "price": 19.99, "quantity": 2}'

4.  ### Update Order by ID

               curl -X PUT http://localhost:8080/orders/{id} -d '{"name": "Updated Product Name", "price": 25.99, "quantity": 3}'

5.  ### Delete Order by ID
               curl -X DELETE http://localhost:8080/orders/{id}

## Configuration

The application can be configured via the `application/config.go` file. Update the Redis connection details, port, or any other necessary configurations.

```go
        // application/config.go

        package config

        type Config struct {
            RedisURL string
            Port     string
        }
```

Feel free to customize the configuration according to your environment.

## Dependencies

- github.com/go-chi/chi: Router for the API.
- github.com/go-redis/redis/v8: Redis client for Go.

## License

This project is licensed under the MIT License.

Feel free to contribute, report issues, or suggest improvements. Happy coding!
