# Docker Cheat Sheet

### **Getting Started with Docker**

1. **Check Docker Installation**:
    
    ```bash
    docker --version
    
    ```
    

### **Basic Commands**

1. **Pull an Image from Docker Hub**:
    
    ```bash
    docker pull <image-name>
    
    ```
    
    Example:
    
    ```bash
    docker pull ubuntu
    
    ```
    
2. **List Available Images**:
    
    ```bash
    docker images
    
    ```
    
3. **Run a Container**:
    
    ```bash
    docker run -it <image-name>
    
    ```
    
    Example:
    
    ```bash
    docker run -it ubuntu
    
    ```
    
4. **Run a Container in Detached Mode**:
    
    ```bash
    docker run -d <image-name>
    
    ```
    
5. **Stop a Running Container**:
    
    ```bash
    docker stop <container-id>
    
    ```
    
6. **Start a Stopped Container**:
    
    ```bash
    docker start <container-id>
    
    ```
    
7. **Remove a Stopped Container**:
    
    ```bash
    docker rm <container-id>
    
    ```
    
8. **Remove an Image**:
    
    ```bash
    docker rmi <image-name>
    
    ```
    

### **Managing Containers**

1. **List Running Containers**:
    
    ```bash
    docker ps
    
    ```
    
2. **List All Containers (including stopped)**:
    
    ```bash
    docker ps -a
    
    ```
    
3. **View Container Logs**:
    
    ```bash
    docker logs <container-id>
    
    ```
    
4. **Execute a Command in a Running Container**:
    
    ```bash
    docker exec -it <container-id> <command>
    
    ```
    
    Example:
    
    ```bash
    docker exec -it <container-id> bash
    
    ```
    
5. **Inspect a Container**:
    
    ```bash
    docker inspect <container-id>
    
    ```
    

### **Networking**

1. **List Docker Networks**:
    
    ```bash
    docker network ls
    
    ```
    
2. **Create a New Network**:
    
    ```bash
    docker network create <network-name>
    
    ```
    
3. **Connect a Container to a Network**:
    
    ```bash
    docker network connect <network-name> <container-id>
    
    ```
    
4. **Disconnect a Container from a Network**:
    
    ```bash
    docker network disconnect <network-name> <container-id>
    
    ```
    

### **Volumes and Data Management**

1. **Create a Volume**:
    
    ```bash
    docker volume create <volume-name>
    
    ```
    
2. **List Volumes**:
    
    ```bash
    docker volume ls
    
    ```
    
3. **Remove a Volume**:
    
    ```bash
    docker volume rm <volume-name>
    
    ```
    
4. **Mount a Volume to a Container**:
    
    ```bash
    docker run -v <volume-name>:<container-path> <image-name>
    
    ```
    

### **Dockerfile and Building Images**

1. **Create a Dockerfile**:
Basic structure:
    
    ```
    FROM <base-image>
    MAINTAINER <your-name>
    COPY <source> <destination>
    RUN <command>
    CMD ["<executable>"]
    
    ```
    
2. **Build an Image from a Dockerfile**:
    
    ```bash
    docker build -t <image-name>:<tag> .
    
    ```
    
    Example:
    
    ```bash
    docker build -t myapp:latest .
    
    ```
    
3. **List Built Images**:
    
    ```bash
    docker images
    
    ```
    

### **Advanced Commands**

1. **Tag an Image**:
    
    ```bash
    docker tag <image-id> <new-image-name>:<tag>
    
    ```
    
2. **Push an Image to Docker Hub**:
    
    ```bash
    docker push <image-name>:<tag>
    
    ```
    
3. **Save an Image to a Tar File**:
    
    ```bash
    docker save -o <path-to-output-file> <image-name>
    
    ```
    
4. **Load an Image from a Tar File**:
    
    ```bash
    docker load -i <path-to-input-file>
    
    ```
    
5. **Docker Compose**:
    - **Start Services**:
        
        ```bash
        docker-compose up
        
        ```
        
    - **Stop Services**:
        
        ```bash
        docker-compose down
        
        ```
        
6. **Scale Services**:
    
    ```bash
    docker-compose up --scale <service-name>=<number>
    
    ```
    
7. **View Running Docker Compose Services**:
    
    ```bash
    docker-compose ps
    
    ```
    

### **Useful Docker Commands**

1. **Remove All Stopped Containers**:
    
    ```bash
    docker container prune
    
    ```
    
2. **Remove Unused Images**:
    
    ```bash
    docker image prune
    
    ```
    
3. **Remove All Unused Data (containers, networks, images)**:
    
    ```bash
    docker system prune
    
    ```
    
4. **Get Docker System Information**:
    
    ```bash
    docker info
    
    ```
    

---
