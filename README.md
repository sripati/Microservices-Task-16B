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



# Microservices Deployment on Kubernetes (Minikube)

Deployment of four containerized Node.js microservices onto a local Kubernetes
cluster running on Minikube, with in-cluster service discovery, health probes,
resource governance, and (bonus) NGINX Ingress routing.

Source application: <https://github.com/sripati/Microservices-Task-16B>

---

## 1. Architecture

```
                     ┌──────────────────────────────────────────┐
   browser / curl    │             Kubernetes cluster           │
        │            │                                          │
        │  Ingress   │   ┌───────────────────┐                  │
        ├───────────►│   │  gateway-service  │  NodePort 30080  │
        │   or       │   │   (port 3003)     │                  │
        │ port-fwd   │   └─────────┬─────────┘                  │
        │            │             │  ClusterIP DNS             │
        │            │   ┌─────────┼─────────┐                  │
        │            │   ▼         ▼         ▼                  │
        │            │ user-    product-   order-               │
        │            │ service  service    service              │
        │            │ :3000    :3001      :3002                │
        │            │ (ClusterIP — internal only)              │
        └───────────►└──────────────────────────────────────────┘
```

| Service         | Container port | Service type | Cluster DNS name                | Endpoints                      |
|-----------------|----------------|--------------|---------------------------------|--------------------------------|
| user-service    | 3000           | ClusterIP    | `http://user-service:3000`      | `/health`, `/users`            |
| product-service | 3001           | ClusterIP    | `http://product-service:3001`   | `/health`, `/products`         |
| order-service   | 3002           | ClusterIP    | `http://order-service:3002`     | `/health`, `/orders` (GET/POST)|
| gateway-service | 3003           | NodePort     | `http://gateway-service:3003`   | `/health`, `/api/users`, `/api/products`, `/api/orders` |

**Why these names matter:** `gateway-service/app.js` hard-codes the upstream
URLs `http://user-service:3000`, `http://product-service:3001`, and
`http://order-service:3002`. The Kubernetes `Service` objects are therefore
named **exactly** `user-service`, `product-service`, and `order-service` and
listen on those same ports, so kube-dns resolves them with zero code changes.

**Why the gateway is NodePort:** it is the single public entry point. The three
backends stay `ClusterIP` so they are unreachable from outside the cluster and
are discoverable only via internal DNS — which is what the assignment asks for.
The gateway still receives a ClusterIP too, so `http://gateway-service:3003`
works in-cluster as normal.

---

## 2. Repository layout

```
submission/
├── deployments/          # Deployment manifests (replicas, probes, env, resources)
│   ├── user-service.yaml
│   ├── product-service.yaml
│   ├── order-service.yaml
│   └── gateway-service.yaml
├── services/             # Service manifests (ClusterIP / NodePort)
│   ├── user-service.yaml
│   ├── product-service.yaml
│   ├── order-service.yaml
│   └── gateway-service.yaml
├── ingress/              # BONUS: NGINX Ingress routing rules
│   └── ingress.yaml
├── screenshots/
│   ├── pods.png
│   ├── logs.png
│   └── service-test.png
└── README.md
```

---

## 3. Prerequisites

| Tool     | Minimum version | Check with          |
|----------|-----------------|---------------------|
| Docker   | 20.10+          | `docker --version`  |
| Minikube | 1.30+           | `minikube version`  |
| kubectl  | 1.27+           | `kubectl version --client` |
| Git      | any             | `git --version`     |

---

## 4. Minikube setup

```bash
# 1. Start a cluster with enough headroom for 8 pods + the ingress controller
minikube start --driver=docker --cpus=2 --memory=4096

# 2. Confirm the node is Ready
kubectl get nodes
kubectl cluster-info

# 3. (Optional but useful) enable the metrics + dashboard addons
minikube addons enable metrics-server
```

---

## 5. Build the images **inside** Minikube's Docker daemon

The manifests reference local image tags (`user-service:1.0`, etc.) that do not
exist on Docker Hub. They must be built inside the cluster's own Docker daemon,
otherwise every pod fails with `ErrImagePull`.

