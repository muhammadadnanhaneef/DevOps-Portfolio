# Docker Volume, Network & Container Setup

## 📌 Objective

The objective of this practice was to learn how to create and use Docker volumes for persistent data storage and Docker networks for container-to-container communication.

The full-stack application was run and tested using frontend, backend, and database containers.

---

## 🚀 What I Practiced

During this practice, I worked on:

* Creating a Docker volume for persistent database storage.
* Attaching the volume to the database container.
* Creating a Docker network.
* Connecting frontend, backend, and database containers to the same network.
* Configuring containers to communicate using service/container names.
* Running the complete full-stack application.
* Testing frontend-to-backend communication.
* Testing backend-to-database communication.
* Verifying database data persistence.
* Troubleshooting Docker-related issues.
* Following Git feature branch and Pull Request workflow.
* Documenting practical work and progress.

---

# 1. Docker Volume

A Docker volume was created to provide persistent storage for the database container.

Example:

```bash
docker volume create appointy-data
```

The volume was attached to the database container so that database data could survive container restarts or removal.

### Why use a Docker Volume?

Containers are temporary by nature. If a database container is removed without persistent storage, its data can be lost.

A Docker volume stores the database data outside the container lifecycle.

The concept is:

```text
Database Container
        │
        ↓
   Docker Volume
        │
        ↓
 Persistent Data
```

---

# 2. Docker Network

A custom Docker network was created to allow the application containers to communicate with each other.

Example:

```bash
docker network create appointy-network
```

The following containers were connected to the network:

* Frontend
* Backend
* MongoDB

The architecture was:

```text
┌─────────────────┐
│    Frontend     │
└────────┬────────┘
         │
         ↓
   Docker Network
         │
    ┌────┴────┐
    ↓         ↓
 Backend    MongoDB
              │
              ↓
        Docker Volume
```

---

# 3. Container Communication

The containers were configured to communicate through the Docker network.

Instead of using `localhost` to communicate between containers, the appropriate container/service name was used as the hostname.

For example:

```text
Backend → MongoDB
```

The backend could communicate with the MongoDB container through the Docker network using the MongoDB service/container name and port.

---

# 4. Full-Stack Containers

The application was run using three main containers:

| Container | Purpose                |
| --------- | ---------------------- |
| Frontend  | User interface         |
| Backend   | Application/API server |
| MongoDB   | Database               |

All required containers were connected to the same Docker network.

The database container also used the Docker volume for persistent storage.

---

# 5. Port Configuration

The required application ports were configured so that the services could be accessed and tested.

Example:

| Service  |  Port |
| -------- | ----: |
| Frontend |  3000 |
| Backend  |  5000 |
| MongoDB  | 27017 |

Port mapping allowed services running inside containers to be accessed from the host machine where required.

---

# 6. Running & Verifying Containers

The running containers were checked using:

```bash
docker ps
```

Docker network information was checked using:

```bash
docker network inspect appointy-network
```

The Docker volume was checked using:

```bash
docker volume inspect appointy-data
```

These commands helped verify that the required containers, network, and persistent storage were configured correctly.

---

# 7. Testing Container Functionality

The complete application flow was tested.

## Frontend → Backend

The frontend was tested to verify that it could communicate with the backend API.

```text
Frontend
   ↓
Backend API
```

## Backend → Database

The backend was tested to verify that it could connect to MongoDB and interact with the database.

```text
Backend
   ↓
MongoDB
```

## Database → Volume

The database container was restarted/removed and the persistent storage configuration was verified.

```text
MongoDB Container
       ↓
 Docker Volume
       ↓
Persistent Database Data
```

---

# 8. End-to-End Application Flow

The complete application architecture was:

```text
                 User
                  │
                  ↓
          ┌───────────────┐
          │    Frontend   │
          │    Container  │
          └───────┬───────┘
                  │
                  ↓
          ┌───────────────┐
          │    Backend    │
          │    Container  │
          └───────┬───────┘
                  │
                  ↓
          ┌───────────────┐
          │    MongoDB    │
          │    Container  │
          └───────┬───────┘
                  │
                  ↓
          ┌───────────────┐
          │ Docker Volume │
          │  Persistent   │
          │     Data      │
          └───────────────┘
```

---

# 9. Troubleshooting & Documentation

During this practice, I worked through Docker configuration and connectivity issues while setting up the containers.

The troubleshooting process included:

### Issue

Container communication or configuration issues could prevent the frontend, backend, and database from communicating correctly.

### Root Cause

Possible causes included:

* Incorrect container names.
* Incorrect ports.
* Containers not connected to the same network.
* Incorrect database connection configuration.
* Incorrect volume configuration.

### Solution

The configuration was reviewed and corrected by:

* Checking running containers.
* Inspecting the Docker network.
* Verifying container names.
* Checking exposed and mapped ports.
* Reviewing database connection settings.
* Verifying the Docker volume.
* Restarting containers after configuration changes.

This process improved my understanding of Docker networking, persistent storage, and container troubleshooting.

---

# 10. Git Workflow / Pull Request

The required changes were managed using a feature branch.

The workflow followed wa
