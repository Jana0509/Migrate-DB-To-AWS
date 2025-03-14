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
![GetImage (5)](https://github.com/user-attachments/assets/bc17edc1-30f4-43ac-a7fd-6906fa31ffc9)



## Steps Taken:
1. Created the On-prem Environment using Cloudformation template which provisions the Webserver and DB server in EC2 Instances.
2. Create the AWS VPC from the stractch having multiple Availability zone for creating High Availability and Resilence Solution.
3. Spinned up the EC2 instances in the public subnets of both the availability zones.
4. In order to Create the Connection between on-prem and AWS Cloud, Created the VPC peering between two VPCs which are On-prem VPC and AWS VPC and configured the route tables for the traffic between the VPCs.
5. Provisioned the RDS Database of Maria DB engine and enabled Multi-AZ for high Availability and fault tolerant.
6. Created the DMS Instance which migrates the Data from On-prem DB server to Instance, before this step, created the source and destination endpoint of DB.
7. Once Replication instances are created, create the Dtabase Migration tasks, This starts the replication task and does a full load from catdbonpremises to the RDS Instance.It will create the task then start the task then it will be in the Running State until it moves into Load complete. At this point the data has been migrated into the RDS instance
8. Cut Over the application instance to call the RDS instance.

## **Re-platform- AWS Database Migration Service(DMS)**
1. Created a new managed database, using Amazon Relational Database Service (RDS)
2. Created an AWS Database Migration Service (DMS) Replication Instance - that allows you to replicate data between databases
3. Created the source and target DMS Endpoints
4. Started the replication of data through a DMS replication task


## Conclusion:
This Project teaches how to migrate the on-prem workloads such as application layer and database layer to the AWS cloud by providing High RTO and RPO. By leveraging DMS and other Services we are able to move the workload in ease.