```bash
# Clone the application source
git clone https://github.com/sripati/Microservices-Task-16B.git
cd Microservices-Task-16B/Microservices

# Point your shell's docker CLI at Minikube's daemon
eval $(minikube docker-env)          # Linux / macOS
# PowerShell:  & minikube -p minikube docker-env --shell powershell | Invoke-Expression

# Build all four images
docker build -t user-service:1.0     ./user-service
docker build -t product-service:1.0  ./product-service
docker build -t order-service:1.0    ./order-service
docker build -t gateway-service:1.0  ./gateway-service

# Verify they exist inside Minikube
docker images | grep -E 'user-service|product-service|order-service|gateway-service'
```

> **Alternative** — if you prefer to build on your host Docker, run the four
> `docker build` commands *without* `eval $(minikube docker-env)` and then push
> them into the cluster:
> ```bash
> minikube image load user-service:1.0
> minikube image load product-service:1.0
> minikube image load order-service:1.0
> minikube image load gateway-service:1.0
> ```

> **Note on `eval $(minikube docker-env)`:** it only affects the current
> terminal session. Open a new terminal and your `docker` CLI points back at
> your host daemon. Run `eval $(minikube docker-env -u)` to unset it manually.

---

## 6. Deploy to Kubernetes

Order matters slightly: create the Services first so DNS entries exist before
the gateway pods start calling them.

```bash
cd /path/to/submission

# 1. Services (creates the DNS names)
kubectl apply -f services/

# 2. Deployments (creates the pods)
kubectl apply -f deployments/

# Or apply everything at once, recursively:
kubectl apply -f services/ -f deployments/
```

Expected output:

```
service/user-service created
service/product-service created
service/order-service created
service/gateway-service created
deployment.apps/user-service created
deployment.apps/product-service created
deployment.apps/order-service created
deployment.apps/gateway-service created
```

### Wait for everything to become Ready

```bash
kubectl rollout status deployment/user-service
kubectl rollout status deployment/product-service
kubectl rollout status deployment/order-service
kubectl rollout status deployment/gateway-service
```

### Verify

```bash
kubectl get pods -o wide        # → screenshots/pods.png
kubectl get svc
kubectl get deployments
kubectl get endpoints           # each service must list 2 pod IPs
```

Expected pod list (8 pods, all `1/1 Running`):

```
NAME                               READY   STATUS    RESTARTS   AGE
gateway-service-7d4b8c9f5-abcde    1/1     Running   0          60s
gateway-service-7d4b8c9f5-fghij    1/1     Running   0          60s
order-service-6c8d7b5f4-klmno      1/1     Running   0          60s
order-service-6c8d7b5f4-pqrst      1/1     Running   0          60s
product-service-5b7c6d4e3-uvwxy    1/1     Running   0          60s
product-service-5b7c6d4e3-zabcd    1/1     Running   0          60s
user-service-8f9a7b6c5-efghi       1/1     Running   0          60s
user-service-8f9a7b6c5-jklmn       1/1     Running   0          60s
```

---

## 7. Testing service communication

### 7.1 Via `kubectl port-forward` (works for every service)

Run each in its own terminal, or append `&`:

```bash
kubectl port-forward svc/gateway-service 3003:3003
kubectl port-forward svc/user-service    3000:3000
kubectl port-forward svc/product-service 3001:3001
kubectl port-forward svc/order-service   3002:3002
```

Then, from another terminal:

```bash
# Health checks (the same endpoints the probes hit)
curl http://localhost:3003/health
curl http://localhost:3000/health

# Direct service calls
curl http://localhost:3000/users
curl http://localhost:3001/products

# Through the gateway — this proves inter-service communication,
# because the gateway resolves user-service via cluster DNS
curl http://localhost:3003/api/users
curl http://localhost:3003/api/products
curl http://localhost:3003/api/orders

# Create an order through the gateway (POST → gateway → order-service)
curl -X POST http://localhost:3003/api/orders \
  -H "Content-Type: application/json" \
  -d '{"userId": 1, "productId": 2}'

# Read it back
curl http://localhost:3003/api/orders
```

