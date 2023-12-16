Kubernetes Architecture
-----------------------
It is divided into two things:

- Worker Nodes, Master Nodes

# Worker Node provides a running environment for client application.
thouth containerized microservices, these application are encapsulated in Pods.

- Pods are the smallest deployable units of computing that you can create and manage in Kubernetes
- A Pod is a group of one or more containers, with shared and network rources.

* Worker Node Components
.........

# Container Runtime:
Pod can run on Container or more, If he has it available Container Runtime,
and this is done in process ( CRI: CRI Runtime Interface ):
The most famous of them:
Containerd ..... and CRI-O

- Node Agent (Kubelet):
- Proxy (kube-proxy):
- addons (DNS, Dashboard User Interface, Monitoring and Loggings)

# Node Agent - Kubelet:

The Kubelet is an agent running on each node and communicates with the control
plane components from the master node.

It receives Pod definitions, primarily from the API Server, and interacts with the container runtime onthe node to run containers associated with the Pod.
It also monitors the health and resources of Pods running containers.


