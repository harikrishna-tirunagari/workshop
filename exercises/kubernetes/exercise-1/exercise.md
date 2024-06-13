### Kubernetes Workshop

#### **Exercises**

**Exercise 1: Deploying a Simple Application** (15 minutes)
   - **Objective:** Deploy a simple Node.js application to Kubernetes
   - **Steps:**
     - Create a Deployment YAML file (`deployment.yaml`):
       ```yaml
       apiVersion: apps/v1
       kind: Deployment
       metadata:
         name: my-node-app
       spec:
         replicas: 2
         selector:
           matchLabels:
             app: my-node-app
         template:
           metadata:
             labels:
               app: my-node-app
           spec:
             containers:
             - name: my-node-app
               image: node:14
               command: ["node", "-e", "http.createServer((req, res) => res.end('Hello World')).listen(3000)"]
               ports:
               - containerPort: 3000
       ```
     - Create the deployment: `kubectl apply -f deployment.yaml`
     - Verify the deployment: `kubectl get deployments`
     - Describe the deployment: `kubectl describe deployment my-node-app`
   - **Discussion Points:**
     - What a Deployment is
     - YAML structure and key fields
     - Creating and managing deployments
