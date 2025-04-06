# NexaRide Backend

## Overview
NexaRide is a backend service for a ride-sharing application. This project is built using Node.js and Express, and it utilizes MongoDB for data storage through Mongoose.

## Project Structure
```
Backend
├── controllers
│   └── user.controller.js      # Handles user registration and validation
├── models
│   └── user.model.js           # Defines the user schema and methods
├── routes
│   └── user.routes.js          # Sets up user-related routes
├── services
│   └── user.service.js         # Contains business logic for user creation
├── package.json                 # npm configuration file
├── .env                         # Environment variables
└── README.md                    # Project documentation
```

## Installation
1. Clone the repository:
   ```
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```
   cd Backend
   ```
3. Install the dependencies:
   ```
   npm install
   ```

## Environment Variables
Create a `.env` file in the root directory and add the following variables:
```
JWT_SECRET=<your_jwt_secret>
```

## Usage
To start the server, run:
```
npm start
```

## API Endpoints
### User Registration
- **POST** `/register`
  - Request Body:
    ```json
    {
      "fullname": {
        "firstname": "John",
        "lastname": "Doe"
      },
      "email": "john.doe@example.com",
      "password": "yourpassword"
    }
    ```
  - Response:
    - On success:
      ```json
      {
        "token": "<jwt_token>",
        "user": {
          "fullname": {
            "firstname": "John",
            "lastname": "Doe"
          },
          "email": "john.doe@example.com"
        }
      }
      ```
    - On error:
      ```json
      {
        "errors": [
          {
            "msg": "Invalid Email",
            "param": "email"
          }
        ]
      }
      ```

## Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License
This project is licensed under the MIT License.