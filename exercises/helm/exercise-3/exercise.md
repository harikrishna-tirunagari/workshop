**Exercise 3: Creating a Custom Helm Chart** (15 minutes)
   - **Objective:** Create and deploy a custom Helm chart for a simple application
   - **Steps:**
     - Create a new Helm chart: `helm create my-node-app`
     - Modify `values.yaml` to customize application values:
       ```yaml
       replicaCount: 2
       image:
         repository: node
         tag: "14"
       service:
         type: NodePort
         port: 80
       ```
     - Update the `templates/deployment.yaml` to match the Node.js application requirements:
       ```yaml
       apiVersion: apps/v1
       kind: Deployment
       metadata:
         name: {{ .Release.Name }}
       spec:
         replicas: {{ .Values.replicaCount }}
         selector:
           matchLabels:
             app: {{ .Release.Name }}
         template:
           metadata:
             labels:
               app: {{ .Release.Name }}
           spec:
             containers:
             - name: {{ .Chart.Name }}
               image: "{{ .Values.image.repository }}:{{ .Values.image.tag }}"
               ports:
               - containerPort: 3000
               command: ["node", "-e", "http.createServer((req, res) => res.end('Hello World')).listen(3000)"]
       ```
     - Install the custom chart:
       ```sh
       helm install my-node-app ./my-node-app
       ```
     - Verify the deployment: `helm list`
     - Access the application using Minikube: `minikube service my-node-app`
   - **Discussion Points:**
     - Customizing Helm charts
     - Understanding Helm template files
     - Deploying custom applications with Helm
