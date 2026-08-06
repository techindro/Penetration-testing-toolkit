# ☸️ Module 05: Kubernetes (`kubectl`) Master Sheet (30 Commands)

Complete reference for 30 essential Kubernetes `kubectl` commands categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner Commands (1 - 10)

```bash
# 1. Get list of pods in current namespace
kubectl get pods

# 2. Get list of services in current namespace
kubectl get svc

# 3. Get list of deployments
kubectl get deployments

# 4. View cluster nodes and their status
kubectl get nodes

# 5. Display detailed status and events of a pod
kubectl describe pod web-pod-name

# 6. Apply configuration YAML file
kubectl apply -f deployment.yaml

# 7. Delete resource defined in YAML file
kubectl delete -f deployment.yaml

# 8. Get cluster info and master endpoint
kubectl cluster-info

# 9. View current active kubectl context
kubectl config current-context

# 10. View all configured kubectl contexts
kubectl config get-contexts
```

---

## 🟡 Level 2: Medium / Intermediate Commands (11 - 20)

```bash
# 11. Get all running pods across ALL namespaces
kubectl get pods -A

# 12. View pod logs in real-time
kubectl logs -f web-pod-name

# 13. Port-forward local port 8080 to pod port 80
kubectl port-forward pod/web-pod-name 8080:80

# 14. Port-forward local port 8080 to service port 80
kubectl port-forward svc/web-service 8080:80

# 15. Execute interactive bash inside pod
kubectl exec -it web-pod-name -- /bin/bash

# 16. Scale deployment to 5 replicas
kubectl scale deployment/web-app --replicas=5

# 17. View resource utilization (CPU/Memory) of nodes
kubectl top nodes

# 18. View resource utilization (CPU/Memory) of pods
kubectl top pods

# 19. Set default namespace for current context
kubectl config set-context --current --namespace=production

# 20. Output pod definition as clean YAML
kubectl get pod web-pod-name -o yaml
```

---

## 🔴 Level 3: Hard / Advanced Pro Tricks (21 - 30)

```bash
# 21. View logs of previous crashed container instance (-p)
kubectl logs web-pod-name -p

# 22. View logs of specific container inside multi-container pod
kubectl logs web-pod-name -c container-name -f

# 23. Restart deployment gracefully without downtime
kubectl rollout restart deployment/web-app

# 24. View rollout status of deployment update
kubectl rollout status deployment/web-app

# 25. Rollback deployment to previous stable revision
kubectl rollout undo deployment/web-app

# 26. View revision history of deployment
kubectl rollout history deployment/web-app

# 27. Delete stuck pod forcefully without grace period delay
kubectl delete pod web-pod-name --grace-period=0 --force

# 28. Edit running deployment configuration live
kubectl edit deployment/web-app

# 29. Generate dry-run deployment YAML manifest without creating it
kubectl create deployment web-app --image=nginx --dry-run=client -o yaml > deployment.yaml

# 30. Run temporary interactive debugging pod in cluster
kubectl run tmp-shell --rm -i --tty --image=nicolaka/netshoot -- /bin/bash
```
