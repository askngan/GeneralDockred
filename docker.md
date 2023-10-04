Having diagnostic and troubleshooting commands at your disposal is essential for ensuring the smooth operation of Docker in a standalone setup. Below are some commands you might find useful:

### 1. **Docker Version and Info:**
   - To check the Docker version:
     ```bash
     docker --version
     ```
   - To get a lot of system-wide information regarding Docker:
     ```bash
     docker info
     ```

### 2. **Container Inspection:**
   - To list all running containers:
     ```bash
     docker ps
     ```
   - To list all containers (running and stopped):
     ```bash
     docker ps -a
     ```
   - To inspect a particular container:
     ```bash
     docker inspect <container_id_or_name>
     ```

### 3. **Docker Configuration:**
   - To view the Docker daemon configuration:
     ```bash
     cat /etc/docker/daemon.json
     ```

### 4. **Container Logs:**
   - To view the logs for a specific container:
     ```bash
     docker logs <container_id_or_name>
     ```

### 5. **Docker Health Check:**
   - If you have health checks configured for your containers, you can view their status with:
     ```bash
     docker inspect --format='{{.State.Health.Status}}' <container_id_or_name>
     ```

### 6. **Network Inspection:**
   - To list all networks:
     ```bash
     docker network ls
     ```
   - To inspect a particular network:
     ```bash
     docker network inspect <network_id_or_name>
     ```

### 7. **Image Inspection:**
   - To list all images:
     ```bash
     docker images
     ```
   - To inspect a particular image:
     ```bash
     docker inspect <image_id_or_name>
     ```

### 8. **System Resource Usage:**
   - To view real-time events from the server:
     ```bash
     docker events
     ```
   - To display system-wide resource usage:
     ```bash
     docker stats
     ```

### 9. **Volume Inspection:**
   - To list all volumes:
     ```bash
     docker volume ls
     ```
   - To inspect a particular volume:
     ```bash
     docker volume inspect <volume_name>
     ```

### 10. **Troubleshooting:**
   - If you encounter issues, you can increase the log level for the Docker daemon (note: this requires restarting the Docker daemon):
     ```bash
     echo '{"debug": true}' | sudo tee /etc/docker/daemon.json
     sudo systemctl restart docker
     ```
```bash
docker ps -a --format "{{.ID}}" | xargs docker logs
```
```bash
for id in $(docker ps -a --format "{{.ID}}"); do
            docker logs $id
  done
```



These commands should provide a good starting point for diagnosing issues and gathering configuration information from your Docker standalone setup.
