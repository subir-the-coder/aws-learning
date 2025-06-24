#### EC2 Notes

EC2 is Elastic Compute Cloud = Infrastructure as a Service

- Rent virtual vachines on EC2 (EC2 Instances)
- Store Data on Virtual Drives (EBS)
- Distribute Load across machines (ELB) Elastic Load Balancer
- Scaling the services using an auto-scaling group (ASG)


#### Created the First Instance of t2.micro in ap-south-1, and launched a web server

![image](https://github.com/user-attachments/assets/d81db565-f9e0-4122-9e35-ef0ed7710de4)

The server is accessed by the Public IPv4 Address

**Note:** We should stop the instance, when not using in free tier otherwise we will be billed.
We can also terminate a server, if not required

**Note:** The Public IPv4 address can get changed, after Stopping and Starting an instance

#### EC2 Instance Types

We can use different types of EC2 instances, that are optimized for different types of use cases.

There are 7 different types of EC2 instances
- General Purpose - great for diversity of work loads such as web servers or code repositories, balanced between compute, memory and networking
- Compute Optimzed - grat for compute intensive tasks, which requires high performance processors (Bathc processing, high performance web servers, media transcoding, high performance computing, machine learning, game servers)
- Memory Optimized - great for instances that processes large datasets in memory, relational/non relational db, BI, real time procesing of big unstructured data, distributed web scale cache stores
- Acelerated Computing
- Storage Optimized - great for storage intensive tasks, that require high sequential read write access to large data.  Relational and NoSQL Databases, Online transaction processing, 
- Instance Features
- Measuring Instance Performance

Instance naming convention:
Ex: m5.2xlarge 
- m : General Purpose (instance class)
- 5 : Generation
- 2xlarge : size of the instance class

Compute Optimzed Instances names starts with c series 
Memory Optimzed Instances starts with r series *r stands for RAM
Storage Optimized Instances starts with i, g series
