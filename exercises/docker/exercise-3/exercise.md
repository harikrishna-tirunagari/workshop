### Docker Workshop

#### **Exercises**

**Exercise 3: Docker Compose** (15 minutes)
   - **Objective:** Use Docker Compose to manage multi-container applications
   - **Steps:**
     - Create a `docker-compose.yml` file for a web application and a database:
       ```yaml
       version: '3'
       services:
         web:
           image: my-node-app
           ports:
             - "3000:3000"
         db:
           image: postgres
           environment:
             POSTGRES_USER: user
             POSTGRES_PASSWORD: password
             POSTGRES_DB: mydatabase
       ```
     - Start the application: `docker-compose up`
     - Access the web application in the browser
   - **Discussion Points:**
     - Introduction to Docker Compose
     - Managing multi-container applications
     - Docker networks and volumes
