
# What is Kubernetes
--------------------

Kubernetes is an open-source system for automating deployment, scaling, and 
management of containerized applications.

- kubernetes commes from the Greek word, which means helmsman or ship pilot.

- You can think of Kubernetes as the pilot on a ship of containers.

- Kubernetes is also referred to as K8s (Pronounced Kate's).

- K8s because it is located between the letter K and S.

- Written in Go language. it ist Deployed by GOOGEL.

Feature of Kubernetes:
......................

 ## Scalability - Kubernetes provides horizontal scaling of pods on the basis of CPU utilization.
 
 The threshold for CPU usage is configurable and Kubernetes will automatically start new pods if the threshold is reached.
 
 - we have two types of Scaling.
 
 1- Vertical Scaling: (is Scaling up)
 
 Means to modify the attributed resources (like CPU or RAM) of each node in the cluster ( Vertical Pod Autoscaler).
 
 2- Horizontal Scaling: (is Scaling Out)
 
 Means modifying the compute rsources of an existing cluster, for example, 
 by adding new nodes to it or by adding new pods by increasing the replica count of pods ( Horizontal Pod Autoscaler).
 
 ## Self-healing - Kubernetes automatically replaces and reschedules containers from failed nodes.
 It kills and restarts containers unresponsive to health checks, based on existing rules/policy.
 It also prevents traffic from being routed to unreponsive containers.
 
 
## Automated rollouts and rollbacks - Kubernetes seamlessly rolls out and rolls back applications updates and configuration change,
 constantly monitoring the application's health toprevent any downtime.
 
## Secret and configuration and management - Kubernetes manages sensitiv data and configuration details for an application separately from the container image.
Secrets consist of sensitive/confidential information passed to the application without revealing the sensitive content to the stack configuration, like on GitHub

## Portability - a cluster can run on any mainstream Linux distribution, processor architectures ( either virtual machines or bare metal),
cloud providers ( AWS, Azure or Google Cloud Platform). and new container runtimes, besides Docker.

