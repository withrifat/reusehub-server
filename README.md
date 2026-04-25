# ReuseHub Backend API

## Overview

ReuseHub is a community-driven platform designed to help users share, exchange, and reuse unused items. This repository contains the backend API service that powers the platform.

### Core Functionality

- User authentication and authorization
- Item management and inventory tracking
- Image upload and storage integration
- User-to-user communication system
- Secure API endpoints with role-based access control

---

## Features

- **Authentication System**
  - User registration and login
  - JWT-based authentication and session management

- **Item Management**
  - Create, read, update, and delete items
  - Track item availability status
  - Categorization and filtering

- **Image Upload**
  - Cloud storage integration via Cloudinary
  - Secure file handling

- **Communication**
  - User-to-user messaging system
  - Expandable for real-time capabilities

- **Security**
  - Protected routes with middleware-based authorization
  - Secure data validation and sanitization

---

## Tech Stack

- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MongoDB + Mongoose** - Database and ODM
- **JWT** - Authentication mechanism
- **Cloudinary** - Image storage and management

---

## Installation

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn package manager
- MongoDB instance
- Cloudinary account

### Setup Instructions

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd reusehub-server
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Configure environment variables**

   Create a `.env` file in the root directory with the following variables:

   ```env
   PORT=5000
   DB_URL=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   
   CLOUDINARY_CLOUD_NAME=your_cloud_name
   CLOUDINARY_API_KEY=your_api_key
   CLOUDINARY_API_SECRET=your_api_secret
   ```

4. **Start the server**

   Development mode:
   ```bash
   npm run dev
   ```

   Production mode:
   ```bash
   npm start
   ```

---

## API Endpoints

### Authentication Routes

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|----------------|
| POST | `/api/auth/register` | Register a new user | No |
| POST | `/api/auth/login` | Login user | No |
| GET | `/api/auth/profile` | Get user profile | Yes |

### Item Routes

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|----------------|
| POST | `/api/items` | Create a new item | Yes |
| GET | `/api/items` | Get all items | No |
| GET | `/api/items/:id` | Get item by ID | No |
| PUT | `/api/items/:id` | Update item | Yes |
| DELETE | `/api/items/:id` | Delete item | Yes |

---

## Architecture

The project follows a modular architecture with clear separation of concerns:

- **Controllers** - Handle business logic and request processing
- **Routes** - Define API endpoints
- **Middleware** - Implement authentication and authorization
- **Models** - Define database schemas
- **Utils** - Provide reusable utility functions

---

## Security Considerations

- Passwords are hashed using bcrypt
- Sensitive credentials must be stored in environment variables
- HTTPS is required for production deployments
- All incoming data is validated before processing
- API endpoints are protected with JWT authentication where appropriate

---

## Future Enhancements

- Real-time messaging with Socket.io
- User notification system
- Rating and review system
- Location-based item filtering
- Recommendation engine

---

## Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add YourFeature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

Please ensure code follows the existing structure and includes appropriate documentation.

---

## License

This project is licensed under the MIT License. See the LICENSE file for more details.
