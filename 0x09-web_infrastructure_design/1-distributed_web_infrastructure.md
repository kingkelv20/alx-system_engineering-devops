![1-distributed_web_infrastructure](https://github.com/kingkelv20/alx-system_engineering-devops/assets/117770810/9666a50b-5b89-4986-b7ff-c0b0ad1b9fcf)

## Description
To design a three-server web infrastructure that hosts the website www.foobar.com, we will incorporate the following components:

## Load Balancer (HAProxy):
The load balancer is essential to distribute incoming network traffic across multiple servers. It helps optimize resource utilization, improve reliability, and provide scalability. In this case, we will use HAProxy as our load balancer.

## Web Server (Nginx):
Nginx will serve as the web server to handle HTTP requests and serve static content. It is known for its high performance, efficient resource utilization, and ability to handle concurrent connections.

## Application Server:
The application server will host the dynamic components of the website, including processing business logic and generating dynamic content. It will run the application codebase.

## Database (MySQL):
MySQL will act as the database server, storing and managing the website's data. It provides a robust and scalable relational database management system.

Now, let's address the specific requirements and explain some details about the infrastructure:

## Distribution Algorithm and Load Balancer Setup:
The load balancer (HAProxy) will be configured with a round-robin distribution algorithm. Round-robin ensures that each server receives an equal number of requests in sequential order. This algorithm helps distribute the load evenly across the servers and prevents overloading a single server.

## Active-Active vs. Active-Passive Setup:
In this infrastructure, the load balancer will be configured for an Active-Passive setup. In an Active-Passive setup, only one server is actively serving requests while the others remain on standby. If the active server fails or becomes overwhelmed, the passive server takes over. This setup provides high availability but may result in underutilization of resources during normal operation.

## Primary-Replica (Master-Slave) Database Cluster:
The MySQL database will be configured as a Primary-Replica cluster. In this configuration, the primary node acts as the master, handling read and write operations, while the replica nodes serve as slaves, replicating data from the primary node. The replication process ensures data consistency and provides fault tolerance.

## Primary vs. Replica Nodes:
The primary node in the database cluster handles read and write operations from the application. It is responsible for maintaining the integrity and consistency of the data. Replica nodes, on the other hand, replicate data from the primary node and serve as backups. They can be utilized for read operations, reducing the load on the primary node and enhancing scalability.

Now let's address the issues with this infrastructure:

## Single Point of Failure (SPOF):
The infrastructure currently lacks redundancy, making it vulnerable to a single point of failure. If any component (load balancer, web server, application server, or database) fails, the website's availability will be compromised.

## Security Issues:
The infrastructure lacks essential security measures, such as a firewall and HTTPS configuration. Without a firewall, the servers are exposed to potential attacks and unauthorized access. The absence of HTTPS leaves the communication between clients and servers unencrypted, making it susceptible to interception and data breaches.

## Monitoring:
There is no monitoring system implemented in this infrastructure. Monitoring is crucial to ensure the availability, performance, and security of the servers and services. It helps detect and address issues promptly, ensuring a reliable and optimized environment.

To create a more robust and secure infrastructure, consider addressing the identified issues by adding redundancy, implementing security measures, and incorporating a monitoring system.
