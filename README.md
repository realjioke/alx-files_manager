# ALX Files Manager

## Overview

The **ALX Files Manager** is a web-based application designed to facilitate secure file storage, management, and access. Developed as part of the ALX Software Engineering program, this project integrates several backend technologies to provide a robust and efficient file management system.

## Features

- **User Authentication**: Secure user registration and login using token-based authentication.
- **File Upload and Management**: Users can upload, view, and manage their files seamlessly.
- **Access Control**: Set permissions to control file accessibility.
- **Thumbnail Generation**: Automatic creation of image thumbnails for quick previews.
- **Background Processing**: Efficient handling of tasks like email notifications and thumbnail generation using background workers.

## Technologies Used

- **Backend**: Node.js with Express.js framework
- **Database**: MongoDB for data storage
- **Caching**: Redis for caching and session management
- **Background Jobs**: Bull library for handling background tasks
- **Authentication**: JSON Web Tokens (JWT) for secure authentication
- **Testing**: Mocha and Chai for unit and integration tests

## Installation

### Prerequisites

Ensure you have the following installed:

- [Node.js](https://nodejs.org/) (version 12.x.x or higher)
- [MongoDB](https://www.mongodb.com/) (local instance or [MongoDB Atlas](https://www.mongodb.com/cloud/atlas))
- [Redis](https://redis.io/)

### Steps

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/realjioke/alx-files_manager.git
   cd alx-files_manager
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   ```

3. **Set Up Environment Variables**:
   Create a `.env` file in the root directory and configure the following variables:
   ```
   PORT=5000
   DB_HOST=localhost
   DB_PORT=27017
   DB_DATABASE=files_manager
   REDIS_HOST=localhost
   REDIS_PORT=6379
   ```

4. **Start the Application**:
   - **Start the Server**:
     ```bash
     npm run start-server
     ```
   - **Start the Worker** (for background tasks):
     ```bash
     npm run start-worker
     ```

## API Documentation

The application provides a RESTful API with the following endpoints:

- **Authentication**:
  - `POST /users`: Register a new user
  - `GET /connect`: User login
  - `GET /disconnect`: User logout
  - `GET /users/me`: Retrieve user profile

- **File Management**:
  - `POST /files`: Upload a new file
  - `GET /files/:id`: Retrieve file metadata
  - `GET /files`: List all user files
  - `PUT /files/:id/publish`: Make a file public
  - `PUT /files/:id/unpublish`: Make a file private
  - `GET /files/:id/data`: Download a file

For detailed request and response structures, refer to the [API Documentation](./docs/api.md).

## Testing

To run tests, execute:
```bash
npm test
```

Ensure that your test environment is configured correctly, and necessary services (MongoDB, Redis) are running.

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature-branch
   ```
3. Make your changes and commit them:
   ```bash
   git commit -m "Description of changes"
   ```
4. Push to the branch:
   ```bash
   git push origin feature-branch
   ```
5. Open a Pull Request detailing your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more information.
