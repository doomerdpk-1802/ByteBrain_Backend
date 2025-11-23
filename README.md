# ByteBrain Backend

ByteBrain Backend is a backend API written in TypeScript for ByteBrain — A personal “Second Brain” app built to help you capture, organize, and connect ideas, notes, and knowledge. With ByteBrain, you can easily revisit and build upon your thoughts to supercharge your learning, creativity, and productivity.

---

## Features

- **User authentication**: Secure signup and login with JWT
- **Personal brains**: Create, retrieve, update, and delete your digital brains (collections of notes/ideas)
- **Knowledge sharing**: Share brains with others and view shared ones
- **Self-service endpoint**: `/me` for user profile and personal data
- **RESTful API design**: Fast, scalable, and standards-compliant
- **MongoDB Integration**: Flexible and reliable data storage
- **Dockerized**: Easily deployable anywhere via Docker

---

## Tech Stack

- **Language:** TypeScript
- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB
- **ODM:** Mongoose
- **Authentication:** JWT
- **Environment Management:** dotenv
- **Deployment:** Docker

---

## Setup & Installation

### Clone and Install

```sh
git clone https://github.com/doomerdpk-1802/ByteBrain_Backend.git
cd ByteBrain_Backend
npm install
```

### Environment Variables

Copy `.env.example` to `.env` and set:

```env
MONGO_URI=<your-mongodb-uri>
JWT_SECRET=<your-jwt-secret>
PORT=3000
```

### Run Server

For development:
```sh
npm run dev
```

For production:
```sh
npm run start
```

---

## API Endpoints

| Endpoint                          | Method | Description                        |
|------------------------------------|--------|------------------------------------|
| `/api/v1/auth/signup`              | POST   | Register a new user                |
| `/api/v1/auth/login`               | POST   | User login                         |
| `/api/v1/content`                   | POST   | Create a new brain                 |
| `/api/v1/contents`                   | GET    | Get all brains for the user        |
| `/api/v1/update-content`               | PUT    | Update a brain by ID               |
| `/api/v1/delete-content`               | DELETE | Delete a brain by ID               |
| `/api/v1/me`                       | GET    | Get current user's profile         |
| `/api/v1/share`         | POST   | Share a brain with another user    |
| `/api/v1//brain/:hash`        | GET    | View a shared brain by ID          |

_Authentication is required for most endpoints. Use the JWT token in the Authorization header._

---

## Docker Usage

Build and run the backend in a Docker container:

```sh
docker build -t bytebrain-backend .
docker run --env-file .env -p 3000:3000 bytebrain-backend
```

Make sure MongoDB is accessible from your container. 
You can use Docker Compose for multi-container deployment (MongoDB + Backend).


_Thanks for exploring ByteBrain_Backend!_
