# 🐳 Module 04: Docker Container Management (Easy to Hard)

Docker container and compose commands categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner Commands

```bash
# 1. List active running containers
docker ps

# 2. List all containers (including stopped ones)
docker ps -a

# 3. Stop a running container
docker stop container_id
```

---

## 🟡 Level 2: Medium / Intermediate Commands

```bash
# 1. Open interactive bash shell inside container
docker exec -it my_web_app bash

# 2. View real-time container logs
docker logs -f my_web_app

# 3. Start compose stack in background
docker compose up -d --build
```

---

## 🔴 Level 3: Hard / Advanced Pro Tricks

```bash
# 1. Stop ALL running containers in one line
docker stop $(docker ps -q)

# 2. Remove ALL stopped containers in one line
docker rm $(docker ps -a -q)

# 3. Deep system cleanup (Remove unused images, networks, volumes)
docker system prune -a --volumes -f

# 4. Inspect internal container IP address
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my_container
```
