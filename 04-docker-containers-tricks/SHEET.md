# 🐳 Module 04: Docker & Compose Master Sheet (30 Commands)

Complete reference for 30 essential Docker container, image, volume, network, and compose commands categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner Commands (1 - 10)

```bash
# 1. List active running containers
docker ps

# 2. List all containers (including stopped ones)
docker ps -a

# 3. Pull image from Docker Hub
docker pull nginx:latest

# 4. List all downloaded Docker images
docker images

# 5. Run container from image in background detached mode (-d)
docker run -d -p 80:80 --name my_nginx nginx

# 6. Stop running container
docker stop my_nginx

# 7. Start stopped container
docker start my_nginx

# 8. Restart container
docker restart my_nginx

# 9. Remove stopped container
docker rm my_nginx

# 10. Remove local Docker image
docker rmi nginx
```

---

## 🟡 Level 2: Medium / Intermediate Commands (11 - 20)

```bash
# 11. Open interactive bash shell inside container
docker exec -it my_nginx bash

# 12. View real-time output logs of container
docker logs -f my_nginx

# 13. View resource utilization statistics of running containers (CPU/RAM)
docker stats

# 14. Build Docker image from Dockerfile in current directory
docker build -t my_app:1.0 .

# 15. Run container and remove automatically on exit (--rm)
docker run --rm -it ubuntu bash

# 16. Start Compose services stack in background detached mode
docker compose up -d

# 17. Rebuild and start Compose services
docker compose up -d --build

# 18. Stop and remove Compose containers, networks, and volumes
docker compose down

# 19. View logs of all services in Compose stack
docker compose logs -f

# 20. List services running in Compose stack
docker compose ps
```

---

## 🔴 Level 3: Hard / Advanced Pro Tricks (21 - 30)

```bash
# 21. Stop ALL running containers in one command
docker stop $(docker ps -q)

# 22. Remove ALL stopped containers in one command
docker rm $(docker ps -a -q)

# 23. Remove ALL dangling images without tags
docker rmi $(docker images -f "dangling=true" -q)

# 24. Deep system cleanup (Remove unused images, networks, volumes)
docker system prune -a --volumes -f

# 25. Inspect internal container IP address and network configuration
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my_nginx

# 26. Copy file from local machine into running container
docker cp ./config.json my_nginx:/etc/nginx/config.json

# 27. Copy file from container back to local host
docker cp my_nginx:/var/log/nginx/access.log ./access.log

# 28. Create named Docker volume for persistent data
docker volume create my_db_data

# 29. List all Docker volumes
docker volume ls

# 30. Create custom isolated Docker bridge network
docker network create my_custom_network
```
