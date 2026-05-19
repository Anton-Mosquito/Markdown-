# API Reference

## `GET /users`

Retrieve a paginated list of users.

### Request

```json
{
  "page": 1,
  "limit": 10,
  "search": "john"
}
```

**Response** `200 OK`

```json
{
  "page": 1,
  "limit": 10,
  "total": 45,
  "users": [
    {
      "id": "12345",
      "name": "John Doe",
      "email": "john.doe@example.com"
    },
    {
      "id": "12346",
      "name": "Jane Smith",
      "email": "jane.smith@example.com"
    }
  ]
}
```

> [!NOTE]
> Use the `search` parameter to filter users by name or email.

## `POST /auth/login`

Authenticate a user and return an access token.

### Request

```json
{
  "email": "user@example.com",
  "password": "secret123"
}
```

**Response** `200 OK`

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expireµsIn": 3600,
  "refreshToken": "dGhpcy1pcy1hLXJlZnJlc2gtdG9rZW4=",
  "user": {
    "id": "1",
    "name": "User Example",
    "email": "user@example.com"
  }
}
```

> [!WARNING]
> Access tokens expire in 1 hour. Call `/auth/refresh` before expiry to maintain session.

## `POST /auth/refresh`

Refresh an expired access token using a valid refresh token.

### Request

```json
{
  "refreshToken": "dGhpcy1pcy1hLXJlZnJlc2gtdG9rZW4="
}
```

**Response** `200 OK`

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expiresIn": 3600
}
```

## `GET /users/{id}`

Retrieve a single user by ID.

### Request

```
GET /users/12345
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

**Response** `200 OK`

```json
{
  "id": "12345",
  "name": "John Doe",
  "email": "john.doe@example.com",
  "role": "member",
  "createdAt": "2026-05-19T12:00:00Z"
}
```

## `PUT /users/{id}`

Update user profile fields.

### Request

```json
{
  "name": "John Doe",
  "email": "john.new@example.com"
}
```

**Response** `200 OK`

```json
{
  "id": "12345",
  "name": "John Doe",
  "email": "john.new@example.com",
  "updatedAt": "2026-05-19T12:15:00Z"
}
```

## `DELETE /users/{id}`

Remove a user from the system.

### Request

```
DELETE /users/12345
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

**Response** `204 No Content`


## Error Codes

| Code | Meaning               | Description                                        |
| ---- | --------------------- | -------------------------------------------------- |
| 400  | Bad Request           | Invalid request payload or missing required fields |
| 401  | Unauthorized          | Missing or invalid authentication token            |
| 403  | Forbidden             | Authenticated user does not have permission        |
| 404  | Not Found             | Requested resource does not exist                  |
| 429  | Too Many Requests     | Request rate limit exceeded                        |
| 500  | Internal Server Error | Unexpected server error                            |

## Auth flow

```mermaid
sequenceDiagram
    participant Client
    participant API
    participant Auth

    Client->>API: POST /auth/login
    API->>Auth: verify credentials
    Auth-->>API: access token + refresh token
    API-->>Client: 200 OK with tokens

    Client->>API: GET /users/12345
    API->>API: validate access token
    API-->>Client: 200 OK with user data

    Client->>API: POST /auth/refresh
    API->>Auth: verify refresh token
    Auth-->>API: new access token
    API-->>Client: 200 OK with new token
```

## Endpoints

| Endpoint             | Description                     |
| :------------------- | :------------------------------ |
| `GET /users`         | Get a paginated list of users   |
| `POST /auth/login`   | Authenticate and receive tokens |
| `POST /auth/refresh` | Refresh an access token         |
| `GET /users/{id}`    | Retrieve a user by ID           |
| `PUT /users/{id}`    | Update a user profile           |
| `DELETE /users/{id}` | Remove a user from the system   |