Expected responses:

```jsonc
// GET /api/users
[{"id":1,"name":"John Doe"},{"id":2,"name":"Jane Smith"}]

// GET /api/products
[{"id":1,"name":"Laptop","price":999},{"id":2,"name":"Phone","price":699}]

// POST /api/orders
{"id":1,"userId":1,"productId":2,"timestamp":"2025-01-01T10:00:00.000Z"}
```

> `{"error":"Error fetching users"}` means the gateway could **not** reach
> user-service — see troubleshooting §9.

### 7.2 Via NodePort (no port-forward needed)

```bash
minikube service gateway-service --url
# → http://192.168.49.2:30080

curl $(minikube service gateway-service --url)/api/users
```

### 7.3 From inside the cluster, using service DNS names

This is the cleanest proof that ClusterIP service discovery works:

```bash
# Temporary debug pod
kubectl run curl-test --image=curlimages/curl:latest -it --rm --restart=Never -- sh

# Inside the pod:
curl http://user-service:3000/users
curl http://product-service:3001/products
curl http://order-service:3002/orders
curl http://gateway-service:3003/api/users
nslookup user-service          # shows user-service.default.svc.cluster.local
exit
```

One-liners without an interactive shell:

```bash
kubectl run curl-test --image=curlimages/curl:latest --rm -i --restart=Never -- \
  curl -s http://gateway-service:3003/api/products

# Or exec into a gateway pod itself
kubectl exec -it deploy/gateway-service -- wget -qO- http://user-service:3000/users
```

### 7.4 Logs proving communication

```bash
# Startup logs
kubectl logs -l app=user-service --tail=20
kubectl logs -l app=gateway-service --tail=20        # → screenshots/logs.png

# Follow the gateway live while you curl it from another terminal
kubectl logs -f -l app=gateway-service

# Logs from all services at once
kubectl logs -l app.kubernetes.io/part-of=microservices-demo --prefix --tail=10
```

---

## 8. BONUS — Ingress

### 8.1 Enable the controller

```bash
minikube addons enable ingress
kubectl get pods -n ingress-nginx          # wait for controller → Running
kubectl wait --namespace ingress-nginx \
  --for=condition=ready pod \
  --selector=app.kubernetes.io/component=controller \
  --timeout=120s
```

### 8.2 Apply the rules

```bash
kubectl apply -f ingress/
kubectl get ingress
```

### 8.3 Map the host name

```bash
minikube ip                                 # e.g. 192.168.49.2
echo "$(minikube ip) microservices.local" | sudo tee -a /etc/hosts
# Windows: add "192.168.49.2  microservices.local" to
#          C:\Windows\System32\drivers\etc\hosts (as Administrator)
```

### 8.4 Routing table

| Request path                          | Routed to               | Rewritten to |
|---------------------------------------|-------------------------|--------------|
| `http://microservices.local/api/users`    | user-service:3000    | `/users`     |
| `http://microservices.local/api/products` | product-service:3001 | `/products`  |
| `http://microservices.local/api/orders`   | order-service:3002   | `/orders`    |
| `http://microservices.local/`             | gateway-service:3003 | *(unchanged)*|

```bash
curl http://microservices.local/api/users
curl http://microservices.local/api/products
curl http://microservices.local/api/orders
curl http://microservices.local/health          # → gateway health
```

**Why two Ingress objects?** The `rewrite-target` annotation applies to every
path within a single Ingress object. The `/api/*` rules need the `/api` prefix
stripped (user-service serves `/users`, not `/api/users`), while `/` must reach
the gateway with the path untouched. Splitting them into
`microservices-api-ingress` and `microservices-root-ingress` keeps each
annotation scoped correctly. NGINX prefers the more specific path, so the two
coexist on the same host.

> On Docker-driver Minikube, if `microservices.local` times out, run
> `minikube tunnel` in a separate terminal, or use
> `curl -H "Host: microservices.local" http://$(minikube ip)/api/users`.

---

## 9. Troubleshooting

