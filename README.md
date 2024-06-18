## Data-Tricks
# Distributed caching system for micro-services architecture 

## Benefits
- Faster responses times, better user experience
- Micro-services may dependent on each other to full fill requests, having a distributed cache reduces micro-services network traffic leading to a lower latency
- reduce load on databases (reduce costs)
- Improves fault tolerancen, micro-services can continue functioning with cached data even if the primary database temporary becomes unavailable
  

## Tools Comparison

| Tool                               | Redis                                                             | Hazelcast                                          | Memcached                                 | Apache Ignite                                                      |
|------------------------------------|-------------------------------------------------------------------|----------------------------------------------------|-------------------------------------------|--------------------------------------------------------------------|
| **Supported Data Structure**       | Key-value store (Lists, Sets, Sorted Sets, Streams, Hashes)       | Key-value store(Maps, Lists, Sets, Queues,etc.)    | Key-value store                           | Key-value store (Maps, Lists, Sets, Queues, Atomic counters, etc.) |
| **Availability & Fault Tolerance** | High (with Redis Sentinel, automatic failover)                     | High (built-in)                                    | Low (no built-in clustering, replication) | High (built-in)                                                    |
| **Replication**                    | Yes (Single Leader replication)                                   | Yes                                                | No (can use third-party solutions)        | Yes                                                                |
| **Partitioning**                   | Yes                                                               | Yes                                                | Yes                                       | Yes                                                                |
| **Persistence**                    | Optional                                                          | Optional                                           | No                                        | Yes                                                                |
| **Consistency**                    | Strong (single instance), eventual (distributed)                  | Strong                                             | Eventual                                  | Strong                                                             |
| **Security**                       | SSL/TLS, ACL, Authentication                                      | SSL/TLS, Authentication, Role-based access control | SASL authentication                       | SSL/TLS, Authentication, Role-based access control                 |
| **Deployment**                     | On-premises, Cloud                                                | On-premises, Cloud                                 | On-premises, Cloud                        | On-premises, Cloud                                                 |
| **Scalability**                    | High  (clustering)                                                | High (scalability with built-in tools)             | Low (Manual scaling)                      | High                                                               |
| **Monitoring**                     | RedisInsight (GUI), Prometheus, Grafana                           | Built-in monitoring tools                          | Third-party tools                         | Built-in monitoring tools                                          |
| **Pricing**                        | Free (Open Source), Paid (Redis Enterprise for distributed mode ) | Free (Open Source), Paid (enterprise support)      | Free                                      | Free (Open Source), Paid                                           |


## Distributed Redis Solutions 
<img width="794" alt="Capture d’écran 2024-06-18 à 12 59 28" src="https://github.com/ybf34/distributedcaching-benchmarks/assets/55197714/790fdede-4fe9-496c-90bc-0482736f9957">



| Tools                              | Amazon ElastiCache Redis                        | Redis Enterprise                                             |
|------------------------------------|-------------------------------------------------|--------------------------------------------------------------|
| **Provider**                       | AWS                                             | Redis                                                        |
| **Deployment**                     | AWS Cloud                                       | On-Premise,AWS, Azure, Google Cloud,                         |
| **Scalability**                    | High , Automatic scaling                        | High, Automatic scaling                                      |
| **Failover**                       | Automatic detection and failover within seconds | Self-healing process automatically detects the hardware failure (elect new primary server) |
| **Deployment Options**             | Cluster Mode, Multi-AZ                          | Cluster Mode, Multi-AZ                                       |
| **Availability SLA**               | 99.99%                                          | 99.999%                                                      |
| **Backup & Restore**               | Yes                                             | Yes                                                          |
| **Active-Active Geo Distribution** | No                                              | Yes                                                          |
| **Monitoring & Management**        | AWS Console, CloudWatch                         | built-in monitoring capabilities, Prometheus,Grafana         |
| **Data Persistence**               | RDB & AOF, Snapshotting                         | RDB & AOF                                                    |
| **Security**                       | TLS/SSL, IAM, Security Groups                   | TLS/SSL, Network Isolation, RBAC                             |
| **Customer Support**               | AWS Support, Community Forums                   | Redis Enterprise Support, Community Forums                   |
| **Pricing**                        | Pay-as-you-go, Reserved Nodes                   | Subscription based, Pay-as-you-go                            |

![image](https://github.com/ybf34/distributedcaching-benchmarks/assets/55197714/87ae7bd4-0329-456c-94c2-9e9fe1c3ed8c)

