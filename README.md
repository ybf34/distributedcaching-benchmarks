# Data-Tricks
## Distributed caching system for micro-services architecture 

### Benefits
- Faster responses times, better user experience
- Micro-services may dependent on each other to full fill requests, having a distributed cache reduces micro-services network traffic leading to a lower latency
- reduce load on databases (reduce costs)
- Improves fault tolerancen, micro-services can continue functioning with cached data even if the primary database temporary becomes unavailable
  

### Caching Solutions

| Tools                               | Redis                                                             | Hazelcast                                          | Memcached                                 | Apache Ignite                                                      |
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

## Redis

### Fully Managed Distributed Solutions 
| Tools                       | Amazon ElastiCache Redis                        | Redis Enterprise                                             |
|-----------------------------|-------------------------------------------------|--------------------------------------------------------------|
| **Provider**                | AWS                                             | Redis                                                        |
| **Deployment**              | AWS Cloud                                       | On-Premise,AWS, Azure, Google Cloud,                         |
| **Scalability**             | High , Automatic scaling                        | High, Automatic scaling                                      |
| **Failover**                | Automatic detection and failover within seconds | Self-healing process automatically detects the hardware failure (elect new primary server) |
| **Deployment Options**      | Cluster Mode, Multi-AZ                          | Cluster Mode, Multi-AZ                                       |
| **Availability SLA**        | 99.99%                                          | 99.999%                                                      |
| **Backup & Restore**        | Yes                                             | Yes                                                          |
| **Monitoring & Management** | AWS Console, CloudWatch                         | built-in monitoring capabilities, Prometheus,Grafana         |
| **Data Persistence**        | RDB & AOF, Snapshotting                         | RDB & AOF                                                    |
| **Security**                | TLS/SSL, IAM, Security Groups                   | TLS/SSL, Network Isolation, RBAC                             |
| **Customer Support**        | AWS Support, Community Forums                   | Redis Enterprise Support, Community Forums                   |
| **Pricing**                 | Pay-as-you-go, Reserved Nodes                   | Subscription based, Pay-as-you-go                            |

### Self-Managed Redis(aws) /Fully Managed ElastiCache Redis Comparison
| Feature                     | Self-Managed Redis                                           | Fully Managed ElastiCache                                    |
|-----------------------------|--------------------------------------------------------------|--------------------------------------------------------------|
| **Setup**                   | Manual installation on hardware or EC2 , (Kubernetes)        | Cluster provisioning in minutes via AWS Management Console   |
| **Configuration**           | Manual configuration required                                | Pre-configured                                               |
| **Scalability**             | Manual node configuration and network adjustments (automatic scaling with k8s?) | Automatic scaling with up to 310 TiB in-memory data          |
| **Monitoring**              | Third-party tools                                            | Built-in monitoring via Amazon CloudWatch                    |
| **Automatic Failover**      | Redis Sentinel or Cluster for failover management            | One-click Multi-AZ failover with automatic primary promotion |
| **Security**                | implement Aws encryption-in-transit for Redis                | Built-in in-transit (TLS) and at-rest encryption             |
| **Read Scalability**        | Manual setup of read replicas                                | Up to 5 replicas per shard across multiple Availability Zones |
| **Write Scalability**       |  Redis Cluster setup                                         | Automatic distribution across up to 500 shards               |
| **Online Cluster Resizing** | Supports adding/removing nodes dynamically but the process is error-prone (partial availability) | dynamic shard addition/removal with improved latency during resharding, |
| **Pricing**                 | Pay for EC2 instances and additional third-party tools       | Pay for managed service ( infrastructure/usage)              |