| Symptom | Cause | Fix |
|---------|-------|-----|
| `ErrImagePull` / `ImagePullBackOff` | Image not present in Minikube's Docker daemon | Re-run `eval $(minikube docker-env)` **then** rebuild, or `minikube image load <image>:1.0` |
| Pod stuck `Pending` | Not enough CPU/memory on the node | `minikube stop && minikube start --cpus=4 --memory=6144`, or lower `resources.requests` |
| Pod `CrashLoopBackOff` | App crashed on boot | `kubectl logs <pod> --previous` and `kubectl describe pod <pod>` |
| `0/1 Running` forever (never Ready) | Readiness probe failing | `kubectl describe pod <pod>` → check the `/health` path and port |
| Liveness restarts in a loop | `initialDelaySeconds` too short | Increase it in the deployment manifest and re-apply |
| Gateway returns `{"error":"Error fetching users"}` | Gateway can't resolve/reach a backend | `kubectl get endpoints user-service` — if empty, labels/selectors don't match. Verify Service name is exactly `user-service` on port `3000` |
| `kubectl get endpoints` shows `<none>` | Service `selector` ≠ pod template `labels` | Both must be `app: <service-name>` |
| DNS not resolving in cluster | CoreDNS down | `kubectl get pods -n kube-system \| grep coredns` |
| `port-forward` says address in use | Local port already taken | Use a different local port: `kubectl port-forward svc/user-service 8000:3000` |
| Ingress returns 404 | Controller not ready, or wrong `Host` header | `kubectl get pods -n ingress-nginx`; test with `curl -H "Host: microservices.local" http://$(minikube ip)/` |
| Ingress `/api/users` returns 404 from the app | Rewrite not applied | Confirm `use-regex: "true"` and `rewrite-target: /$1$2` on `microservices-api-ingress` |

### Useful diagnostic commands

```bash
kubectl describe pod <pod-name>
kubectl describe svc user-service
kubectl get events --sort-by=.metadata.creationTimestamp
kubectl get pods -o wide
kubectl top pods                       # requires metrics-server
kubectl logs <pod-name> --previous     # logs from the crashed container
minikube dashboard                     # visual cluster browser
```

---

## 10. Manifest design notes (mapping to the grading criteria)

**Deployments** — each of the four contains:
- `image: <service>:1.0` with `imagePullPolicy: IfNotPresent` (locally built)
- `resources.requests` `50m` CPU / `64Mi` memory and `limits` `250m` / `128Mi`
- Environment variables: `NODE_ENV`, `PORT`, `SERVICE_NAME`, plus `POD_NAME`
  injected from the downward API. The gateway additionally carries
  `USER_SERVICE_URL`, `PRODUCT_SERVICE_URL`, and `ORDER_SERVICE_URL`
- `readinessProbe` — `GET /health`, 5s initial delay, 5s period
- `livenessProbe` — `GET /health`, 15s initial delay, 10s period
- Labels `app`, `tier`, `app.kubernetes.io/part-of` with a matching
  `selector.matchLabels`
- `replicas: 2` and a zero-downtime `RollingUpdate` strategy
  (`maxUnavailable: 0`)

**Services** — `targetPort` references the *named* container port `http` rather
than a number, so a port change in the Deployment doesn't silently break the
Service.

> **Note on env vars:** the provided `app.js` files hard-code their ports and
> upstream URLs rather than reading `process.env`. The environment variables
> above are declared to match those values exactly, so the manifests are
> already correct if the application is later refactored to read them (e.g.
> `const port = process.env.PORT || 3000`). No code change is required for this
> deployment to work.

---

## 11. Screenshots

| File | Command to capture |
|------|--------------------|
| `screenshots/pods.png` | `kubectl get pods -o wide` (all 8 pods `1/1 Running`) |
| `screenshots/logs.png` | `kubectl logs -l app=gateway-service --tail=20` |
| `screenshots/service-test.png` | `curl http://localhost:3003/api/users` and `curl http://localhost:3003/api/products` output after `kubectl port-forward` |

---

## 12. Cleanup

```bash
kubectl delete -f ingress/ -f deployments/ -f services/
minikube stop
minikube delete          # destroy the cluster entirely
```

