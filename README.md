# Express Middleware Logging and Authentication

## Course Outcome Mapped

**CO3:** Implement RESTful APIs and integrate databases (MongoDB/MySQL) with a backend server using Node.js and Express.js.
**CO4:** Debug, test, and optimize full-stack applications by analyzing performance and security aspects.

---

# Aim

To implement Express middleware for logging and authentication in a Node.js application.

---

# Objectives

* Create custom logging middleware
* Develop authentication middleware
* Apply middleware to routes
* Test middleware sequencing
* Handle middleware errors

---

# Hardware Requirements

* Minimum **4 GB RAM**
* **Dual-core processor**

---

# Software Requirements

* **Node.js 18+**
* **Express.js**
* **MongoDB**
* **Postman**

---

# About the Experiment

This experiment demonstrates how middleware works in the request-response cycle of a backend application. Middleware functions allow developers to process requests, perform authentication, log activity, and handle errors before sending responses.

The experiment includes:

* Request/Response pipeline handling
* Middleware chaining using `next()`
* Error-handling middleware
* Authentication patterns using tokens
* Request logging for monitoring API usage

---

# Project Structure

```
express-middleware-project
│
├── server.js
│
├── middleware
│   ├── logger.js
│   ├── auth.js
│   └── errorHandler.js
│
├── routes
│   └── userRoutes.js
│
├── package.json
└── README.md
```

---

# Installation

### 1. Clone the repository

```
git clone https://github.com/your-username/express-middleware-project.git
```

### 2. Navigate to the project folder

```
cd express-middleware-project
```

### 3. Install dependencies

```
npm install
```

### 4. Run the server

```
node server.js
```

Server will start on:

```
http://localhost:3000
```

---

# API Endpoints

## Public Route

```
GET /api/public
```

Response:

```
{
  "message": "This is a public route"
}
```

---

## Protected Route

```
GET /api/profile
```

Header Required:

```
Authorization: mysecrettoken
```

Response:

```
{
  "message": "Welcome to protected profile route"
}
```

---

# Expected Output

* Request logs displayed in the console
* Protected route access with a valid token
* **401 Unauthorized** error for invalid tokens
* Proper middleware execution sequence
* Error handling for server issues

---

# Viva Questions

**1. What is middleware in Express?**
Middleware is a function that executes during the request-response cycle and can modify the request or response objects.

**2. How does the `next()` function work?**
`next()` passes control to the next middleware function in the chain.

**3. Why is the error handler placed last?**
Express executes middleware sequentially, so the error handler must be last to catch errors from previous middleware.

**4. What is the difference between `app.use()` and `router.use()`?**
`app.use()` applies middleware globally, while `router.use()` applies it to specific routes.

**5. How would you implement API rate limiting?**
By using middleware such as `express-rate-limit` to restrict the number of requests from a client within a specific time window.

---

# Conclusion

This experiment demonstrates the use of middleware in Express.js for logging requests, authenticating users, and handling errors efficiently. Middleware improves the security, maintainability, and scalability of backend applications.
