# 🐳 Module 04: Docker & Container Management Shortcuts

One-liner commands for managing containers, inspecting volumes, executing terminal sessions, and performing system cleanups.

---

## ⚡ 1. Container Administration One-Liners

```bash
# Open interactive bash terminal inside a running container
docker exec -it <container_name_or_id> bash

# Stop ALL running containers simultaneously
docker stop $(docker ps -q)

# Remove ALL stopped containers simultaneously
docker rm $(docker ps -a -q)

# Remove ALL unused images, containers, networks, and volumes (Deep System Cleanup)
docker system prune -a --volumes -f

# Inspect container IP address and network details
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container_id>

# View real-time container CPU, RAM, and network resource usage
docker stats
```

---

## 🚀 2. Docker Compose Shortcuts

```bash
# Build and start services in background mode
docker compose up -d --build

# Stop and remove containers, networks, and attached volumes
docker compose down -v

# Follow real-time output logs for all compose services
docker compose logs -f

# Restart a specific service inside compose setup
docker compose restart <service_name>
```
