Helm Deployment: Custom Web Page on Kubernetes

📌 Project Overview
This project demonstrates how to deploy a custom HTML webpage on Kubernetes using Helm and Nginx.
By leveraging ConfigMaps, we replace the default Nginx page with our custom HTML file and ensure the correct configuration is applied.

🛠️ Tech Stack
✅ Kubernetes - Orchestrating the deployment
✅ Helm - Package management for Kubernetes
✅ Docker - Containerized Nginx server
✅ GitHub - Version control

📂 Project Structure
📁 my-repo/                    # Helm Chart Directory
 ├── 📁 templates/              # Helm Template Files
 │   ├── deployment.yaml        # Deployment definition for Nginx
 │   ├── configmap.yaml         # Stores index.html and nginx.conf
 │   ├── service.yaml           # Kubernetes Service definition
 ├── values.yaml                # Configurable Helm values
 ├── Chart.yaml                 # Helm chart metadata
 ├── README.md                  # Documentation
 
🚀 Setup & Deployment Steps
1️⃣ Prerequisites
Ensure you have the following installed:

Docker
Kubernetes (kubectl)
Kind (Kubernetes in Docker)
Helm

2️⃣ Create a Kind Cluster
Since we are using Kind instead of EKS, create a local Kubernetes cluster:

kind create cluster --name helm-cluster
Verify the cluster is running:

kubectl cluster-info
kubectl get nodes

3️⃣ Install the Helm Chart
First, navigate to the Helm project directory:

cd my-repo
Deploy the Helm chart:

helm upgrade --install my-repo .

✅ This deploys the Nginx server with a custom webpage.

Check if the pods are running:
kubectl get pods

4️⃣ Expose the Service
Since we are using NodePort, expose the service with:

kubectl port-forward svc/my-repo 8080:80
Now, visit:

http://127.0.0.1:8080

✅ You should see your custom webpage!

⚙️ Modifying the Web Page
To modify the webpage, update the configmap.yaml inside templates/, then reapply the Helm chart:

helm upgrade --install my-repo .
kubectl delete pod -l app=my-repo
