# 🐳 Module 04: Docker & Container Management Examples

One-liner commands for managing containers, inspecting volumes, executing terminal sessions, and performing system cleanups with practical examples.

---

## ⚡ 1. Container Administration Examples

```bash
# Example 1: Open interactive bash terminal inside a running container
docker exec -it my_web_app bash
# Usage: Opens bash terminal inside 'my_web_app' container to inspect files or run commands.

# Example 2: Stop ALL running containers simultaneously
docker stop $(docker ps -q)
# Usage: Instantly stops all active containers on your system.

# Example 3: Remove ALL stopped containers simultaneously
docker rm $(docker ps -a -q)
# Usage: Cleans up all exited container instances.

# Example 4: Remove ALL unused images, containers, networks, and volumes (Deep System Cleanup)
docker system prune -a --volumes -f
# Usage: Reclaims tens of gigabytes of disk space taken by dangling Docker build caches.

# Example 5: Inspect container IP address
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my_postgres_db
# Output: 172.17.0.2

# Example 6: View real-time container CPU, RAM, and network resource usage
docker stats
# Output: Live table showing CPU %, MEM USAGE / LIMIT, NET I/O for all containers.
```

---

## 🚀 2. Docker Compose Examples

```bash
# Example 1: Build and start services in background mode
docker compose up -d --build
# Usage: Builds images and launches web, db, and redis containers in background.

# Example 2: Stop and remove containers, networks, and attached volumes
docker compose down -v
# Usage: Shuts down compose stack and deletes volumes for a fresh database reset.

# Example 3: Follow real-time output logs for all compose services
docker compose logs -f web_service
# Usage: Streams live console logs specifically from 'web_service'.
```
