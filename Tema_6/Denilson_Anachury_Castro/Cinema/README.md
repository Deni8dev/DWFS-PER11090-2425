# REST API Cinema

## Endpoints

| HTTP Method | URI                          | Description                                  | Query Params                          | Request Body                                  | Response Body                                                                                               | HTTP Response Code |
|-------------|------------------------------|----------------------------------------------|---------------------------------------|------------------------------------------------|-------------------------------------------------------------------------------------------------------------|-------------------|
| POST        | /movies                       | Create a new movie                           | -                                  | `{ "title": "string", "duration": "int", "genre": "string", "releaseDate": "string" }`   | `{ "id": "int", "title": "string", "duration": "int", "genre": "string", "releaseDate": "string" }`            | 201 Created       |
| DELETE      | /movies/{movieId}             | Delete a movie                               | -                                  | -                                           | `{ "message": "Movie deleted successfully" }`                                                                 | 200 OK            |
| PUT         | /movies/{movieId}             | Modify a movie                               | -                                  | `{ "title": "string", "duration": "int", "genre": "string", "releaseDate": "string" }` | `{ "id": "int", "title": "string", "duration": "int", "genre": "string", "releaseDate": "string" }`            | 200 OK            |
| POST        | /rooms                        | Create a new room                            | -                                  | `{ "roomName": "string", "seats": "int" }`    | `{ "id": "int", "roomName": "string", "seats": "int" }`                                                      | 201 Created       |
| DELETE      | /rooms/{roomId}               | Delete a room                                | -                                  | -                                           | `{ "message": "Room deleted successfully" }`                                                                  | 200 OK            |
| PUT         | /rooms/{roomId}               | Modify a room (full modification)            | -                                  | `{ "roomName": "string", "seats": "int" }`    | `{ "id": "int", "roomName": "string", "seats": "int" }`                                                      | 200 OK            |
| PATCH       | /rooms/{roomId}               | Modify a room (partial modification)         | -                                  | `{ "roomName": "string" | "seats": "int" }`  | `{ "id": "int", "roomName": "string", "seats": "int" }`                                                      | 200 OK            |
| POST        | /users                        | Create a new user                            | -                                  | `{ "name": "string", "email": "string", "password": "string" }` | `{ "id": "int", "name": "string", "email": "string" }`                                                         | 201 Created       |
| DELETE      | /users/{userId}               | Delete a user                                | -                                  | -                                           | `{ "message": "User deleted successfully" }`                                                                  | 200 OK            |
| PUT         | /users/{userId}               | Modify a user (full modification)            | -                                  | `{ "name": "string", "email": "string", "password": "string" }` | `{ "id": "int", "name": "string", "email": "string" }`                                                         | 200 OK            |
| PATCH       | /users/{userId}               | Modify a user (partial modification)         | -                                  | `{ "name": "string" | "email": "string" | "password": "string" }` | `{ "id": "int", "name": "string", "email": "string" }`                                                         | 200 OK            |
| POST        | /reservations                 | Create a reservation for a user              | -                                  | `{ "userId": "int", "roomId": "int", "movieId": "int", "seatNumber": "int" }`   | `{ "reservationId": "int", "userId": "int", "roomId": "int", "movieId": "int", "seatNumber": "int" }`      | 201 Created       |
| DELETE      | /reservations/{reservationId} | Cancel a reservation for a user              | -                                  | -                                           | `{ "message": "Reservation canceled successfully" }`                                                           | 200 OK            |
| PUT         | /reservations/{reservationId} | Modify a reservation for a user              | -                                  | `{ "roomId": "int", "seatNumber": "int" }`  | `{ "reservationId": "int", "userId": "int", "roomId": "int", "seatNumber": "int" }`                        | 200 OK            |
| POST        | /payments                     | Register a payment for a reservation         | -                                  | `{ "reservationId": "int", "amount": "float", "paymentMethod": "string" }` | `{ "paymentId": "int", "reservationId": "int", "amount": "float", "paymentMethod": "string", "status": "string" }` | 201 Created       |