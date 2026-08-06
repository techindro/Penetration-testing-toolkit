# 🐳 Module 04: Docker & Container Shortcut Tricks

One-liner commands for starting containers, entering container terminals, and performing complete system cleanups.

---

## ⚡ 1. Container Management Tricks

```bash
# Enter interactive bash terminal inside running container
docker exec -it <container_name_or_id> bash

# Stop ALL running containers in one line
docker stop $(docker ps -q)

# Remove ALL stopped containers
docker rm $(docker ps -a -q)

# Remove ALL unused images, networks, and stopped containers (Deep Cleanup)
docker system prune -a --volumes -f
```

---

## 🚀 2. Docker Compose Shortcuts

```bash
# Build and run containers in background mode (-d)
docker compose up -d --build

# Stop and remove containers, networks, and volumes
docker compose down -v

# View real-time logs for all services
docker compose logs -f
```
