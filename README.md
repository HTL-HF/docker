Here's a well-structured README that explains how to run the project using both Docker and Node.js, with clear instructions and styled sections for a professional look:

---

# ATMORS

This project is a full-stack application written in TypeScript using MongoDB, Node.js, Express (backend), React (frontend), and an Nginx reverse proxy. It can be run using Docker Compose or manually via Node.js.

---

## 📝 Table of Contents
- [Prerequisites](#prerequisites)
- [Running the Project with Docker](#docker-setup)
- [Running the Project with Node.js](#manual-nodejs-setup)
- [Environment Variables](#environment-variables)
- [Folder Structure](#folder-structure)
- [Usage](#usage)

---

## ⚙️ Prerequisites

Before you can run this project, ensure you have the following installed:

### For Docker Setup:
- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

### For Node.js Setup:
- [Node.js](https://nodejs.org/en/) (version 18+ recommended)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)

---

## 🚢 Docker Setup

Docker makes it easy to run the application with just a few commands. This setup includes MongoDB, the backend, the frontend, and an Nginx reverse proxy.

### Steps:

1. **Clone the repository:**
    ```bash
    git clone https://github.com/HTL-HF/docker.git
    cd docker
    ```

2. **Set up environment variables:**
   Create a `.env` file in the root directory and fill it with the required variables (see [Environment Variables](#environment-variables) section).

3. **Build and run the containers:**
    ```bash
    docker-compose up --build
    ```

4. **Access the app:**
    - Frontend: [http://localhost](http://localhost)
    - Backend (API): [http://localhost/api](http://localhost/api)

### Stopping the containers:

To stop the running containers, press `Ctrl + C` or run:
```bash
docker-compose down
```

---

## 🖥️ Manual Node.js Setup

If you prefer to run the app without Docker, follow the steps below to set up the backend, frontend, and MongoDB individually.

### Steps:

1. **Clone the repository:**
    ```bash
    git clone https://github.com/your-repo/fullstack-nginx-docker.git
    cd fullstack-nginx-docker
    ```

2. **Install MongoDB**:
   - Install [MongoDB](https://www.mongodb.com/try/download/community) locally or use a cloud solution like [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).

3. **Set up environment variables**:
   - Create a `.env` file in both `backend` and `frontend` folders. See [Environment Variables](#environment-variables) for required settings.

4. **Backend Setup**:

   Navigate to the backend folder:
   ```bash
   cd backend
   ```

   Install dependencies:
   ```bash
   npm install
   ```

   Run the backend:
   ```bash
   npm run dev
   ```

5. **Frontend Setup**:

   Navigate to the frontend folder:
   ```bash
   cd ../frontend
   ```

   Install dependencies:
   ```bash
   npm install
   ```

   Run the frontend:
   ```bash
   npm run dev
   ```

6. **Access the app**:
    - Frontend: [http://localhost:3000](http://localhost:3000)
    - Backend (API): [http://localhost:5173](http://localhost:5173)

---

## 🔧 Environment Variables

To ensure the services communicate properly, you need to set up the following environment variables:

### Backend `.env`
```env
DB_USERNAME_ARG=yourMongoUsername
DB_PASSWORD_ARG=yourMongoPassword
DB_NAME_ARG=yourDatabaseName
JWT_SECRET_KEY_ARG=yourJWTSecret
BACKEND_PORT_ARG=4000
FRONTEND_IP_ARG=frontend
FRONTEND_PORT_ARG=3000
```

### Frontend `.env`
```env
REACT_APP_BACKEND_IP=http://localhost
REACT_APP_BACKEND_PORT=4000
```

### Docker `.env`
For Docker Compose, create a root `.env` file:
```env
DB_USERNAME=yourMongoUsername
DB_PASSWORD=yourMongoPassword
DB_NAME=yourDatabaseName
JWT_SECRET_KEY=yourJWTSecret
BACKEND_PORT=4000
FRONTEND_PORT=3000
```

---

## 🗂️ Folder Structure

```
.
├── backend
│   ├── src
│   ├── Dockerfile
│   └── package.json
├── frontend
│   ├── src
│   ├── Dockerfile
│   └── package.json
├── nginx
│   └── nginx.conf.template
├── docker-compose.yml
└── README.md
```

- **backend/**: Contains the Node.js backend code.
- **frontend/**: Contains the React frontend code.
- **nginx/**: Contains the Nginx configuration file.
- **docker-compose.yml**: Defines the Docker services.
  
---

## 📚 Usage

Once everything is up and running:

- The frontend will be served at [http://localhost](http://localhost).
- The backend API will be available at [http://localhost/api](http://localhost/api).
  
Feel free to explore the app, add new features, or modify the existing ones!

---

## ✨ Features

- **Dockerized Full-Stack App**: Easily run the entire stack with Docker.
- **Nginx Reverse Proxy**: Seamlessly route traffic between the frontend and backend.
- **MongoDB**: Used for database management with secure user credentials.
- **JWT Authentication**: Secured API with JWT-based authentication.

---

## 🤝 Contributing

Feel free to fork this project and submit pull requests.

---

## 🛠️ License

This project is licensed under the MIT License.

---
