# Practice 2 – Server Setup & Feature Branch Deployment

## 📌 Objective

The objective of this practice was to deploy my feature branch on a server environment, test the complete full-stack application, troubleshoot deployment issues, and follow a professional Git workflow.

---

## 🚀 What I Practiced

During this practice, I worked on deploying a full-stack application on an AWS EC2 server.

The main areas I practiced included:

* Setting up a server environment.
* Connecting to an AWS EC2 instance using SSH.
* Installing and verifying required dependencies.
* Cloning my feature branch into the server environment.
* Reviewing the frontend and backend project structure.
* Identifying application ports.
* Reviewing environment variables.
* Understanding the backend-to-database connection.
* Running the frontend, backend, and database services.
* Testing communication between application components.
* Troubleshooting deployment and environment issues.
* Following a feature branch workflow using Git and GitHub.

---

## 🖥️ Server Setup

I used an AWS EC2 instance as the server environment.

The server was prepared for application deployment by setting up the required tools and dependencies needed to run the full-stack application.

### Server Environment

* AWS EC2
* Ubuntu Linux
* SSH
* Git
* Docker
* Docker Compose
* Node.js
* npm

---

## 🌿 Feature Branch Deployment

The project was deployed from my feature branch rather than directly from the main branch.

This allowed development changes to remain isolated while testing the application in a server environment.

The workflow involved:

1. Connecting to the EC2 server using SSH.
2. Cloning the project repository.
3. Switching to my feature branch.
4. Reviewing the application configuration.
5. Starting the application services.
6. Testing the complete application.

---

## 🐳 Application Deployment

The full-stack application consisted of multiple services:

* Frontend
* Backend
* MongoDB Database

Docker and Docker Compose were used to build and run the services.

The services were configured to communicate with each other and run as containers.

---

## 🔌 Application Ports

The application services were configured to use the following ports:

| Service  | Port  |
| -------- | ----- |
| Frontend | 3000  |
| Backend  | 5000  |
| MongoDB  | 27017 |

---

## ⚙️ Environment Configuration

Before running the application, I reviewed the environment configuration.

The configuration included values for:

* Frontend port
* Backend port
* MongoDB port
* Database name
* Frontend URL
* Container image configuration

Environment variables allow application configuration to be managed separately from the application source code.

---

## 🔗 Application Communication

### Frontend → Backend

I tested whether the frontend could communicate correctly with the backend services.

### Backend → Database

I verified that the backend could connect to MongoDB and that the database connection was working correctly.

### End-to-End Testing

The complete application flow was tested to confirm that:

```text
User → Frontend → Backend → Database
```

All application services were running successfully.

---

## 🧪 Verification

The deployment was verified by checking:

* Docker container status.
* Frontend accessibility.
* Backend health status.
* Database connection.
* Full-stack communication.

The application containers were successfully started and verified on the server.

---

## 🔄 Git Workflow

The Git workflow followed during this practice was:

```text
feature/adnan-haneef
        ↓
       dev
        ↓
       stg
        ↓
      main
```

The workflow included:

1. Making changes in the feature branch.
2. Adding changes using Git.
3. Creating commits.
4. Pushing changes to GitHub.
5. Creating a Pull Request.
6. Reviewing and testing changes.
7. Merging the feature branch into the development branch.

---

## ⚠️ Challenges & Troubleshooting

During the server setup and deployment process, I encountered and worked through several challenges, including:

* Setting up the server environment.
* Installing missing dependencies.
* Understanding Docker and Docker Compose.
* Configuring environment variables.
* Managing application ports.
* Connecting multiple application services.
* Understanding Git branch deployment.
* Verifying frontend and backend communication.
* Troubleshooting server commands and deployment issues.

Working through these issues helped me better understand how a full-stack application is deployed and tested on a Linux server.

---

## 📚 Key Learnings

Through this practice, I learned about:

* AWS EC2 server setup.
* Connecting to a Linux server using SSH.
* Deploying an application from a feature branch.
* Docker containers.
* Docker Compose.
* Environment variables.
* Frontend, backend, and database architecture.
* Application ports and networking.
* Backend-to-database communication.
* End-to-end testing.
* Git feature branch workflows.
* Pull Requests.

---

## 🎯 Practice Outcome

This practice gave me hands-on experience deploying and testing a full-stack application on an AWS EC2 server.

It improved my understanding of how different components of an application work together in a real deployment environment:

**Git & GitHub → AWS EC2 → Linux → Docker → Frontend → Backend → MongoDB**

---

## 📸 Screenshots

Screenshots from the server setup, Docker deployment, application testing, and AWS EC2 environment are included in this practice.
