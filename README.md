# Microservices-Task

## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.

---

## Architecture Overview

```
                    ┌─────────────────────────────┐
                    │     Gateway Service :3003    │
                    │  (Single entry point / BFF)  │
                    └────────────┬────────────────-┘
                                 │ routes requests
             ┌───────────────────┼───────────────────┐
             ▼                   ▼                   ▼
  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐
  │  User Service    │  │ Product Service  │  │  Order Service   │
  │    :3000         │  │    :3001         │  │    :3002         │
  └──────────────────┘  └──────────────────┘  └──────────────────┘

  All services communicate via Docker network: microservices-network
```

| Service          | Port | Description                          |
|------------------|------|--------------------------------------|
| user-service     | 3000 | Returns list of users                |
| product-service  | 3001 | Returns list of products             |
| order-service    | 3002 | Manages orders (in-memory)           |
| gateway-service  | 3003 | Aggregates all services (API gateway)|

---

## Services and Endpoints

### **User Service**
- **Base URL:** `http://localhost:3000`
- **Endpoints:**
  - **List Users:**  
    ```
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)
    

    <img width="383" height="168" alt="G Google" src="https://github.com/user-attachments/assets/185c314c-66a5-4638-b471-4620e094fb3d" />
    
    <img width="466" height="301" alt="G Google" src="https://github.com/user-attachments/assets/a1db5b86-4b26-4122-bc55-8719f5c02903" />

- **Docker File:**
<img width="842" height="290" alt="EXPLORER" src="https://github.com/user-attachments/assets/8b7e0fdd-37e3-4c67-bde6-b649042b09ef" />

---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)

    <img width="420" height="158" alt="  c A" src="https://github.com/user-attachments/assets/04fb6cf0-6697-4f5f-ba18-8e5696c1e5a6" />
    <img width="462" height="338" alt="• localhost3001products" src="https://github.com/user-attachments/assets/2ce5ba22-aec1-4240-affa-9ee892502676" />


**Docker File:**

<img width="755" height="314" alt="EXPLORER" src="https://github.com/user-attachments/assets/aa5ed4e5-1f3e-4551-a719-60cf9dcd59fa" />

---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

    <img width="408" height="168" alt="localhost 3002health" src="https://github.com/user-attachments/assets/8863a55c-85bf-40a5-88c5-58223a02d3fe" />
    <img width="814" height="115" alt="• sripat i@ripatis-MacBook-Air Microser" src="https://github.com/user-attachments/assets/53175749-dc2e-4ac2-bd55-bd325b96d693" />
    <img width="461" height="273" alt="88  G Google C day" src="https://github.com/user-attachments/assets/d99dba64-ad2b-454f-8a19-2b3ff0585c79" />


- **Docker File:**
<img width="800" height="277" alt="V MICROSERVICo o Ce" src="https://github.com/user-attachments/assets/d68f6344-8635-4ff5-9cd6-fb4951fb7e8c" />

---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
    <img width="500" height="289" alt="BB  G Google" src="https://github.com/user-attachments/assets/c009a7c7-6648-40d6-b99a-4055bb6eb5ce" />

  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
    <img width="481" height="335" alt="localhost3003apiproducts" src="https://github.com/user-attachments/assets/79b11a5e-7242-48fc-b16a-34db02590402" />

  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```
    <img width="465" height="265" alt="G Google" src="https://github.com/user-attachments/assets/1c15e9c3-3fe8-4538-9c43-7b1c2ab0df59" />

  - **Health Check:**
  <img width="434" height="189" alt="G Google" src="https://github.com/user-attachments/assets/8e0773de-0f86-4a55-a80d-9ac461b91f1e" />

  
  - **Docker File:**
  <img width="874" height="231" alt="y oateway-service" src="https://github.com/user-attachments/assets/43781ce3-a87d-4213-ba06-24faf4074224" />

---

### **Folder Structure and Docker Compose File**
<img width="268" height="475" alt="EXPLORER" src="https://github.com/user-attachments/assets/747811bb-8489-4add-9647-b801eb51b949" />
<img width="489" height="688" alt="Pasted Graphic 18" src="https://github.com/user-attachments/assets/91a1a3cd-2af2-41bb-8528-6e34564af40d" />


## Instructions
1. Start all services using the `docker-compose` file:
   ```
   docker-compose up Or
   docker-compose up --build
   ```
<img width="1131" height="482" alt="Pasted Graphic 6" src="https://github.com/user-attachments/assets/9108f356-69ec-4908-807e-db3e4ceb71fd" />
<img width="1088" height="340" alt="Pasted Graphic 7" src="https://github.com/user-attachments/assets/0f04e849-ac10-4984-8d5f-57216e7fdb8e" />
<img width="1356" height="248" alt="Pasted Graphic 8" src="https://github.com/user-attachments/assets/673055f2-ac82-44c3-b3a5-583620205883" />
<img width="976" height="171" alt="1 minute and" src="https://github.com/user-attachments/assets/9d27e17b-120b-4cd4-9a5a-1cada8937924" />
<img width="980" height="219" alt="micreservices-sateways 2003-2003 c3" src="https://github.com/user-attachments/assets/175f9521-33b5-4bbe-8cc5-49af65fa2abb" />

2. Once the services are running, use the above endpoints to verify the functionality.

Happy testing!
