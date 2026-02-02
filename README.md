# Personalized News Aggregator API

## Description
A RESTful API built with Node.js and Express that allows users to register, log in, set news preferences, and fetch personalized news articles from external sources. It features JWT-based authentication, password hashing with bcrypt, and basic caching.

## Tech Stack
- **Node.js & Express.js:** Backend framework.
- **Bcrypt:** Password hashing.
- **JWT (JsonWebToken):** Secure authentication.
- **Axios:** Fetching data from external News API.

## Installation
1. Clone the repository.
2. Run `npm install` to install dependencies.
3. (Optional) Get a free API Key from [NewsAPI.org](https://newsapi.org) and add it to `app.js`.
4. Run `npm start` (or `node app.js`) to start the server.

## API Endpoints

### 1. Register User
- **POST** `/register`
- **Body:** `{ "email": "test@test.com", "password": "123", "preferences": ["bitcoin", "tech"] }`
- **Response:** 201 Created

### 2. Login
- **POST** `/login`
- **Body:** `{ "email": "test@test.com", "password": "123" }`
- **Response:** `{ "token": "eyJhbGciOi..." }`

### 3. Get Preferences (Protected)
- **GET** `/preferences`
- **Header:** `Authorization: Bearer <token>`
- **Response:** `["bitcoin", "tech"]`

### 4. Update Preferences (Protected)
- **PUT** `/preferences`
- **Header:** `Authorization: Bearer <token>`
- **Body:** `{ "preferences": ["sports", "health"] }`
- **Response:** 200 OK

### 5. Get News (Protected)
- **GET** `/news`
- **Header:** `Authorization: Bearer <token>`
- **Response:** Returns a list of articles based on user preferences.

## Testing
Run the automated test suite with:
```bash
npm run test