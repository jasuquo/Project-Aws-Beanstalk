# Project-Aws-Beanstalk
### Deploying a high-availability WordPress website with an external Amazon RDS database to Elastic Beanstalk

In this project, you will learn how to deploy and host WordPress, an open-source blogging tool and content management system (CMS) based on PHP and MySQL. You will implement an architecture to host WordPress for a production workload with minimal management responsibilities required from you. To accomplish this, you will use AWS Elastic Beanstalk and Amazon Relational Database Service (RDS). Once you upload the WordPress files, Elastic Beanstalk automatically handles the deployment, from capacity provisioning, load balancing, auto-scaling to application health monitoring. Amazon RDS provides cost-efficient and resizable capacity, while managing time-consuming database administration tasks for you.

<img width="688" alt="AWS-beanstalk-wordpress-architecture" src="https://user-images.githubusercontent.com/10384951/221054122-07b6cefc-5340-4031-9b89-53e15ba7ca60.png">

## Prerequisites
1.A terminal to run commands 
2.Default VPC -The Amazon Relational Database Service (Amazon RDS) procedures in this tutorial assume that you are launching resources in a default Amazon Virtual Private Cloud (Amazon VPC).
3.Efs required ensure you your project in a region that supports Efs 
4. RDS Mysql

## Launch a DB instance in Amazon RDS

In the following steps you'll use the Amazon RDS console to:

Launch a database with the MySQL engine.

Enable a Multi-AZ deployment. This creates a standby in a different Availability Zone (AZ) to provide data redundancy, eliminate I/O freezes, and minimize latency spikes during system backups.

To launch an RDS DB instance in a default VPC
Open the RDS console.

In the navigation pane, choose Databases.

Choose Create database.

Choose Standard Create.
```
### Important
Do not choose Easy Create. If you choose it, you can't configure the necessary settings to launch this RDS DB.
```

Under Additional configuration, for Initial database name, type ebdb.

Review the default settings and adjust these settings according to your specific requirements. Pay attention to the following options:

**DB instance class** – Choose an instance size that has an appropriate amount of memory and CPU power for your workload.

**Multi-AZ deployment** – For high availability, set this to Create an Aurora Replica/Reader node in a different AZ.

**Master username ** and **Master password **– The database username and password. Make a note of these settings because you will use them later.

Verify the default settings for the remaining options, and then choose **Create database.
**

After your DB instance is created, modify the security group attached to it in order to allow inbound traffic on the appropriate port..
