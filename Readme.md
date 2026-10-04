# Go Movies CRUD API

A small Go API for managing movies.

## Run the server

```bash
go run main.go
```

The server starts on:

```text
http://localhost:8000
```

## Routes

### Get all movies

```http
GET /movies
```

Example:

```bash
curl http://localhost:8000/movies
```

### Get one movie by ID

```http
GET /movies/{id}
```

Example:

```bash
curl http://localhost:8000/movies/1
```

### Create a movie

```http
POST /movies
```

Example request body:

```json
{
  "isbn": "1234567",
  "title": "Inception",
  "director": {
    "firstname": "Christopher",
    "lastname": "Nolan"
  }
}
```

Example:

```bash
curl -X POST http://localhost:8000/movies \
  -H "Content-Type: application/json" \
  -d '{
  "isbn": "1234567",
  "title": "Inception",
  "director": {
     "firstname": "Christopher",
     "lastname": "Nolan"
   }
  }'
```

### Update a movie

```http
PUT /movies/{id}
```

Example request body:

```json
{
  "id": "5562808",
  "isbn": "1234568",
  "title": "The Dark Knight",
  "director": {
    "firstname": "Christopher",
    "lastname": "Nolan"
  }
}
```

Example:

```bash
curl -X PUT http://localhost:8000/movies/5562808 \
  -H "Content-Type: application/json" \
  -d '{
  "id": "5562808",
  "isbn": "1234568",
  "title": "The Dark Knight",
  "director": {
     "firstname": "Christopher",
     "lastname": "Nolan"
   }
  }'
```

### Delete a movie

```http
DELETE /movies/{id}
```

Example:

```bash
curl -X DELETE http://localhost:8000/movies/1
```

### Delete all movies

```http
DELETE /movies
```

Example:

```bash
curl -X DELETE http://localhost:8000/movies
```

## Notes

This project is a simple REST API example using Go and the standard library. It stores movie data in memory while the server is running.
