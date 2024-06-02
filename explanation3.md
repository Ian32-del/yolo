# Explanation of Kubernetes Implementation

## 1. Choice of Kubernetes Objects Used for Deployment

For this project, we used a combination of Deployments and StatefulSets:
- **Deployments** were used for the backend and frontend services. Deployments are ideal for stateless applications as they provide easy management of replicas, updates, and rollbacks.
- **StatefulSets** were used for the PostgreSQL database to ensure each replica has a unique, stable identity and persistent storage. This is crucial for stateful applications where data consistency and stability are necessary.

## 2. Method Used to Expose Pods to Internet Traffic

To expose our services to internet traffic, we used:
- **LoadBalancer** for the frontend service, which provides a stable external IP and load balances traffic across the replicas.
- **ClusterIP** for internal services like the backend and database, ensuring they are only accessible within the cluster for security and efficiency.

## 3. Use of Persistent Storage

For persistent storage, we implemented:
- **PersistentVolumeClaims (PVCs)** for the PostgreSQL database. PVCs ensure data persistence across pod restarts and node changes, which is essential for stateful services.
- **Ephemeral Storage** for the frontend and backend services, as they do not require data persistence beyond their lifecycle.

## 4. Git Workflow Used to Achieve the Task

Our Git workflow involved:
- **Feature Branch Workflow:** Developing each feature or fix in a separate branch and merging into the main branch after review.
- **Clear Commit Messages:** Using descriptive commit messages to effectively track changes.
- **Pull Requests:** Using pull requests to ensure code is reviewed and tested before merging.

## 5. Successful Running of the Applications

The application is successfully running and can be accessed at:
- [Live Application URL](http://localhost 80:80)

### Debugging Measures
- **Logs:** Checked using `kubectl logs` to identify and resolve issues.
- **Events:** Monitored using `kubectl get events` to troubleshoot scheduling and resource allocation problems.
- **Resource Adjustments:** Made adjustments to resource requests and limits to fit node capacities.

## 6. Good Practices for Docker Image Tag Naming Standards

We followed good practices for Docker image tagging:
- **Versioning:** Using semantic versioning (e.g., `v1.0.0`) to ensure clear and reproducible version tracking.
- **Descriptive Tags:** Including descriptive tags like `frontend:v1.0` and `backend:latest` for clarity and ease of identification.

This structured approach ensured the effective deployment and management of our Kubernetes applications.
