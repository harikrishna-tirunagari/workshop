**Exercise 4: Managing Helm Releases** (10 minutes)
   - **Objective:** Update and roll back Helm releases
   - **Steps:**
     - Update the `values.yaml` to change the replica count:
       ```yaml
       replicaCount: 3
       ```
     - Upgrade the release: `helm upgrade my-node-app ./my-node-app`
     - Verify the update: `kubectl get pods`
     - Roll back the release if needed: `helm rollback my-node-app <REVISION>`
   - **Discussion Points:**
     - Managing application updates with Helm
     - Rollback functionality
     - Best practices for versioning and updates
