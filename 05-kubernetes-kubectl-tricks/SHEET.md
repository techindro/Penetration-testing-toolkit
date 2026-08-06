# ☸️ Module 05: Kubernetes (`kubectl`) Comprehensive Shortcuts

Essential `kubectl` one-liners for cluster management, Pod debugging, deployments, service logs, and namespace switching.

---

## ⚡ 1. Pod & Node Inspection Shortcuts

```bash
# Get all running pods across ALL namespaces
kubectl get pods -A

# Get detailed information and events for a specific pod
kubectl describe pod <pod_name> -n <namespace>

# View real-time logs for a pod
kubectl logs -f <pod_name> -n <namespace>

# View logs for a previous crashed container instance inside a pod (-p)
kubectl logs <pod_name> -n <namespace> -p

# Open interactive bash shell inside a running Kubernetes container
kubectl exec -it <pod_name> -n <namespace> -- /bin/bash
```

---

## 🚀 2. Cluster Deployment & Port Forwarding

```bash
# Forward local port 8080 to pod port 80 (Access pod directly on localhost)
kubectl port-forward pod/<pod_name> 8080:80

# Restart a deployment gracefully without downtime
kubectl rollout restart deployment/<deployment_name> -n <namespace>

# Rollback deployment to previous revision
kubectl rollout undo deployment/<deployment_name> -n <namespace>

# Set current working default namespace (Saves typing -n <namespace> every time!)
kubectl config set-context --current --namespace=<namespace>

# Delete stuck pod forcefully without delay
kubectl delete pod <pod_name> --grace-period=0 --force
```
