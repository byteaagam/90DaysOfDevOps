# Week 5: Docker Basics & Advanced Challenge

Welcome to the Week 5 Docker Challenge! In this task, you will work with Docker concepts and tools . This challenge covers the following topics:

- **Introduction and Purpose:** Understand Docker’s role in modern development.
- **Virtualization vs. Containerization:** Learn the differences and benefits.
- **Build Kya Hota Hai:** Understand the Docker build process.
- **Docker Terminologies:** Get familiar with key Docker terms.
- **Docker Components:** Explore Docker Engine, images, containers, and more.
- **Project Building Using Docker:** Containerize a sample project.
- **Multi-stage Docker Builds / Distroless Images:** Optimize your images.
- **Docker Hub (Push/Tag/Pull):** Manage and distribute your Docker images.
- **Docker Volumes:** Persist data across container runs.
- **Docker Networking:** Connect containers using networks.
- **Docker Compose:** Orchestrate multi-container applications.
- **Docker Scout:** Analyze your images for vulnerabilities and insights.



---

## Challenge Tasks

### 🧠Task 1: Introduction and Conceptual Understanding
1. **What is Docker?**  
   - Docker is a containerization platform that allows developers to package applications along with their dependencies into lightweight, portable containers.
   - It ensures that applications run consistently across different environments such as development, testing, and production.
     
    <img width="1238" height="662" alt="image" src="https://github.com/user-attachments/assets/e6b3bd63-f7ef-48d0-b468-83054f569efa" />

⚡ Why Containerization is Preferred?

- Containerization is widely used in modern DevOps because:

- Lightweight & Fast → Containers start in seconds

- Consistency → Same behavior across environments

- Scalability → Easy to scale microservices

- Efficient Resource Usage → No need for full OS per app

CI/CD Friendly → Faster builds and deployments

---

### Task 2: Create a Dockerfile for a Sample Project

1. **Select or Create a Sample Application:**
     
  - This application presents random quotes 

2. **Write a Dockerfile:**
   
   <img width="690" height="704" alt="image" src="https://github.com/user-attachments/assets/8e476426-c657-4c53-888c-258ca3b7d264" />

     ```bash
     docker build -t /java-quotes:latest .
     ```

4. **Verify Your Build:**  

    <img width="1157" height="44" alt="image" src="https://github.com/user-attachments/assets/de4eb9be-5d0e-42de-9e23-bf1aba865a3f" />
 
    - Verify the container is running:
    <img width="1346" height="100" alt="image" src="https://github.com/user-attachments/assets/98238a1c-5fe0-43c6-8e3d-19e3356df304" />

   - Check logs:
    <img width="774" height="70" alt="image" src="https://github.com/user-attachments/assets/dbdd75cd-dd0a-42b9-9ee1-85e577648c9c" />

---

### Task 3: Docker Terminologies and Components

 **Key Docker Terminologies**  
  
1. Image

  A Docker image is a read-only template that contains the application code, dependencies, and runtime environment required to run an application.

  It is used to create containers.

2. Container

  A container is a running instance of a Docker image.

  It is lightweight, isolated, and executes the application.

  Image = blueprint
  Container = running application

3. Dockerfile

  A Dockerfile is a configuration file that contains step-by-step instructions to build a Docker image.

  It defines:

  base image

  dependencies

  application setup

  startup command

4. Volume

  A Docker volume is used for persistent data storage.

  It ensures that data is not lost even if the container is stopped or removed.

  Common use cases:

  databases

  logs

  file storage

5. Network

  Docker networking allows containers to communicate with each other and with external systems.

  Containers in the same network can connect using their container names.

6. Registry (Docker Hub)

  A Docker registry is a storage system for Docker images.

  Docker Hub is the most commonly used public registry where images can be pushed and pulled.

7. Tag

  A tag is used for versioning Docker images.

Examples:

  sample-app:latest

  sample-app:v1.0

---

### Task 4: Docker Image with Multi-Stage Builds

<img width="994" height="713" alt="image" src="https://github.com/user-attachments/assets/90cb6c74-4ab4-4fe8-9c1b-125407a1ced3" />

1. **Implement a Multi-Stage Docker Build:**  
  <img width="1173" height="348" alt="image" src="https://github.com/user-attachments/assets/4493021b-d125-4af5-95d6-a39d1eaebf6b" />
 
   <img width="578" height="297" alt="image" src="https://github.com/user-attachments/assets/f4802c09-e7aa-465c-90f7-f6c2c9a0fce1" />

2. **Compare Image Sizes:**
   
  <img width="1028" height="212" alt="image" src="https://github.com/user-attachments/assets/4b47c7f5-4e38-4adb-8ba6-279af5a31dc8" />

4. **Benefits of Multi-Stage Builds**
   
Smaller Image Size → Faster pull and deploy

Improved Security → No unnecessary packages

Better Performance → Lightweight containers

Cleaner Images → Only required files included
---

### Task 5: Manage Your Image with Docker Hub
1. **Tag Your Image:**  
   <img width="1173" height="48" alt="image" src="https://github.com/user-attachments/assets/053370a9-38b7-449b-a60f-3d6c21d91309" />

2. **Push Your Image to Docker Hub:**  
   <img width="1055" height="250" alt="image" src="https://github.com/user-attachments/assets/16f706ba-49fd-4549-9fe9-ee4135be8c39" />

---

### Task 6: Persist Data with Docker Volumes
1. **Create a Docker Volume:**
   
  <img width="762" height="67" alt="image" src="https://github.com/user-attachments/assets/9ed0c486-3646-4495-9b96-1b05d5cee59d" />

     
3. **Run a Container with the Volume:**
   
 <img width="713" height="119" alt="image" src="https://github.com/user-attachments/assets/f1703a37-391e-46a5-baa9-3dbac9e4d6a3" />
<img width="1349" height="134" alt="image" src="https://github.com/user-attachments/assets/bc064ce5-fc28-470a-b8f5-fd78d8ac9b43" />

5. **Process and Commands:**  
 ### Commands Used

docker volume create my_volume

docker run -d \
  -p 8081:80 \
  -v my_volume:/app/data \
  byteaagam/python-app-mini:latest

### Explanation

Docker volumes are used for persistent storage.  
Data stored inside the volume remains intact even if the container is removed or restarted.

### Result

The container was successfully run with a mounted volume, demonstrating data persistence.


---

### Task 7: Configure Docker Networking
1. **Create a Custom Docker Network:**
   <img width="798" height="65" alt="image" src="https://github.com/user-attachments/assets/80288b81-8aca-4ffd-a0ae-5343206c8138" />

3. **Run Containers on the Same Network:**  
   <img width="805" height="544" alt="image" src="https://github.com/user-attachments/assets/55214c6f-f83e-46e6-b751-51d4a425a105" />

   <img width="1035" height="477" alt="image" src="https://github.com/user-attachments/assets/66f8fe08-241a-43e4-a3f9-00de9b8c7f1a" />

   <img width="899" height="487" alt="image" src="https://github.com/user-attachments/assets/23913183-08a7-44ff-adff-c3b8789e9572" />


4. **Process:**  
 ### Commands Used

docker network create my_network

docker run -d \
  --name python-app-net \
  --network my_network \
  -p 8082:80 \
  byteaagam/python-app-mini:latest

docker run -d \
  --name my-db \
  --network my_network \
  -e MYSQL_ROOT_PASSWORD=root \
  -e MYSQL_DATABASE=sampledb \
  mysql:latest

### Explanation

Docker networking allows containers to communicate with each other using container names instead of IP addresses.

### Result

Both containers were successfully connected through a custom Docker network, enabling inter-container communication.

---

