# 🚗 Ride Evee Backend Assignment

A backend system for managing users in an electric vehicle ecosystem. It supports JWT and OTP-based authentication, and allows full CRUD operations on user data. Built with Node.js, Express.js, and MongoDB, fully containerized using Docker Compose.

---

## 🔧 Features

- ✅ User Signup & Login with JWT
- ✅ Email-based OTP Signup/Signin
- ✅ Secure CRUD APIs for User Resource
- ✅ Input validation and error handling
- ✅ Protected routes via middleware
- ✅ Modular and scalable architecture
- ✅ Dockerized with `docker-compose.yml` (no Dockerfile used)

---

## 🛠️🖥️ System Design 

  ![WhatsApp Image 2025-04-01 at 13 43 30_e38b1cff](https://github.com/user-attachments/assets/98514ca4-42f3-448e-9da5-4065b1fbc938)


## 📁 Project Structure
```bash


ride-evee-backend/
│── docker-compose.yml # Runs Node.js and MongoDB containers
│── .env # Environment variables (JWT_SECRET, DB_URI, EMAIL creds, etc.)
│── package.json # Project dependencies
│── server.js # Express server entry point
│
├── config/
│ └── db.js # MongoDB connection setup
│
├── controllers/
│ ├── authController.js # Signup, Login, OTP Send/Verify logic
│ └── userController.js # User CRUD logic
│
├── models/
│ ├── User.js # Mongoose User schema
│ └── OTP.js # Mongoose OTP schema with expiry
│
├── routes/
│ ├── authRoutes.js # Routes for login, signup, OTP
│ └── userRoutes.js # Routes for CRUD operations
│
├── middleware/
│ ├── authMiddleware.js # JWT token verification middleware
│ └── errorHandler.js # Centralized error handling middleware
│
├── utils/
│ └── sendEmail.js # Nodemailer configuration for sending OTP emails
│
└── public/ # Frontend static files (hosted on GitHub Pages)
├── index.html # Main HTML file
├── style.css # Styling
├── script.js # Frontend logic
└── assets/ # Images, icons, logos, etc. (optional)/yourusername/ride-evee-backend.git

```
### 2. Create `.env` file

```env
PORT=4832
JWT_SECRET=your_jwt_secret
MONGO_URI=mongodb://mongo:27117/rideevee
EMAIL_USER=your_email@example.com
EMAIL_PASS=your_email_password
OTP_EXPIRY_MINUTES=10
```
### 3. Start the application

```bash
docker-compose up
```

## 📮 API Endpoints

### 🔐 Auth

- `POST /auth/signup` – Register user with JWT
- `POST /auth/login` – Login user with JWT
- `POST /auth/otp/send` – Send OTP to email
- `POST /auth/otp/verify` – Verify OTP for login/signup

### 👤 Users

- `GET /users` – Get all users
- `GET /users/:id` – Get user by ID
- `POST /users` – Create a user
- `PUT /users/:id` – Update user (Protected)
- `DELETE /users/:id` – Delete user (Protected)


## 📦 Tech Stack

- **Backend:** Node.js, Express.js
- **Database:** MongoDB
- **Auth:** JWT, OTP via Email (Nodemailer)
- **Containerization:** Docker + Docker Compose



