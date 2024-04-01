## What Is Kubernetes ?
  - Kubernetes is an open-source Container Management tool that automates container deployment, container scaling, descaling, and container load balancing (also called a container orchestration tool).
  - It is written in Golang and has a vast community because it was first developed by Google and later donated to CNCF (Cloud Native Computing Foundation).
  - Kubernetes can group ‘n’ number of containers into one logical unit for managing and deploying them easily.
  - Kubernetes to manage microservices applications.
  - Multiple numbers of containers run on multiple hosts at a time.

## Why Kubernetes ?
  - Kubernetes addresses several key challenges in modern software development and deployment, making it a crucial tool for managing containerized applications effectively.
  
  - Here's why we need Kubernetes:
      * `Container Orchestration`
      * `Scalability`
      * `High Availability`
      * `Resource Efficiency`
      * `Self-healing`
      * `Service Discovery and Load Balancing`
      * `Declarative Configuration`
      * `Extensibility`
      * `Community Support`
      * `Vendor Neutrality`

## Here We See Detail Explaination Of Above Points That Have Mentioned:
  - **Container Orchestration:**
     - With the rise of containerization, managing individual containers manually becomes impractical as the number of containers and services grows.
     - Kubernetes provides automated container orchestration, enabling efficient deployment, scaling, and management of containerized applications across clusters of machines.
  - **Scalability:**
     - Kubernetes simplifies scaling applications by allowing them to scale horizontally (adding more instances) or vertically (increasing resources per instance) based on demand.
     - This ensures that applications can handle varying levels of traffic without manual intervention.
  - **High Availability:**
     - Kubernetes ensures high availability of applications by automatically monitoring the health of containers and nodes.
     - It can detect and replace failed containers or nodes, ensuring that applications remain available and responsive to user requests.
  - **Resource Efficiency:**
     - Kubernetes optimizes resource utilization by efficiently packing containers onto nodes based on their resource requirements and constraints.
     - This helps in maximizing the utilization of underlying infrastructure, reducing costs, and improving performance.
  - **Self-healing:**
     - Kubernetes automatically detects and responds to failures within the cluster.
     - It can restart containers that fail, reschedule them to healthy nodes, and perform rolling updates with zero downtime, ensuring that applications remain resilient and available.
  - **Service Discovery and Load Balancing:**
     - Kubernetes provides built-in mechanisms for service discovery and load balancing, making it easy to distribute traffic among multiple instances of an application.
     - This simplifies the process of managing network traffic and ensures that applications are accessible and responsive.
  - **Declarative Configuration:**
     - Kubernetes uses a declarative approach to configuration, allowing users to define the desired state of their applications and infrastructure.
     -  This simplifies deployment and management tasks, as Kubernetes automatically reconciles the current state with the desired state, ensuring consistency and reliability.
  - **Extensibility:**
     - Kubernetes has a modular architecture and a rich ecosystem of plugins and extensions, allowing users to customize and extend its functionality to suit their specific requirements.
     - This flexibility enables Kubernetes to adapt to a wide range of use cases and environments.
  - **Community Support:**
     - Kubernetes has a large and active community of developers and contributors, who provide ongoing support, documentation, and best practices.
     - This ensures that Kubernetes remains up-to-date, secure, and reliable, and fosters innovation and collaboration within the community.
  - **Vendor Neutrality:**
     - Kubernetes is open-source and vendor-neutral, which means it can run on any cloud platform, on-premises, or in hybrid environments.
     - This provides users with flexibility and avoids vendor lock-in, allowing them to choose the best infrastructure for their needs.
    
## Architecture Of Kubernetes:

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20221230204459/Yellow-Greyscale-Script-Landscape-Photography-Blog-Banner.jpg"/>

- **Kubernetes Cluster:**
    - In architecture, a Kubernetes cluster refers to a collection of nodes (machines) that are used to run containerized applications orchestrated by Kubernetes.
    - A Kubernetes cluster is a distributed system designed to manage containerized applications efficiently, providing features like automatic scaling, self-healing, and rolling updates while abstracting away the complexities of underlying infrastructure management.
 
- **kubectl:**
    - Kubernetes provides kubectl to use the Kubernetes API and Kubernetes clusterscontrol surfaceCommand line tool for communication.
    - `kubectl` is a command-line tool used to interact with Kubernetes clusters.
    - It allows users to manage and control Kubernetes resources, such as pods, services, deployments, and more, from the command line.
    - It simplifies the management and operation of Kubernetes environments, providing users with a unified interface for interacting with Kubernetes clusters and controlling their resources.

