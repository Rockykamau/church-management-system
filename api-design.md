# API Design for Church Management System

## 1. **Authentication**
### Endpoints
- **POST** `/auth/login`
  - Request: `{ "username": "string", "password": "string" }`
  - Response: `{ "token": "string", "expiresIn": "integer" }`

- **POST** `/auth/register`
  - Request: `{ "username": "string", "email": "string", "password": "string" }`
  - Response: `{ "message": "User registered successfully" }`

- **POST** `/auth/forgot-password`
  - Request: `{ "email": "string" }`
  - Response: `{ "message": "Password reset link sent" }`

---

## 2. **User Management**
### Endpoints
- **GET** `/users`
  - Response: `[ { "id": "integer", "name": "string", "role": "string" } ]`

- **POST** `/users`
  - Request: `{ "name": "string", "email": "string", "role": "string" }`
  - Response: `{ "message": "User created successfully" }`

- **PUT** `/users/{id}`
  - Request: `{ "name": "string", "email": "string", "role": "string" }`
  - Response: `{ "message": "User updated successfully" }`

- **DELETE** `/users/{id}`
  - Response: `{ "message": "User deleted successfully" }`

---

## 3. **Attendance Tracking**
### Endpoints
- **GET** `/attendance/events`
  - Response: `[ { "id": "integer", "name": "string", "date": "string" } ]`

- **POST** `/attendance`
  - Request: `{ "eventId": "integer", "memberId": "integer", "status": "Present/Absent" }`
  - Response: `{ "message": "Attendance recorded" }`

---

## 4. **Finance Management**
### Endpoints
- **GET** `/finance/summary`
  - Response: `{ "income": "number", "expenses": "number", "balance": "number" }`

- **POST** `/finance/donation`
  - Request: `{ "amount": "number", "memberId": "integer", "date": "string" }`
  - Response: `{ "message": "Donation recorded" }`

- **POST** `/finance/expense`
  - Request: `{ "amount": "number", "category": "string", "date": "string" }`
  - Response: `{ "message": "Expense recorded" }`
