# 449-Midterm-Project | Flask RESTful API with Authentication, Error Handling, and File Handling

## Overview
This project is a RESTful API built using Flask that includes authentication, error handling, file handling, and CRUD operations. The API consists of public and admin routes, ensuring secure access using JWT authentication.

## Features
- User authentication with JWT (JSON Web Tokens)
- Error handling with proper status codes
- File handling (uploading and retrieving files)
- Public routes accessible without authentication
- Admin routes requiring authentication
- CRUD operations for managing items in a database
- MySQL database integration

## Requirements
Make sure you have the following installed before running the project:
- Python 3.x
- MySQL Server
- Virtual environment (optional but recommended)

## Setup Instructions

### 1. Clone the Repository
```sh
git clone <repository-url>
cd <repository-folder>
```

### 2. Set Up a Virtual Environment (Optional but Recommended)
```sh
python -m venv venv
source venv/bin/activate  # On Windows, use 'venv\Scripts\activate'
```

### 3. Install Dependencies
```sh
pip install -r requirements.txt
```

### 4. Configure Database
Create a MySQL database and update the `app.config['SQLALCHEMY_DATABASE_URI']` in `app.py` with your database credentials:
```python
app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql://username:password@localhost/dbname'
```

### 5. Run the Application
```sh
python app.py
```
The server should start running on `http://127.0.0.1:5000`

## API Endpoints

### Authentication
- **Register a User:** `POST /register`
- **Login and Get JWT Token:** `POST /login`

### Public Route
- **Public Route (No Authentication Required):** `GET /public`

### Admin Routes (Require JWT Authentication)
- **Protected Admin Route:** `GET /admin`

### File Handling
- **Upload a File:** `POST /upload` (Requires JWT Authentication)
- **Retrieve a File:** `GET /files/<filename>` (Requires JWT Authentication)

### CRUD Operations (Requires JWT Authentication)
- **Get All Items:** `GET /items`
- **Add an Item:** `POST /items`
- **Update an Item:** `PUT /items/<item_id>`
- **Delete an Item:** `DELETE /items/<item_id>`

## Testing the API with Postman
1. Use Postman to send requests to `http://127.0.0.1:5000`.
2. Obtain a JWT token by logging in and include it in the `Authorization` header as `Bearer <token>` for protected routes.
3. Test file uploads using the `/upload` endpoint.

## Additional Notes
- Ensure MySQL is running and accessible before launching the API.
- Run database migrations if needed (`flask db migrate` and `flask db upgrade`).
- Modify `JWT_SECRET_KEY` in `app.py` for better security.

## Authors
- Ian Gabriel Vista
- ?


