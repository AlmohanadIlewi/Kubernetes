Kubernetes Concepts Explained
Pod:
-----

Pod refers to one or more conatiners that should be controlled as a single application.
A pod encapsulates application conatiners, storage resources, a unique network ID and other configuration on how to run the conatiners.

Node:
-----
A Node is a worker machine in Kubernetes and may be either a virtual or a physical machine,
depending on the cluster. Each Node is managed by control plane.
A Node can have multiple pods, and the kubernetes control plane automatically handles scheduling the pods across the Nodes in the cluster.

Cluster:
--------
A kubernetes cluster is a set nodes that run containerized application.
Kubernetes cluster allow containers to run across multiple machines and environments:
virtual, physical, cloud-based, and on-premises.
kubernetes conatiners are not restricted to specific operating system, unlike virtual machines.
Instead, they are able to share operating system and run anywhere.

* Namespaces:
-------------
Namespaces are a way to organize clusters into virtual sub-clusters, they can helpful when different teams organize
projects share a kubernetes cluster.

* Service:
----------

A kubernetes service is a logical abstraction for a deployed group of pods in a cluster which allowperform the same function.
Since pods are ephemeral, a service enables a group of pods, which provide specific functions to be assigned name unique IP addresse.

* Deployment:
-------------
A kubernetes Deployment is used to tell kubernetes how to create or modify instance of the pods that hold
a containerized application. Deployment can scale the number of replica pods, enable rollout of updated
code in a controlled manner, or roll back to an earlier deployment version if necessary.

* Workloads:
------------
A workload is an application running on kubernetes.
whether your workload is a single component or several that work together, on kubernetes you run it inside a set of pods.

* Volume:
---------

Similar to a container volume in Docker, but a kubernetes volume applies to a whole pod and is mounted on allowcontainers in the pod.
The volume will be removed only when the pod gets destroyed. Also, a pod can have multiplevolumes associated.

* ReplicaSet:
-------------
A ReplicaSet's purpode is to maintain a stable of replica Pods running ny given time.
As such, it is often used to guarantee the availability of a specified number of identical Pods.

* Ingress:
----------
An API object that provides routing rules to manage external access service in a Kubernetes cluster,
typically via HTTPS/HTTP, Ingress may provide load balancing, SSL termination and name-based virtual hosting.

* Orchestration:
----------------
Container orchestration is the automation of much of the operational effort required to run containerized workloads and services.
this includes a wide range of things software teams need to manage a container's lifecycle, including provisioning, deployment, scaling (up and down), 
networking, load balancing.