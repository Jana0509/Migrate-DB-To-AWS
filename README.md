# Database Migration from On-premise to AWS
Migrate Database from Onprem to AWS RDS

### Introduction:
Migrating the Database from On-prem to Cloud is one of the key aspects. This Project demonstrates migration of Maria DB from Simulated On-prem to AWS RDS Maria DB engine using Re-platform Approach. In On-prem,  Wordpress Application is running in web server and which is connected to persistent layer [DB layer] (Maria DB) which is deployed in other server. Here, we are migrating the Wordpress application using SSH and replatforming the DB server using AWS Database Migration Service(DMS). In order, to simulate the connection between on-prem and Cloud via Direct connect(DX) or Site-site-VPN, we have used VPC Peering to create the connection between on-prem and AWS.


### Architecture:
![DMS](https://github.com/user-attachments/assets/b698d7c2-d9fe-44aa-be8c-1e50b1f5c058)


