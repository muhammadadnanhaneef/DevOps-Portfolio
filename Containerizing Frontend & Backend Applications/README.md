## Containerizing Frontend & Backend Applications

## 📌 Objective

The objective of this practice was to containerize both the frontend and backend applications using Docker and Node.js, connect the backend with MongoDB, and verify the complete full-stack application.

---

## 🚀 What I Practiced

During this practice, I worked on:

* Creating Dockerfiles for the backend and frontend.
* Selecting suitable Node.js base images.
* Installing application dependencies inside Docker containers.
* Running frontend and backend applications independently in containers.
* Configuring the backend to connect with MongoDB.
* Running MongoDB as a separate Docker container.
* Creating a Docker volume for MongoDB data persistence.
* Creating a Docker network for communication between containers.
* Mapping container ports to accessible host ports.
* Starting and verifying all application services.
* Testing frontend → backend → database communication.

---

## 🏗️ Application Architecture

The application was organized into three main services:

```text
┌─────────────────┐
│    Frontend     │
│  React / Node   │
│    Port 3000    │
└────────┬────────┘
         │
         │ HTTP Requests
         ↓
┌─────────────────┐
│     Backend     │
│   Node.js API   │
│    Port 5000    │
└────────┬────────┘
         │
         │ MongoDB Connection
         ↓
┌─────────────────┐
│     MongoDB     │
│    Port 27017   │
└─────────────────┘
         │
         ↓
   Docker Volume
```

---

# 1. Backend Container

## 🐳 Dockerfile

A Dockerfile was created for the backend application.

The Dockerfile was responsible for:

* Selecting a Node.js base image.
* Creating the application working directory.
* Copying package files.
* Installing backend dependencies.
* Copying the application source code.
* Exposing the backend port.
* Starting the backend application.

Example structure:

```dockerfile
FROM node:20-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 5000

CMD ["npm", "start"]
```

---

## 📦 Backend Dependencies

The required backend dependencies were installed inside the Docker container using npm.

This allowed the backend application to run independently from the host environment.

---

## 🔌 Backend Port

The backend application was configured to listen on:

```text
5000
```

The container port was mapped to the host so that the backend API could be accessed and tested.

---

# 2. MongoDB Setup

MongoDB was configured as a separate Docker container.

The MongoDB container used:

```text
Port: 27017
```

A Docker volume was created to provide persistent storage for MongoDB data.

### Why use a volume?

Without a volume, database data can be lost when the MongoDB container is removed.

A Docker volume allows the database data to remain available independently of the container lifecycle.

---

## 🔗 Backend → MongoDB

The backend was configured to connect to MongoDB through the Docker network.

Instead of relying on `localhost` inside the backend container, the MongoDB container/service hostname was used for communication between containers.

The connection flow was:

```text
Backend Container
       ↓
Docker Network
       ↓
MongoDB Container
       ↓
Docker Volume
```

---

# 3. Frontend Container

A separate Dockerfile was created for the frontend application.

The frontend Dockerfile was responsible for:

* Selecting a Node.js base image.
* Creating the working directory.
* Copying package files.
* Installing frontend dependencies.
* Copying the application source code.
* Exposing the frontend port.
* Starting the frontend application.

Example:

```dockerfile
FROM node:20-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "run", "dev", "--", "--host"]
```

---

## 🔌 Frontend Port

The frontend was configured to run on:

```text
3000
```

The container port was mapped to the host machine so that the application could be opened in a web browser.

---

# 4. Docker Network

A Docker network was used to allow the application containers to communicate with each other.

The network connected:

```text
Frontend
   │
   ├──────── Backend
   │             │
   │             ↓
   └──────── MongoDB
```

This allowed the backend to communicate with MongoDB using the appropriate Docker hostname and port.

---

# 5. Running the Containers

The containers were built and started using Docker commands / Docker Compose.

The running services were verified using:

```bash
docker ps
```

The expected services were:

```text
Frontend
Backend
MongoDB
```

---

# 6. Full-Stack Verification

After starting the containers, the complete application flow was tested.

### Frontend → Backend

The frontend was tested to verify that it could communicate with the backend APIs.

### Backend → MongoDB

The backend was tested to verify that it could connect to MongoDB and interact with the database.

### End-to-End

The complete flow was verified:

```text
User
 ↓
Frontend Container
 ↓
Backend Container
 ↓
MongoDB Container
 ↓
Docker Volume
```

This confirmed that the different components of the application could work together inside the Docker environment.

---

# 🧪 Verification Checklist

| Component              | Status       |
| ---------------------- | ------------ |
| Backend Dockerfile     | ✅ Completed  |
| Backend container      | ✅ Completed  |
| Backend dependencies   | ✅ Installed  |
| Frontend Dockerfile    | ✅ Completed  |
| Frontend container     | ✅ Completed  |
| Frontend dependencies  | ✅ Installed  |
| MongoDB container      | ✅ Configured |
| Docker volume          | ✅ Configured |
| Docker network         | ✅ Configured |
| Frontend → Backend     | ✅ Tested     |
| Backend → MongoDB      | ✅ Tested     |
| Full-stack application | ✅ Verified   |

---

# ⚠️ Challenges & Troubleshooting

During this practice, I worked through several Docker and server-related challenges, including:

* Setting up Docker on the server.
* Starting and managing Docker containers.
* Creating Dockerfiles for different application components.
* Understanding container ports and port mapping.
* Configuring communication between containers.
* Understanding Docker networks.
* Connecting the backend to MongoDB.
* Understanding persistent database storage using Docker volumes.
* Verifying application services and container status.

Troubleshooting these issues helped me understand how containerized applications communicate and operate together.

---

# 📚 Key Learnings

Through this practice, I learned:

* Dockerfile fundamentals.
* Node.js application containerization.
* Docker image and container concepts.
* Installing dependencies inside containers.
* Docker port mapping.
* Docker networks.
* Container-to-container communication.
* MongoDB containerization.
* Docker volumes and data persistence.
* Frontend and backend container communication.
* Full-stack application verification.

---

# 🎯 Practice Outcome

After completing this practice, I gained hands-on experience with containerizing a full-stack application.

The final architecture consisted of:

**Frontend Container → Backend Container → MongoDB Container**

with persistent MongoDB storage through a Docker volume.

This practice strengthened my understanding of Docker-based application deployment and container networking.
