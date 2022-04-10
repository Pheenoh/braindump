# Control Plane
#k8s 

The main controlling unit of the cluster. The "Kubernetes master" consists of 4 parts:

- ETCD - A persistent, lightweight, distributed key-value data store.
- API Server - Serves the API server, creating an internal and external interface to Kubernetes
- scheduler - Manages scheduling of pods. It's purpose is to match resource supply with workload demand.
- controller manager - manages a set of core Kubernetes controllers