# ☸️ Module 05: Kubernetes (`kubectl`) Commands (Easy to Hard)

Kubernetes `kubectl` commands categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner Commands

```bash
# 1. Get list of pods in current namespace
kubectl get pods

# 2. Get list of services
kubectl get svc

# 3. View cluster nodes
kubectl get nodes
```

---

## 🟡 Level 2: Medium / Intermediate Commands

```bash
# 1. Get all running pods across ALL namespaces
kubectl get pods -A

# 2. View pod logs in real-time
kubectl logs -f web-pod-name

# 3. Port-forward local port 8080 to pod port 80
kubectl port-forward pod/web-pod-name 8080:80
```

---

## 🔴 Level 3: Hard / Advanced Pro Tricks

```bash
# 1. View logs of previous crashed container instance (-p)
kubectl logs web-pod-name -p

# 2. Execute interactive bash inside pod
kubectl exec -it web-pod-name -- /bin/bash

# 3. Restart deployment gracefully without downtime
kubectl rollout restart deployment/web-app

# 4. Rollback deployment to previous stable build
kubectl rollout undo deployment/web-app

# 5. Delete stuck pod forcefully without delay
kubectl delete pod web-pod-name --grace-period=0 --force
```
