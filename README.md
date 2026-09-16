# GiftLink

GiftLink is a full-stack web application that connects users who want to give away household items they no longer need with people who enjoy recycling and prefer finding free items instead of purchasing new ones.

The platform promotes sustainability and community sharing by making it easy for users to list, search, and request household goods.

---

## Features

* Home page
* Landing page
* Navigation bar
* Search functionality
* Gift/item listing page
* Item details page
* User registration
* User login
* Editable user profile
* Comments and sentiment analysis
* JWT authentication
* REST API
* MongoDB database
* Request logging
* CORS support
* Global error handling

---

## Technologies Used

### Frontend

* React
* HTML5
* CSS3
* JavaScript

### Backend

* Node.js
* Express.js
* MongoDB
* Mongoose

### Authentication & Security

* JSON Web Tokens (JWT)
* Password hashing
* Middleware validation
* dotenv for environment variables

### DevOps & Deployment

* Docker
* GitHub Actions
* Kubernetes
* IBM Code Engine

### Logging

* Pino
* Pino HTTP

---

## Project Architecture

GiftLink follows a full-stack architecture:

```text
React Frontend
      │
      │ REST API
      ▼
Node.js / Express.js
      │
      ├── Authentication
      ├── Gifts
      ├── Search
      └── Logging
      │
      ▼
MongoDB
```

The backend provides REST API endpoints for authentication, gifts, and search functionality.

---

## API Endpoints

### Gifts

```text
/api/gifts
```

Handles gift/item-related operations.

### Search

```text
/api/search
```

Provides search functionality for gifts.

### Authentication

```text
/api/auth
```

Handles user registration, login and authentication.

### Root

```http
GET /
```

Returns:

```text
Inside the server
```

---

## Project Structure

```text
giftproject/
│
├── giftlink-backend/
│   ├── models/
│   │   └── db.js
│   ├── routes/
│   │   ├── giftRoutes.js
│   │   ├── searchRoutes.js
│   │   └── authRoutes.js
│   ├── util/
│   │   └── import-mongo/
│   ├── logger.js
│   ├── app.js
│   └── package.json
│
├── giftlink-frontend/
│   ├── public/
│   ├── src/
│   └── package.json
│
├── sentiment/
│
└── README.md
```

---

## Backend Configuration

The backend uses environment variables with `dotenv`.

Create a `.env` file:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
NODE_ENV=development
```

Do not commit the `.env` file to GitHub.

---

## Running the Backend

Navigate to the backend directory:

```bash
cd giftlink-backend
```

Install dependencies:

```bash
npm install
```

Start the server:

```bash
npm start
```

The API runs on:

```text
http://localhost:3060
```

---

## Running the Frontend

Navigate to the frontend directory:

```bash
cd giftlink-frontend
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm start
```

---

## Database

GiftLink uses **MongoDB** for persistent data storage.

The backend connects to MongoDB when the application starts. Initial gift data can be imported using the `loadData()` utility.

---

## Logging & Error Handling

The backend uses **Pino** and **Pino HTTP** for request and application logging.

A global Express error handler returns:

```text
500 Internal Server Error
```

when an unexpected server error occurs.

---

## Testing

The application supports a test environment using:

```env
NODE_ENV=test
```

Database connection and initial data loading are skipped when running in test mode.

---

## License

This project was created as a full-stack learning and capstone project.
