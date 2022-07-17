# Kubernetes
Kubernetes is a portable, extensible, open source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation.  

Kubernetes能夠管理多台主機(physical and vm)上的多個容器。提供以下的功能:
* Service discovery and load balancing 
* Storage orchestration
* Automated rollouts and rollbacks
* Automatic bin packing
* Self-healing
* Secret and configuration management

navigate to the reference to get more information.

# Kubernetes Components
Control Plane Components and Node Components.  
TODO   
將書本裡的概念放上來做Overview

## Pods
Pods are the smallest deployable units of computing that you can create and manage in Kubernetes.  

## Node Components 
Node components run on every node, maintaining running pods and providing the Kubernetes runtime environment.  
The components on a node include the kubelet, a container runtime, and the kube-proxy.
### kubelet
An agent that runs on each node in the cluster. It makes sure that containers are running in a Pod.

### kube-proxy
kube-proxy is a network proxy that runs on each node in your cluster, implementing part of the Kubernetes Service concept.

### Nodes
Kubernetes runs your workload by placing containers into Pods to run on Nodes.A node may be a virtual or physical machine, depending on the cluster. Each node is managed by the control plane and contains the services necessary to run Pods.

### Pods
kube-proxy is a network proxy that runs on each node in your cluster, implementing part of the Kubernetes Service concept.
* Pods that run a single container. The "one-container-per-Pod" model is the most common Kubernetes use case; in this case, you can think of a Pod as a wrapper around a single container; Kubernetes manages Pods rather than managing the containers directly.
* Pods that run multiple containers that need to work together.

# Reference
[What is Kubernetes?](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)