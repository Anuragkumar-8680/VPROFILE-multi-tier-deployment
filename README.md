# Multi-Tier Web Application Infrastructure Deployment (vProfile)

A production-style, automated infrastructure deployment of a distributed 5-tier Java Spring Boot application using Vagrant and VirtualBox VMs. Instead of running a monolithic block, each functional tier of the application is completely isolated into its own dedicated Linux virtual server instance to accurately mirror enterprise architecture standards.

## Architectural Design

The application stack distributes traffic and manages dependencies across five dedicated virtual machines:

* **Web Tier (Nginx):** Functions as the internet-facing reverse proxy and round-robin load balancer.
* **Application Tier (Apache Tomcat):** Hosts the Java Spring Boot application layer and processes business logic.
* **Database Tier (MariaDB/MySQL):** Handles relational SQL data persistence and secure transactional user storage.
* **Caching Tier (Memcached):** Acts as a high-performance memory object caching layer to offload heavy read operations from the database.
* **Message Broker Tier (RabbitMQ):** Manages asynchronous message queuing, streaming, and loose coupling between internal application services.

## Repository Layout

```text
vprofile-multi-tier-deployment/
├── src/                               # Application source code
├── pom.xml                            # Maven build dependency manifest
└── vagrant/
    └── Manual_provisioning_WinMacIntel/
        ├── Vagrantfile                # Multi-node infrastructure configuration 
        └── VprofileProjectSetup...pdf # Architectural execution guide

