# Express.js and MongoDB REST API

This project is a simple REST API built with Express.js and MongoDB. It includes user authentication, profile viewing, fetching a random joke from the Chuck Norris API, and user logout functionality.

## Project Structure


## Features

1. **User Signup**: `/api/users/signup`
2. **User Login**: `/api/users/login`
3. **View Profile**: `/api/users/me` (Authenticated users only)
4. **Get a Random Joke**: `/api/random-joke` (Authenticated users only)
5. **User Logout**: `/api/users/logout` (Authenticated users only)

## Setup

### Prerequisites

- Node.js
- MongoDB

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/myapp.git
    cd myapp
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

3. Start MongoDB:
    ```bash
    mongod
    ```

4. Run the application:
    ```bash
    node app.js
    ```

The server will start on `http://localhost:3000`.

## API Endpoints

### User Signup

- **URL**: `/api/users/signup`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "username": "your_username",
        "password": "your_password"
    }
    ```

### User Login

- **URL**: `/api/users/login`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "username": "your_username",
        "password": "your_password"
    }
    ```

- **Response**:
    ```json
    {
        "token": "your_jwt_token"
    }
    ```

### View Profile

- **URL**: `/api/users/me`
- **Method**: `GET`
- **Headers**:
    ```json
    {
        "Authorization": "Bearer your_jwt_token"
    }
    ```

### Get a Random Joke

- **URL**: `/api/random-joke`
- **Method**: `GET`
- **Headers**:
    ```json
    {
        "Authorization": "Bearer your_jwt_token"
    }
    ```

- **Response**:
    ```json
    {
        "joke": "Random Chuck Norris joke"
    }
    ```

### User Logout

- **URL**: `/api/users/logout`
- **Method**: `POST`
- **Headers**:
    ```json
    {
        "Authorization": "Bearer your_jwt_token"
    }
    ```

## Middleware

### Authentication

The `authenticate.js` middleware checks the validity of the JWT token and allows access to protected routes.

## License

This project is licensed under the MIT License.
