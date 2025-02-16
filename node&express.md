**Node.js and Express.js Interview Questions & Answers**

## **Node.js Interview Questions & Answers**

### **1. Core Concepts**

**Q: What is Node.js, and how does it work?**  
**A:** Node.js is a JavaScript runtime built on Chrome's V8 engine. It allows developers to run JavaScript on the server-side. It uses an event-driven, non-blocking I/O model, making it lightweight and efficient for handling asynchronous operations.

**Q: What is the event loop in Node.js? How does it handle asynchronous operations?**  
**A:** The event loop is the core of Node.js's asynchronous execution. It continuously checks the callback queue and executes functions when the call stack is empty, enabling non-blocking I/O.

**Q: Explain the difference between `setImmediate()`, `process.nextTick()`, and `setTimeout()`.**  
**A:**
- `setImmediate()`: Executes after the current event loop phase.
- `process.nextTick()`: Executes before the next event loop iteration.
- `setTimeout()`: Executes after a specified delay.

**Q: How does Node.js handle concurrency with a single-threaded event loop?**  
**A:** Node.js uses an event-driven architecture where asynchronous tasks are delegated to the worker threads in the libuv thread pool, preventing blocking of the main thread.

**Q: What are Streams in Node.js? Explain their types.**  
**A:** Streams handle data in chunks, improving performance. Types:
- Readable Streams (e.g., `fs.createReadStream`)
- Writable Streams (e.g., `fs.createWriteStream`)
- Duplex Streams (both readable & writable)
- Transform Streams (modifies data while reading/writing)

**Q: What is the difference between `spawn()`, `exec()`, and `fork()` in Node.js?**  
**A:**
- `spawn()`: Executes a command as a new process, returning a stream.
- `exec()`: Runs a command and buffers output in a callback.
- `fork()`: Creates a child process for inter-process communication.

**Q: What is the purpose of `process.env` in Node.js?**  
**A:** `process.env` allows access to environment variables, useful for managing configurations like database credentials and API keys.

---

### **2. Asynchronous Programming**

**Q: What are callbacks, promises, and async/await? When would you use each?**  
**A:**
- **Callbacks:** Functions passed as arguments to handle asynchronous tasks.
- **Promises:** Objects representing the completion or failure of an async operation.
- **async/await:** Simplifies promise handling by making async code look synchronous.

**Q: Explain how you handle errors in asynchronous code.**  
**A:**
- Use `try...catch` with async/await.
- Handle promise rejections with `.catch()`.
- Pass errors to the callback in callback-based functions.

---

### **3. Package Management**

**Q: What is `package.json` and why is it important?**  
**A:** It contains metadata about the project, dependencies, scripts, and configurations.

**Q: What is the difference between `npm` and `yarn`?**  
**A:**
- `npm`: Default package manager for Node.js.
- `yarn`: Alternative with better performance and security.

---

### **4. Performance and Optimization**

**Q: How do you optimize performance in a Node.js application?**  
**A:** Use caching, optimize database queries, use clustering, and minimize middleware.

**Q: What is clustering in Node.js, and how does it improve performance?**  
**A:** Clustering allows multiple instances of Node.js to run on different CPU cores, improving scalability.

---

### **5. Security**

**Q: How do you prevent SQL injection in a Node.js application?**  
**A:** Use parameterized queries and ORM libraries like Mongoose.

**Q: How do you protect an Express.js app from CSRF attacks?**  
**A:** Use CSRF tokens and `express-csrf` middleware.

---

### **6. Testing**

**Q: How do you write unit tests in Node.js?**  
**A:** Use Jest, Mocha, or Chai for testing functions and API endpoints.

---

## **Express.js Interview Questions & Answers**

### **1. Core Concepts**

**Q: What is Express.js? Why is it used in Node.js applications?**  
**A:** Express.js is a minimal web framework for Node.js, providing features like routing, middleware support, and request handling.

**Q: How does middleware work in Express.js?**  
**A:** Middleware functions process requests and responses in a pipeline before sending the final response.

---

### **2. Middleware and Request Handling**

**Q: What are the different types of middleware in Express.js?**  
**A:** Application-level, Router-level, Error-handling, Built-in, and Third-party middleware.

**Q: How do you handle errors in Express.js?**  
**A:** Define an error-handling middleware:  
```js
app.use((err, req, res, next) => {
  res.status(500).json({ error: err.message });
});
```

---

### **3. Database Integration**

**Q: How do you connect MongoDB with Express.js?**  
**A:** Use Mongoose:  
```js
const mongoose = require('mongoose');
mongoose.connect('mongodb://localhost:27017/mydb', { useNewUrlParser: true, useUnifiedTopology: true });
```

---

### **4. Authentication & Authorization**

**Q: How do you implement authentication in an Express app?**  
**A:** Use JWT-based authentication or session-based authentication.

**Q: What is the difference between JWT and session-based authentication?**  
**A:** JWT is stateless and stored on the client, while session-based authentication stores user data on the server.

---

### **5. API Development**

**Q: How do you create a RESTful API in Express.js?**  
**A:** Define routes and controllers:
```js
app.get('/users', (req, res) => {
  res.json({ message: 'User data' });
});
```

**Q: What is CORS, and how do you enable it in Express?**  
**A:** CORS allows cross-origin requests:
```js
const cors = require('cors');
app.use(cors());
```

---

### **6. Deployment & Scaling**

**Q: How do you deploy an Express.js app to production?**  
**A:** Use Docker, Nginx, or PM2 for process management and deploy on AWS, Heroku, or DigitalOcean.

**Q: How do you handle environment variables in Express?**  
**A:** Use `dotenv` package:
```js
require('dotenv').config();
console.log(process.env.API_KEY);
```

---

This document provides in-depth answers for key Node.js and Express.js interview questions for a Full Stack MERN Developer with 3 years of experience.

