---
aliases: [service]
---
# Kubernetes Service
#k8s  #rkt 

> [!INFO]
> API Resource: https://kubernetes.io/docs/reference/kubernetes-api/service-resources/service-v1/

An abstract way to expose an application running on a set of [[Pods]] as a network service.

# Example Spec
```yaml
kind: Service 
apiVersion: v1 
metadata:
  name: hostname-service 
spec:
  type: NodePort
  selector:
    app: echo-hostname 
  ports:
    - nodePort: 30163
      port: 8080 
      targetPort: 80
```

## Service Types
- **ClusterIP** - The service receives a cluster IP and is only accessible from within the [[Kubernetes]] cluster.

- **NodePort** - Makes the service accessible from outside the cluster via a static [[port]].

- **LoadBalancer** - The service becomes accessible externally through a cloud provider's load balancer functionality.