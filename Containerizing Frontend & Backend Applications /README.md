Containerizer frontend & Backend Applications..
    Objective:   containerizer both frontend and backend applications using node.js environment, create Dockerfiles, connect to MongoDB (Atlas or container) , and verify full-stuck functionality.

Task/ checklist

1.backend  container.
   Create Dockerfiles.
      * Write a dockerfile for the backend.
      * Setup the node.js environment.
       * Copy the required project files into container.
 
Select Node.js Environment.
  * Chose a standard Node.js base image suitable for the Backend Applications.

Install Dependencies. 
   * Install all required backend dependencies inside the container.
    * Ensure the backend can run independently inside the container.
 
 Expose backend port.
   * Expose the backend port (e.g 3000).
   * Map the container port to a port accessible from your machine.
 
 database Connection..
   Connect the backend to MongoDB using either.
 * MongoDB Atlas _  cloud-hosted MongoDB database.
 * MongoDB container_  MongoDB running in a separate Docker container.
 
 Run and verify. 
   * Start the backend server inside the container.
   * Verify that the backend is accessible.
    * Verify that the backend successfully connected to MongoDB. 

2.frontend  container.
   Create Dockerfiles.
      * Write a dockerfile for the fronted.
      * Setup the node.js environment.
       * Copy the required project files into container.
 
Select Node.js Environment.
  * Chose a standard Node.js base image suitable for the frontend Applications..

Install Dependencies. 
   * Install all required fronted dependencies inside the container.
    * Ensure the frontend can run independently inside the container.
 
 Expose frontend port.
   * Expose the frontend port (e.g 3000).
   * Map the container port to a port accessible from your machine.
 
 Run and verify. 
   * Start the frontend server inside the container.
   * Verify that the frontend is accessible.
    * Verify that it communicates successfully with the backend.

3.MongoDB setup.( If using mongodb container) 
    
    Create mongoDB container.
   * Run MongoDB in a separate docker container.
   * Expose a MongoDB port( e.g 27017)
   * Create a docker volume to persist MongoDB Data. 
 
 Verify connection.
    * Ensure the backend container can connected to the MongoDB container.
   * Use the correct MongoDB hostname and port.
   * Verify that data can be stored and retrieved successfully.
 
4_ Expected Outcome.
    After complete this task, you should be able to: 
 * Run the backend applications inside a docker container.
 * Connect the backend to MongoDB atlas or a mongodb container.
 * Run the frontend Applications inside a docker container..
  * Establish communication between the frontend and backend containers.
 * Run MongoDB in a container with the persistent strong when required..
