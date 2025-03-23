# /users/register Endpoint Documentation

## Description
Endpoint to register a new user. It validates incoming data, hashes the password, stores user details, and returns an authentication token along with user information upon successful registration.

## HTTP Method
POST

## URL
/users/register

## Request Body
- **fullname** (object, required): 
  - **firstname** (string, required): Minimum length of 3 characters.
  - **lastname** (string, optional): Minimum length of 3 characters.
- **email** (string, required): Valid email address.
- **password** (string, required): Minimum length of 6 characters.

### Example Request
```json
{
  "fullname": {
    "firstname": "John",
    "lastname": "Doe"
  },
  "email": "john.doe@example.com",
  "password": "yourpassword"
}
```

## Responses

### Success (HTTP 201)
```json
{
  "token": "JWT token string here",
  "user": {
    // user object details
  }
}
```

### Validation Error (HTTP 400)
```json
{
  "errors": [
    // array of error messages if validation fails
  ]
}
```