- **Control Plane/Master:**
    - The master node is responsible for managing the Kubernetes cluster.
    - It orchestrates the scheduling and scaling of applications, maintains the desired state of the cluster, and performs various administrative tasks.
    - The master node in Kubernetes serves as the brain of the cluster, coordinating and controlling all activities within the cluster.
    - It provides the API server for external interactions, stores cluster state data in etcd, schedules workloads onto worker nodes, and manages various controllers to ensure the cluster's desired state is maintained. 

- **API Server:**
    - The API server serves as the primary control plane component for Kubernetes.
    - It acts as the front-end for the Kubernetes control plane, serving the Kubernetes API.
    - All administrative tasks, including deploying applications, scaling resources, and managing the cluster's state, are performed through the Kubernetes API server.
    - The API server validates and processes requests from various sources, such as users, administrators, and other Kubernetes components.
    - The Kubernetes API server validates and configures data for API objects, including pods, services, replication controllers, etc.
    - It serves as the entry point for all administrative tasks, enforces security policies, validates requests, and facilitates real-time communication and event-driven workflows within the cluster.

- **Scheduler:**
    - The scheduler uses the Kubernetes monitoring (Watch) mechanism to discover newly created Pods in the cluster that have not yet been scheduled to nodes.
    - The scheduler will schedule each unscheduled Pod found to an appropriate node to run.
    - The scheduler aims to optimize resource utilization and maintain a balanced workload distribution across the cluster.
    - The scheduler first finds all the schedulable nodes of a Pod in the cluster, then scores these schedulable nodes according to a series of functions, and selects the node with the highest score to run the Pod.

- **Control Manager:**
    - The Controller Manager is a core component of the Kubernetes control plane responsible for managing various controllers that regulate the state of the cluster and ensure that the desired state is maintained.
    - Controllers include components such as the Replication Controller, ReplicaSet Controller, Endpoint Controller, Service Account & Token Controller, and Node Controller.
    - Each controller continuously monitors the cluster state and takes corrective actions to reconcile the current state with the desired state defined in the Kubernetes API server.
 
- **ETCD:**
    - **etcd** is a consistent and highly available key-value store used as the backend database for all Kubernetes cluster data.
    - It ensures consistency, durability, and high availability, enabling Kubernetes to maintain the desired state of the cluster and react to changes in real-time.
    - The master node typically hosts an instance of etcd, which serves as the cluster's source of truth.

- **Worker Node:**
    - A worker node, also known as a minion node, is a component of a Kubernetes cluster responsible for running application workloads in the form of containers.
    - It interacts with the Kubernetes control plane components, such as the API server and scheduler, to receive instructions, schedule pods, and report node status.
    - The worker node(s) host the Pods that are the components of the application workload.
    - The worker node provides an execution environment for running pods, which encapsulate one or more containers sharing the same network namespace, storage, and lifecycle.
 
- **Pod:**
    - In Kubernetes, a pod is the smallest and simplest unit of deployment.
    - It represents a single instance of a running process in the cluster.
    - A pod is a group(of one or more) container.
    - Pod provides a higher level of abstraction that allows you to manage multiple containers as a single unit.
    - Pods communicate with each other using the IP address.

- **Docker Engine:**
    - In Kubernetes architecture, Docker Engine is not a component per se, but rather a container runtime that Kubernetes can integrate with to manage containers.
    - Docker Engine is one of several container runtimes supported by Kubernetes.
    - Docker Engine is one of several container runtimes that Kubernetes can integrate with to manage containers within the cluster.
    - While Docker Engine has been commonly used in Kubernetes deployments, the platform supports other container runtimes as well, providing users with flexibility and choice in their containerization strategy.
 
- **kubelet:**
    - The kubelet is the primary "node agent" that runs on each node.
    - The kubelet is a critical component responsible for managing the pods and containers running on a node in the cluster.
    - It performs liveness and readiness probes specified in pod configurations to determine whether containers are healthy and ready to serve traffic.
    - It interacts with the container runtime, enforces resource constraints, monitors pod health, reports node status, and performs other tasks to ensure the reliable and efficient operation of the node within the cluster.
- **kubeproxy:**
    - In Kubernetes, kube-proxy is a network proxy that runs on each worker node in the cluster.
    - It is responsible for managing network connectivity between pods and services within the Kubernetes cluster.
    - kube-proxy sets up network rules (e.g., iptables or IPVS rules) to distribute incoming traffic across the pods backing the service.
    - kube-proxy plays a crucial role in managing network connectivity, load balancing, and service discovery within Kubernetes clusters.
