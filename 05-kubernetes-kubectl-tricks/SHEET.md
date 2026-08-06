# ☸️ Module 05: Kubernetes (`kubectl`) Comprehensive Examples

Essential `kubectl` one-liners with practical examples for pod debugging, deployments, logs, and namespace management.

---

## ⚡ 1. Pod & Node Inspection Examples

```bash
# Example 1: Get all running pods across ALL namespaces
kubectl get pods -A
# Output: Lists all pods running in default, kube-system, and custom namespaces.

# Example 2: Get detailed information and events for a specific pod
kubectl describe pod web-api-7945d8b7c-x9k2z -n production
# Usage: Shows container status, restart count, and deployment warning events.

# Example 3: View real-time logs for a pod
kubectl logs -f web-api-7945d8b7c-x9k2z -n production
# Usage: Follows live log output to debug application crashes.

# Example 4: View logs for a previous crashed container instance inside a pod (-p)
kubectl logs web-api-7945d8b7c-x9k2z -n production -p
# Usage: Inspects stdout of the container right before it crashed (OOMKilled / Panic).

# Example 5: Open interactive bash shell inside a running Kubernetes container
kubectl exec -it web-api-7945d8b7c-x9k2z -n production -- /bin/bash
# Usage: Enters pod environment to test environment variables or database connectivity.
```

---

## 🚀 2. Cluster Deployment & Port Forwarding Examples

```bash
# Example 1: Forward local port 8080 to pod port 80
kubectl port-forward pod/web-api-7945d8b7c-x9k2z 8080:80
# Usage: Open http://localhost:8080 in your local browser to test pod directly!

# Example 2: Restart a deployment gracefully without downtime
kubectl rollout restart deployment/web-api -n production
# Usage: Triggers a rolling update to reload config maps or updated container images.

# Example 3: Rollback deployment to previous working revision
kubectl rollout undo deployment/web-api -n production
# Usage: Instantly reverts bad deployment back to previous stable build.

# Example 4: Set current default namespace (Saves typing -n <namespace> every time!)
kubectl config set-context --current --namespace=production
# Usage: All subsequent 'kubectl get pods' commands automatically query 'production'.

# Example 5: Delete stuck pod forcefully without delay
kubectl delete pod web-api-7945d8b7c-x9k2z --grace-period=0 --force
# Usage: Instantly terminates stuck Terminating pods.
```
