# Kubernetes
------------

# Monolithic Architecture:
.......................

- The monolithic architecture ist the traditional unified model
for the design of a software program.

Being a large, single pieces of software which continuously groes.

- Means composed all in one piece. ...
in a tightly-coupled architecture, each comonent and its associated component must
be present in order for code to be executed or compiled.


- Since the entrie monolith application runs as a single process, 
the scaling of individual features of monolith is almos impossible.

- Sacling the entire application can be achieved by manually deploying a new instance of the monolith on another server, 
  typically behind a load balancer.
  -------------------------------------------
  
# SAO Architecture:
...................

SOA Service Oriented Architecture is an architecture approach for defining,
linking and intergrating reusable business services. These service communicate
with each other to enable simple data passing or it cluld involve tow or more services coordinating activity.
The complexity of each service within SOA is usually very low and they communicate with each other over a set of APIs.
--------------------------------------------------------------

# Microservices Architecture:
............................

- A microservices architecture consists of a collection of small services.
Each service is self-contained and should implement a single business module.

-Each service is a separate codebase, which can be managed by a small development team.

- Services can be deployed independently. 
A team can be update an existing service without rebuilding and redeploying the entire application.

- Service communicate wuíth each other by using well-defined APIs.

Internal implementation details of each service are hidden from other services.
 ....
 
# Containers:
..............

Containers are an application-centric method to deliver high-performing,
scalable applications on any infrastructure of your choice.
Containers are best suited to deliver microservices by providing portable, isolated virtual
environments for applications to run without interface from other running applications.

-"Containers that need to be managed require Container Orchestration."

# Container Orchestration:
.........................
  
  Container orchestrators are tools which group systems together to form clusters
  where container's deployment and management is automated at scale while meeting the requirements mentioned above.
  
  
  cluster: group of Containers, group of Services, or group of anything
  
  Tools:
  
  Marathon                                       Nomad
  
  Azure Service Fabric                         Amazone Elastic container Serive (ECS)
                                               
  Docker Swarm                                 Kubernetes
 
 Kubernetes as a Service
 
 - Amazone Elastic Kubernetes Service (Amazon EKS)                          

 - Azure Kubernetes Service (AKS)
 
 - Google Kubernetes Engine (GKE)
 -----------------------------------------------------------------------------------------------------------