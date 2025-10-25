🧠 Kubernetes Basic Commands

This document provides a walkthrough of basic Kubernetes (kubectl) commands used to verify cluster configuration, deploy an application, expose it, scale it, and work with namespaces.

You can also refer to the following files for more details and visual guidance:

📄 Text Reference: Kubernet_Basic-Commands.txt — contains all commands listed below.

🖼️ Installation Reference (Images): Kubernet_Basic-Commands.pdf — includes screenshots and setup steps.

⚙️ Step 1: Check Kubernetes and Cluster Configuration
1️⃣ Check kubectl Version
kubectl version


Displays the version of both the client (kubectl) and server (Kubernetes cluster).
Useful to confirm connectivity and compatibility between them.

2️⃣ Get Available Contexts
kubectl config get-contexts


Shows all available contexts in your Kubernetes configuration.
Each context specifies a cluster, user, and namespace combination.

3️⃣ Switch to Docker Desktop Context
kubectl config use-context docker-desktop


Sets the current Kubernetes context to docker-desktop, which means all future commands will be executed on the Docker Desktop cluster.

4️⃣ List Clusters
kubectl config get-clusters


Displays all the clusters that are defined in your kubeconfig file.

5️⃣ Show Cluster Info
kubectl cluster-info


Displays endpoint details of the Kubernetes master and services running in the cluster.
Confirms that your cluster is active and reachable.

6️⃣ List Nodes
kubectl get nodes


Shows all nodes in your cluster.
Nodes are the machines (VMs or physical) where Kubernetes schedules and runs pods.

🚀 Step 2: Deploy and Expose an Application
7️⃣ Create an Nginx Deployment
kubectl create deployment nginx --image=nginx


Creates a new deployment named nginx using the nginx Docker image.
A deployment manages a set of identical pods (replicas) and ensures they stay running.

8️⃣ Expose Deployment as a Service
kubectl expose deployment nginx --type=LoadBalancer --port=80


Creates a service that exposes the nginx deployment externally on port 80.
The --type=LoadBalancer option allows external access (if your cluster supports it).

9️⃣ Check Running Pods
kubectl get pods


Lists all running pods in the current namespace.
Pods are the smallest deployable units in Kubernetes, containing one or more containers.

🔟 Check Active Services
kubectl get svc


Lists all services running in the current namespace, showing their type, cluster IP, external IP, and ports.

⚡ Step 3: Scale and Manage Resources
11️⃣ Scale the Deployment
kubectl scale deployment nginx --replicas=3


Scales the nginx deployment to 3 replicas.
This ensures three pods are running simultaneously for better load handling or redundancy.

12️⃣ Verify Scaled Services
kubectl get svc


Checks again to ensure the service and pods are properly scaled and still accessible.

🧩 Step 4: Work with Namespaces
13️⃣ Get All Namespaces
kubectl get ns


Lists all namespaces in your cluster.
Namespaces help organize and isolate resources in Kubernetes.

14️⃣ Create a Custom Namespace
kubectl create ns namespace-sachins218


Creates a new namespace named namespace-sachins218.
You can use this namespace to deploy isolated workloads.

15️⃣ Verify Namespace Creation
kubectl get ns


Confirms that the new namespace has been successfully created and is active.

16️⃣ Final Check of Services
kubectl get svc


Displays all services currently deployed.
Useful for confirming that everything is running as expected after scaling and namespace changes.

🧾 Reference Files

📘 Command Reference: Check all command descriptions in
➤ Kubernet_Basic-Commands.txt

🖼️ Installation & Visual Guide: For screenshots and step-by-step images, view
➤ Kubernet_Basic-Commands.pdf
