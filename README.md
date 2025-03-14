# Database Migration from On-premise to AWS
Migrate Database from Onprem to AWS RDS

### Introduction:
Migrating the Database from On-prem to Cloud is one of the key aspects. This Project demonstrates migration of Maria DB from Simulated On-prem to AWS RDS Maria DB engine using Re-platform Approach. In On-prem,  Wordpress Application is running in web server and which is connected to persistent layer [DB layer] (Maria DB) which is deployed in other server. Here, we are migrating the Wordpress application using SSH and replatforming the DB server using AWS Database Migration Service(DMS). In order, to simulate the connection between on-prem and Cloud via Direct connect(DX) or Site-site-VPN, we have used VPC Peering to create the connection between on-prem and AWS.


### Architecture:
![DMS](https://github.com/user-attachments/assets/b698d7c2-d9fe-44aa-be8c-1e50b1f5c058)

## Key Components of the Migration:
**Source Component:**
Simulated the on prem environment with the web application running in web server and Database running in other server in different VPC. Both were deliberately architected in a non-optimal setup to showcase the modernization that AWS enables (check the architecture diagram).

**Target Component:**
Migrated the application to a highly available, well-architected VPC in AWS, spanning two Availability Zones with redundancy and fault tolerance.

## AWS Services Involved:
**Database Migration Service(DMS):**
It is a managed migration and replication service that helps move your database and analytics workloads to AWS quickly, securely, and with minimal downtime and zero data loss. AWS DMS supports migration between 20-plus database and analytics engines, covering homogeneous (ex. MySQL to MySQL) or heterogeneous (Oracle to PostgreSQL) use cases, and single or continuous replication mode. Here, In this Project, we are replatforming the homogeneous data from on-prem to AWS CLOUD using Single replication mode.


## Steps Taken:
