## What is DevOps?
DevOps is a cultural and professional movement that stresses communication, collaboration, and integration between software developers (Dev) and IT operations (Ops) professionals. It’s not a tool; it's a methodology to deliver high-quality software faster.

## The Big Three: Automation, Scaling, & Infrastructure :
-- Automation: Removing manual "Toil." If you do it twice, script it. It ensures consistency and speed.

-- Scaling: The ability to handle more load.
   * Vertical: Adding more RAM/CPU to one server.
   * Horizontal: Adding more servers (the DevOps way).

-- Infrastructure: The underlying "hardware" (servers, networks, storage). In DevOps, we treat this as code (IaC).

## Why is DevOps Important?
Without it, you have "Silos." Devs throw code over the wall, and Ops struggles to run it. DevOps breaks this wall, leading to faster deployments, lower failure rates, and quicker MTTR (Mean Time to Recovery).

📋 Task 1: OSI & TCP/IP Models
In SRE, you use these models to debug. If a site is down, you check Layer 3 (Ping/IP) before checking Layer 7 (HTTP).

Layer (OSI),Real-World Scenario
7. Application,HTTP/HTTPS: Your browser requesting google.com.
6. Presentation,SSL/TLS Encryption: Ensuring the data is readable and secure.
5. Session,APIs/Sockets: Managing the start and end of a connection.
4. Transport,TCP: Ensuring packets arrive in order (Crucial for DBs).
3. Network,IP Addressing: Routing a packet from Hyderabad to a US data center.
2. Data Link,MAC Addresses: How the router in your office talks to your laptop.
1. Physical,Cables/Fiber: The actual electricity or light pulses.


📋 Task 2: Protocols & Ports for DevOps
As a System Engineer, these are your "gates."

Protocol,Port,DevOps Relevance
SSH,  22,   Remote management of Linux servers.
HTTP/S,  80 / 443,   Web traffic and API communication.
DNS,    53,       Resolving service names in a Kubernetes cluster.
FTP/SFTP,  21 / 22,  "File transfers (Legacy, but still common)."
MySQL/Postgres,   3306 / 5432,   Database connections between app and DB tier.


📋 Task 3: AWS EC2 & Security Groups
Concept: A Security Group is a Stateful Firewall.

Inbound Rules: Who can talk to the server (e.g., Allow your IP on port 22).

Outbound Rules: Who the server can talk to (e.g., Allow the server to download updates).

Step-by-Step Guide:

Launch: Go to EC2 Dashboard -> Launch Instance -> Choose Amazon Linux 2023.

Configure SG: Create a new Security Group named web-server-sg.

Add Rule 1: Type: SSH | Port: 22 | Source: My IP (Never use 0.0.0.0/0 for SSH!).

Add Rule 2: Type: HTTP | Port: 80 | Source: Anywhere.

Significance: This provides "Layer 4" security. Even if your app has a bug, the SG blocks unauthorized traffic at the network level.

📋 Task 4: Networking Commands Cheat Sheet

Command,Purpose,Usage Example

ping,   "Check if a host is ""alive.""",  ping 8.8.8.8
traceroute,   "See every ""hop"" a packet takes.",   traceroute google.com
netstat,    See what ports are listening on your server.,   netstat -tulpn
curl,    Test if an API/Website is responding.,   curl -I https://google.com
dig,    Debug DNS issues.,   dig +short google.com

👔 Personal Reflection (The Motivation)

Understanding: DevOps is about building a bridge between code and the customer. Cloud Engineering is the "Lego Set" (AWS/Azure) we use to build that bridge.

Why start? To solve the "Environmental Drift" I saw in my 4 years of IT and to move from reactive support to proactive engineering.

The Goal: To become a Principal SRE capable of designing globally distributed, 99.99% available systems.


