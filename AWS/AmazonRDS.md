1. Relational Database Service 
2. Challenges of Standalone Relational Database
3. Server maintenance and energy footprint
4. Software install and patche
5. Database backup and high availability
6. Limits on scalability
7. Data security
8. OS installs and patches 
9. RDS is a managed service that sets up and operates a relatioal database in the cloud
10. AWS manages OS install and patches, database software install and patches, databse backup, high availability, scaling, power and rack & stack, server maintenance. 
11. DB instance class: CPU, Memory, Network Performance
12. DB instance storage: magnetic, general purpose(SSD), provisioned IOPs
13. DB instance in private subnet
14. Synchronize DB instance across Availability Zones
15. If master DB instance fails, standby DB will serve to avoid data loss
16. Asynchronous replication method 
17. Offload read queries from the master DB instance
18. Ideal for read-heavy databse workloads
19. Read replica can be promoted to Master if needed 
20. Use case: web and mobile applications (high throughput, massive storage scalability, high availability), e-commerce application (low-cost database, data security, fully managed solution), mobile and online games (rapidly grow capacity, automatic scaling, database monitoring) 
