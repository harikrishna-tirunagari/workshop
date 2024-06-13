### Kubernetes Workshop

#### **Exercises**

**Exercise 5: HDP Server** (15 minutes)
   - **Objective:** Run a HDP Server in Kubernetes
   - **Steps:**
     - Create a Deployment YAML file (`deployment.yaml`):
          ```yaml
          apiVersion: apps/v1
          kind: Deployment
          metadata:
            name: hdp
          spec:
            selector:
              matchLabels:
                hdp: workshop
            template:
              metadata:
                labels:
                  hdp: workshop
              spec:
                containers:
                  - name: hdp-server
                    image: hdp-docker-4.6.1:2057
                    ports:
                      - name: hdp-server-port
                        containerPort: 8080
                    env:
                      - name: ACCEPT_EULA
                        value: "true"
                      - name: HDP_EVAL
                        value: "true"
                      - name: HDP_ADMIN_PASSWORD
                        value: "d2cadmin"
                      - name: HDP_USER_PASSWORD
                        value: "d2cuser"
                    volumeMounts:
                      - name: hdpshare
                        mountPath: /hdpshare
                volumes:
                  - name: hdpshare
                    hostPath:
                      path: /run/desktop/mnt/host/c/docker/hdpshare
       ```
     - Create a Service YAML file (`service.yaml`):
          ```yaml
          apiVersion: v1
          kind: Service
          metadata:
            name: hdp-access
          spec:
            type: NodePort
            selector:
              hdp: workshop
            ports:
            - name: hdp-server-port
              port: 8080
              targetPort: 8080
              nodePort: 31080
       ```
   - **Discussion Points:**
     - Explain the output
     - More details on the deployment and service objects