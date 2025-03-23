# Backend for Authentication System

This repository contains the backend for an authentication system built with Node.js, Express, MongoDB, and JWT (JSON Web Tokens). It provides endpoints for user signup, signin, password reset, and retrieving user information.

## Table of Contents
- [Features](#features)
- [Technologies](#technologies)
- [Prerequisites](#prerequisites)
- [Setup](#setup)
- [Environment Variables](#environment-variables)
- [API Endpoints](#api-endpoints)
- [Running the Backend](#running-the-backend)
- [Deployment](#deployment)
- [Folder Structure](#folder-structure)
- [Contributing](#contributing)
- [License](#license)

## Features
- User registration (signup) with email and password.
- User login (signin) with JWT generation.
- Forgot password functionality with reset token generation.
- User info retrieval with JWT verification.
- Secure password hashing with bcrypt.
- MongoDB integration for persistent storage.

## Technologies
- **Node.js**: JavaScript runtime for server-side logic.
- **Express**: Web framework for building RESTful APIs.
- **MongoDB**: NoSQL database for storing user data.
- **Mongoose**: ODM for MongoDB and Node.js.
- **JWT**: JSON Web Tokens for authentication.
- **Bcrypt**: Password hashing library.
- **Crypto**: For generating secure reset tokens.

## Prerequisites
- **Node.js**: v16.x or higher (download from [nodejs.org](https://nodejs.org/)).
- **MongoDB**: Local instance or cloud service (e.g., MongoDB Atlas).
- **Git**: For version control.

## Setup
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/your-backend-repo.git
   cd your-backend-repo

2. Install Dependencies:
    npm install

3. Set Up MongoDB:
    **If using a local MongoDB instance, ensure it’s running (mongod).
If using MongoDB Atlas, create a cluster and get the connection string.
Configure Environment Variables: Create a .env file in the root directory (see ).

API Endpoints
Method	Endpoint	Description	Request Body	Response
POST	/api/auth/signup	Register a new user	{ email, password }	{ token }
POST	/api/auth/signin	Login a user	{ email, password }	{ token }
POST	/api/auth/forgot-password	Request password reset	{ email }	{ message }
GET	/api/auth/user	Get user info (authenticated)	None (requires Authorization: Bearer <token>)	{ id, email }

your-backend-repo/
├── models/           # Mongoose models
│   └── User.js       # User schema
├── routes/           # API routes
│   └── auth.js       # Authentication routes
├── .env              # Environment variables (not tracked)
├── .gitignore        # Git ignore file
├── server.js         # Main server file
├── package.json      # Dependencies and scripts
└── README.md         # This file