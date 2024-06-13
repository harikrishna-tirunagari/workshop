**Exercise 2: Deploying a Pre-Packaged Application with Helm** (15 minutes)
   - **Objective:** Deploy an example application (e.g., WordPress) using Helm
   - **Steps:**
     - Search for the WordPress chart: `helm search repo wordpress`
     - Install the WordPress chart: 
       ```sh
       helm install my-wordpress stable/wordpress
       ```
     - Verify the installation: `helm list`
     - Get the WordPress URL: `kubectl get svc --namespace default my-wordpress -o jsonpath="{.status.loadBalancer.ingress[0].ip}"`
     - Open WordPress in the browser
   - **Discussion Points:**
     - What a Helm chart is
     - The structure of a Helm chart
     - How Helm simplifies Kubernetes deployments
