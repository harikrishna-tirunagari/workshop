### Kubernetes Workshop

#### **Exercises**

**Exercise 2: Exposing the Application** (15 minutes)
   - **Objective:** Expose the deployed application using a Service
   - **Steps:**
     - Create a Service YAML file (`service.yaml`):
       ```yaml
       apiVersion: v1
       kind: Service
       metadata:
         name: my-node-app-service
       spec:
         selector:
           app: my-node-app
         ports:
         - protocol: TCP
           port: 80
           targetPort: 3000
         type: NodePort
       ```
     - Create the service: `kubectl apply -f service.yaml`
     - Verify the service: `kubectl get services`
     - Get the service URL: `minikube service my-node-app-service --url`
   - **Discussion Points:**
     - What a Service is and types of services (ClusterIP, NodePort, LoadBalancer)
     - Exposing applications to the outside world
     - Accessing services
