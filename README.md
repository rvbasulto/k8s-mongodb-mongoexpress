# k8s-mongodb-mongoexpress
# MongoDB + Mongo Express on Kubernetes

## Project Overview

This project demonstrates how to deploy a **MongoDB database** and **Mongo Express web interface** on a Kubernetes cluster, using a structured approach with:

* **Namespaces** for environment isolation
* **Deployments** to manage application lifecycle
* **Services** for internal communication and external exposure
* **Ingress** to route external HTTP requests

It serves as a foundation for understanding how Kubernetes handles multi-component applications, going beyond simple stateless deployments.

## Architecture

* **Namespace**: `mongo-demo`
* **MongoDB Deployment & Service**: Internal database service
* **Mongo Express Deployment & Service**: Web UI to interact with MongoDB
* **Ingress Resource**: Exposes Mongo Express through a domain

## Files

```
./k8s/
├── namespace.yaml
├── mongo-deployment.yaml
├── mongo-service.yaml
├── mongo-express-deployment.yaml
├── mongo-express-service.yaml
└── ingress.yaml
```

## Steps to Deploy

1. **Create Namespace**

```bash
kubectl apply -f namespace.yaml
```

2. **Deploy MongoDB**

```bash
kubectl apply -f mongo-deployment.yaml
kubectl apply -f mongo-service.yaml
```

3. **Deploy Mongo Express**

```bash
kubectl apply -f mongo-express-deployment.yaml
kubectl apply -f mongo-express-service.yaml
```

4. **Apply Ingress Resource**

```bash
kubectl apply -f ingress.yaml
```

5. **Update /etc/hosts (local testing)**
   Map the ingress host to your Minikube IP or cluster IP:

```
192.168.x.x mongo-express.local
```

6. **Access Mongo Express**
   Visit: [http://mongo-express.local](http://mongo-express.local)

## Next Steps

* Implement **Persistent Volumes** for MongoDB data persistence.
* Create a **Helm Chart** to simplify deployment and make it reusable.

## Learnings

* How to structure Kubernetes resources in Namespaces.
* Internal and external service exposure with ClusterIP and Ingress.
* Managing stateful applications (databases) in Kubernetes environments.

---

This project is part of my journey to master Kubernetes beyond stateless apps.

---

Feel free to fork this repo and improve it!

---

## Author

**Robe C. Vazquez**

* [LinkedIn](https://www.linkedin.com/in/roberto-c-vazquez/)
* [Portfolio](https://rcvb.info)
