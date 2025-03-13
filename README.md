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
perl
Copy
Edit
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
