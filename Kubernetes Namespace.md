---
aliases: [namespace, namespaces]
---
## Kubernetes Namespaces
#k8s #rkt

In [[Kubernetes]], [[namespace|namespaces]] provide a mechanism for isolating groups of resources within a single cluster. 

Names of resources must be unique within a namespace, but can be the same across multiple namespaces. If a resource in Kubernetes is not namespace scoped, it applies cluster wide (must be unique cluster wide).