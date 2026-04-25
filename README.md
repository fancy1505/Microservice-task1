#  Microservices Dockerized Application

##  Overview

This project demonstrates containerization of a microservices-based application using **Node.js**, **Docker**, and **Docker Compose**.

The application consists of four services:

* **User Service** (Port 3000)
* **Product Service** (Port 3001)
* **Order Service** (Port 3002)
* **Gateway Service** (Port 3003)

The Gateway service acts as an API gateway and routes requests to other services.

---

## 🛠️ Tech Stack

* Node.js
* Docker
* Docker Compose

---

## 📂 Project Structure

```
.
├── user-service/
├── product-service/
├── order-service/
├── gateway-service/
├── docker-compose.yml
└── README.md
```

---

## ⚙️ Setup Instructions

### 1. Clone the repository

```
git clone https://github.com/fancy1505/Microservice-task1.git
cd Microservice-task1
```

### 2. Run the application

```
docker-compose up --build
```

---

## 🌐 Service Endpoints

### 🔹 User Service

http://localhost:4000/users

### 🔹 Product Service

http://localhost:4001/products

### 🔹 Order Service

http://localhost:4002/orders

---

## 🔹 Gateway Service (API Gateway)

* http://localhost:4003/api/users
* http://localhost:4003/api/products
* http://localhost:4003/api/orders

---

## 🧪 Testing

### Using Browser

Open the URLs above to verify each service.

### Using curl

```
curl http://localhost:4000/users
curl http://localhost:4003/api/users
```

---

## 🔗 Architecture Flow

```
Client → Gateway Service → User/Product/Order Services
```

---

## ⚠️ Troubleshooting

### ❌ Port already in use

Change ports in `docker-compose.yml`:
 I was facing issue with the port as below error as port was already in use
Attaching to gateway-service-1, order-service-1, product-service-1, user-service-1 user-service-1 | User service running on port 3000 Error response from daemon: failed to set up container networking: driver failed programming external connectivity on endpoint microservices-task-order-service-1 (a10ddc8627a51da69e142eb2b7cdae1151e40f368ecb7998540affb9bc91520a): Bind for 0.0.0.0:3002 failed: port is already allocated PS C:\Users\fancy kejriwal\Documents\Microservices-Task>

Solution- I have updated all the ports in docker-compose.yaml as below updated port and my issue got resolved.
services:
  user-service:
    ports:
      - "4000:3000"

  product-service:
    ports:
      - "4001:3001"

  order-service:
    ports:
      - "4002:3002"

  gateway-service:
    ports:
      - "4003:3003"

```

---

### ❌ Gateway not working

Ensure service names are used instead of localhost:

```
http://user-service:3000
```

---

### ❌ Containers not starting

```
docker-compose down
docker-compose up --build
```

---

## 📸 Screenshots

(Add screenshots of:)

* Docker containers running
* Browser API responses

---

##  Output

* All services run successfully using Docker Compose
* Services are accessible via browser
* Gateway correctly routes requests
<img width="943" height="691" alt="image" src="https://github.com/user-attachments/assets/7db95134-6ac6-4707-a1b8-fee51e0e922d" />
# Now Testing in browsers
# Direct Services
<img width="911" height="503" alt="image" src="https://github.com/user-attachments/assets/973e6df5-b89a-4e71-ad9e-714f40ee168b" />
<img width="850" height="328" alt="image" src="https://github.com/user-attachments/assets/e56edfcc-f35b-4c92-9e3a-35fb9a01e482" />
Proper screenshots I have attached in the screenshot.png 





---


