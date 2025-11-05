

## 3-Tier App on K8s (Minikube)

This project demonstrates the **end-to-end DevOps implementation** of a full-stack chat application, containerized with **Docker**, orchestrated using **Kubernetes**, and fully automated through infrastructure and configuration management best practices.


This project showcases how a DevOps engineer can:

- Containerize microservices with **Docker**
- Deploy services on a **Kubernetes cluster**
- Use **ConfigMaps** and **Secrets** for secure configuration management
- Expose services via **ClusterIP**, **NodePort**, and **Ingress**
- Debug and monitor deployed applications efficiently


## 🏗️ Architecture Diagram

![[diagram-export-05-11-2025-17_32_10.png]]


## 🧩 Kubernetes Resources Used

| Resource        | Description                                                       |
| --------------- | ----------------------------------------------------------------- |
| **Namespace**   | `chat-app` — to isolate application resources                     |
| **Deployments** | `frontend-deployment`, `backend-deployment`, `mongodb-deployment` |
| **Services**    | `frontend-service`, `backend-service`, `mongodb-service`          |
| **Secrets**     | Stores sensitive credentials like DB password and JWT secret      |
| **Ingress**     | (Optional) Used for domain-based routing                          |

## 🪄 Step-by-Step Setup & Deployment

###  Create the Namespace

```
kubectl create namespace.yml
```

### Deploy MongoDB

```
kubectl apply -f mongodb-deployment.yml
```


###  Deploy Backend

```
kubectl apply -f backend-deployment.yml
```

###  Deploy Frontend

```
kubectl apply -f frontend-deployment.yml
```

###  Apply Service

```
kubectl apply -f frontend-service.yml
```

```
kubectl apply -f backend-service.yml
```

```
kubectl apply -f mongodb-service.yml
```

### Apply Secret

```
kubectl apply -f secret.yml
```

### Apply PV/PVC

```
kubectl apply -f mongodb-pv.yml
kubectl apply -f mongodb-pvc.yml
```


### Apply Ingress to access Application

```
kubectl apply -f ingress.yml
```

- Open 127.0.0.1:80
### Boom 

![[Screenshot 2025-11-05 101054.png]]



## 📈 Future Improvements

- Add **CI/CD pipeline** with GitHub Actions for automated deployment
- Integrate **Ingress + TLS** using Cert-Manager
- Add **Prometheus + Grafana** for monitoring
- Configure **Horizontal Pod Autoscaler (HPA)**


