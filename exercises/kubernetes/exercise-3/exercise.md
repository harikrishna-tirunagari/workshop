### Kubernetes Workshop

#### **Exercises**

**Exercise 3: Scaling the Application** (10 minutes)
   - **Objective:** Scale the application to handle more load
   - **Steps:**
     - Scale the deployment: `kubectl scale deployment my-node-app --replicas=4`
     - Verify the scaling: `kubectl get deployments`
     - Check the pods: `kubectl get pods`
   - **Discussion Points:**
     - Importance of scaling
     - Horizontal scaling in Kubernetes
     - Managing replicas
