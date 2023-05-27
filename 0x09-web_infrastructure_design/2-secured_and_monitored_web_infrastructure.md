To design a three-server web infrastructure that hosts the website www.foobar.com while ensuring security, encrypted traffic, and monitoring, let's incorporate the additional elements and explain their roles:

Firewalls:

We'll add three firewalls to enhance the security of the infrastructure.
Firewalls act as a barrier between the internet and the servers, monitoring and controlling incoming and outgoing network traffic.
They help protect against unauthorized access, malicious attacks, and potential vulnerabilities.
SSL Certificate:

An SSL (Secure Socket Layer) certificate is added to enable HTTPS (HTTP over SSL/TLS) for secure communication between the website and the users' browsers.
HTTPS ensures encrypted transmission of data, preventing eavesdropping and tampering with the information exchanged.
The SSL certificate is installed on the web server to enable encryption and establish a trusted connection.
Monitoring Clients:

We'll incorporate three monitoring clients (data collectors) to collect and send server and application metrics to a monitoring service like Sumo Logic or other monitoring tools.
Monitoring clients help gather information about server health, performance, and availability.
They allow proactive identification of issues, performance bottlenecks, or anomalies to ensure the infrastructure operates optimally.
Firewalls' Role:

Firewalls are essential for network security.
They inspect network traffic, filter packets based on predefined rules, and block unauthorized or malicious access attempts.
Firewalls prevent unauthorized access to the servers, protecting them from potential threats.
Traffic Served over HTTPS:

Serving traffic over HTTPS ensures secure communication between the website and users.
HTTPS encrypts data transmitted between the server and the user's browser, preventing unauthorized interception or tampering.
It protects sensitive information, such as user credentials, payment details, and other personal data.
Monitoring Purpose:

Monitoring is used to collect and analyze various metrics and data about the infrastructure's performance, availability, and security.
It helps identify and resolve issues promptly, track resource utilization, and ensure optimal performance.
Monitoring enables proactive maintenance, timely response to incidents, and capacity planning.
Data Collection by Monitoring Tool:

The monitoring tool collects data by deploying monitoring clients or agents on the servers.
These agents collect and transmit performance metrics, log data, and other relevant information to the monitoring service.
The monitoring tool aggregates and analyzes the data, providing insights and alerts for administrators to monitor and manage the infrastructure effectively.
Monitoring Web Server QPS (Queries per Second):

To monitor the web server's queries per second (QPS), metrics such as request count or response time can be collected and analyzed.
Monitoring tools can track the web server's performance, identify potential bottlenecks, and help optimize the infrastructure's capacity.
Now, let's discuss the issues with this infrastructure:

Terminating SSL at the Load Balancer Level:

Terminating SSL at the load balancer level means decrypting the HTTPS traffic at the load balancer and sending the requests to the backend servers over unencrypted HTTP.
This can be an issue as it exposes the traffic between the load balancer and backend servers to potential eavesdropping or tampering.
To mitigate this, SSL termination should happen on the backend servers, ensuring end-to-end encryption.
Single MySQL Server for Writes:

Having only one MySQL server capable of accepting write operations can be a single point of failure (SPOF).
If the MySQL server fails, it can result in downtime or data loss, impacting the website's availability and functionality.
To address this, implementing a MySQL cluster with multiple nodes (both for reads and writes)
