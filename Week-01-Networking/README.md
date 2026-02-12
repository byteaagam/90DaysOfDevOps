# ⭐Week 1: Networking Challenge <br>

## Tasks
### A. **Understand OSI & TCP/IP Models**
   
  #### ⭐ OSI Model (7 Layers)
  
   -The OSI (Open Systems Interconnection) Model is a set of rules that explains how different computer systems communicate over a          network.

   
   ##### 📌 The 7 Layers of OSI
   Let's understand the working of each layers of OSI Model .
     Suppose two friends X and Y , X wants to send a message to Y
     The Journey from X to Y
     
Layer 7. Application: X types "Hello!" into an app.

Layer 6. Presentation: The app encrypts the message so only Y can read it.

Layer 5. Session: A connection is opened to ensure Y is "online" and ready.

Layer 4. Transport: The message is chopped into numbered pieces so none are lost.

Layer 3. Network: The "GPS" adds Y's IP address to find the best path across the internet.

Layer 2. Data Link: The "Local Driver" uses Y's MAC address to find the specific house.

Layer 1. Physical: The data travels as electrical pulses over a wire.

<img width="5667" height="2834" alt="osi" src="https://github.com/user-attachments/assets/788e665b-3774-4f71-9c77-62b282ca37c1" />



#### ⭐ TCP/IP Model

The TCP/IP Model is a 4-layer networking model used in real-world networks and the foundation of the Internet.
It focuses on practical communication between systems and is more widely implemented than the OSI model.

 ##### 📌 The 7 Layers of TCP/IP

  Layer 4: Application - X types the message "Hello!" and the app immediately handles the translation and encryption. In TCP/IP, this one layer does the job of OSI layers 5, 6, and 7.

Layer 3: Transport - The "Quality Control" stage. X’s message is broken into segments. It ensures Y receives them in the right order and asks for a "receipt" to confirm delivery.

Layer 2: Internet - The "Global GPS." This layer stamps the data with Y’s IP address. It doesn't care how it gets there, just that it finds the right network across the globe.

Layer 1: Network Access - The "Physical Delivery." This combines the local driver (MAC address) and the actual road (cables/Wi-Fi). It’s the final step that pushes the bits out of X’s device and onto the wire.

![tcp-layers](https://github.com/user-attachments/assets/3d9c0823-e14c-43af-9ff4-cd30f16d180a)


## <br>
### B. **Protocols and Ports for DevOps**
  #### 🔹 Protocols 
 
A protocol is a set of rules that define how data is formatted, transmitted, and received between devices over a network.

📌 Without protocols, computers wouldn’t understand how to communicate.

 #### 🔹 Prots

 A port is a logical endpoint that identifies which service or application should receive the incoming data.
 Port Range

- 0–65535 total ports

- Well-known ports: 0–1023 (standard services)

- Registered ports: 1024–49151

- Dynamic/Private ports: 49152–65535

#### 🔹 Role of Ports & Protocols in DevOps

##### 1. Server Management & SSH

  DevOps engineers access servers using:

  SSH → TCP → Port 22

  If port 22 is blocked → ❌ no server access.

##### 2. Application Deployment

  When you deploy apps:

  Backend app might run on 8080

  Frontend on 80/443

##### 3. Containers & Kubernetes

  Containers expose ports (EXPOSE 3000)

  Kubernetes maps:

  Service Port → Target Port → Pod Port

  If ports don’t match → 🚫 app won’t be reachable.

##### 4. CI/CD Pipelines

  CI tools communicate using ports:

  Jenkins → 8080

  GitHub Webhooks → 443

  Artifact repo (Nexus) → 8081

  Ports must be open for pipeline to work



