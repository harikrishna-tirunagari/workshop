### Docker Workshop

#### **Exercises**

**Exercise 2: Building a Custom Docker Image** (10 minutes)
   - **Objective:** Create a Dockerfile and build an image
   - **Steps:**
     - Create a simple Node.js application (or any preferred language)
     - Write a `Dockerfile`:
       ```dockerfile
       FROM node:14
       WORKDIR /app
       COPY . .
       RUN npm install
       CMD ["node", "app.js"]
       ```
     - Build the image: `docker build -t my-node-app .`
     - Run the container: `docker run -p 3000:3000 my-node-app`
   - **Discussion Points:**
     - Explain each line of the Dockerfile
     - Building images and tagging
     - Port mapping
