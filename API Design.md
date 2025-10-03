# API Design

## API Structure

RESTful API following standard HTTP conventions and JSON response format.

## Base URL

```
https://api.poketrade.vault/v1
```

## Authentication

All authenticated endpoints require JWT token in Authorization header:
```
Authorization: Bearer <token>
```

## Core Endpoints

### Authentication
- `POST /auth/register` - Create new user account
- `POST /auth/login` - Authenticate and receive token
- `POST /auth/logout` - Invalidate token
- `GET /auth/me` - Get current user info

### Users
- `GET /users/:id` - Get user profile
- `PUT /users/:id` - Update user profile
- `GET /users/:id/pokemon` - Get user's Pokemon

### Pokemon
- `GET /pokemon` - List all available Pokemon (with filters)
- `POST /pokemon` - Add new Pokemon to vault
- `GET /pokemon/:id` - Get specific Pokemon details
- `PUT /pokemon/:id` - Update Pokemon details
- `DELETE /pokemon/:id` - Remove Pokemon from vault

### Trades
- `GET /trades` - List user's trades
- `POST /trades` - Create new trade proposal
- `GET /trades/:id` - Get trade details
- `PUT /trades/:id` - Update trade (accept/reject)
- `DELETE /trades/:id` - Cancel trade

## Response Format

### Success Response
```json
{
  "success": true,
  "data": { ... }
}
```

### Error Response
```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Human readable message"
  }
}
```

## Status Codes

- `200 OK` - Successful GET/PUT request
- `201 Created` - Successful POST request
- `204 No Content` - Successful DELETE request
- `400 Bad Request` - Invalid request data
- `401 Unauthorized` - Missing or invalid authentication
- `403 Forbidden` - Insufficient permissions
- `404 Not Found` - Resource not found
- `500 Internal Server Error` - Server error

## Related Documents

- [[Data Model]] - Entity definitions
- [[Architecture]] - System architecture
- [[Security]] - Authentication and authorization
