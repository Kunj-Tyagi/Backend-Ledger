# Backend-Ledger

A robust Node.js backend service for managing financial ledger operations with authentication, account management, and transaction tracking capabilities.

## 📋 Overview

Backend-Ledger is a RESTful API service built with Express.js and MongoDB, designed to handle financial ledger operations. It provides secure user authentication, account management, and transaction processing features.

## 🚀 Features

- **User Authentication**: Secure authentication with JWT tokens and bcrypt password hashing
- **Account Management**: Create, read, update, and delete financial accounts
- **Transaction Processing**: Record and manage financial transactions
- **Cookie-based Sessions**: Secure session management using HTTP cookies
- **Email Notifications**: Integrated email service using Nodemailer
- **MongoDB Integration**: Persistent data storage with Mongoose ODM

## 🛠️ Tech Stack

- **Runtime**: Node.js
- **Framework**: Express.js v5.2.1
- **Database**: MongoDB with Mongoose v9.1.5
- **Authentication**: JSON Web Tokens (JWT) + bcryptjs
- **Email Service**: Nodemailer v7.0.12
- **Environment Management**: dotenv

## 📁 Project Structure

```
Backend-Ledger/
├── src/
│   ├── app.js              # Express application setup
│   ├── config/             # Configuration files (database, etc.)
│   ├── controllers/        # Request handlers
│   ├── middleware/         # Custom middleware
│   ├── models/            # Mongoose data models
│   ├── routes/            # API route definitions
│   │   ├── auth.routes.js
│   │   ├── account.routes.js
│   │   └── transaction.routes.js
│   └── services/          # Business logic layer
├── server.js              # Application entry point
├── package.json
└── .gitignore
```

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Kunj-Tyagi/Backend-Ledger.git
   cd Backend-Ledger
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   
   Create a `.env` file in the root directory with the following variables:
   ```env
   # MongoDB Connection
   MONGODB_URI=your_mongodb_connection_string

   # JWT Secret
   JWT_SECRET=your_jwt_secret_key

   # Email Configuration (for Nodemailer)
   EMAIL_HOST=smtp.example.com
   EMAIL_PORT=587
   EMAIL_USER=your_email@example.com
   EMAIL_PASSWORD=your_email_password

   # Server Configuration
   PORT=3000
   ```

4. **Start the server**
   
   Development mode (with nodemon):
   ```bash
   npm run dev
   ```
   
   Production mode:
   ```bash
   npm start
   ```

## 🌐 API Endpoints

### Base URL
```
http://localhost:3000
```

### Health Check
- **GET** `/` - Check if the service is running

### Authentication Routes
- **Base Path**: `/api/auth`
- Handles user registration, login, and authentication

### Account Routes
- **Base Path**: `/api/accounts`
- Manages financial account operations

### Transaction Routes
- **Base Path**: `/api/transactions`
- Handles transaction creation and management

## 🔒 Authentication

The API uses JWT (JSON Web Tokens) for authentication. Protected routes require a valid JWT token to be included in the request cookies.

### Authentication Flow:
1. User registers or logs in via `/api/auth`
2. Server returns JWT token stored in HTTP-only cookie
3. Subsequent requests include the cookie automatically
4. Server validates token before processing protected requests

## 📦 Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| express | ^5.2.1 | Web framework |
| mongoose | ^9.1.5 | MongoDB ODM |
| jsonwebtoken | ^9.0.3 | JWT authentication |
| bcryptjs | ^3.0.3 | Password hashing |
| cookie-parser | ^1.4.7 | Cookie parsing |
| nodemailer | ^7.0.12 | Email sending |
| dotenv | ^17.2.3 | Environment variables |

## 🏃‍♂️ Running the Application

The server runs on port 3000 by default. Once started, you should see:
```
Server is running on port 3000
```

## 👤 Author

**Kunj Tyagi**

## 📄 License

This project is licensed under the ISC License.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📞 Support

For support, email the repository owner or open an issue on GitHub.

---

**Note**: Make sure to keep your `.env` file secure and never commit it to version control. The `.gitignore` file is configured to exclude sensitive files.
```
