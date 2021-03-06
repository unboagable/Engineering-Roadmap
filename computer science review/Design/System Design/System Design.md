# System Design

## Main Components

* webserver (load balancer)
* service (service partition)
* database (primary/secondary database cluster plug cache)

## Concepts

* Vertical scaling
  * increasing the resources of a specific node
  * increasing the scale of a system by adding more power to the existing machine
* Horizontal scaling
  * increasing the number of nodes
  * increasing the scale of a system by adding more machines
  * requires load balancing, meaning the system must also incorporate a component that spreads traffic among the machines equally
* Load balancing
  * by DNS space
    * can be cached
  * round robin
  * by load <->
  * by service type
* Database partitioning
  * vertical partitioning (by feature: one for profiles, one for messages) (federation?)
  * key based partitioning
  * directory based partitioning
  * shards 
    * by geographical location
    * Sharding means splitting the data across multiple machines while ensuring you have a way of figuring out which data is on which machine.
* Caching
  * never do file-based caching
  * with “cache” I always mean in-memory caches like Memcached or Redis 
* Database replication
  * Redundancy
  * (RAID)Redundant array of independent discs
    * raid0 (write some to some, striping) 
    * raid1 (replicate)
* Map reduce

## Considerations

* failures
* availability and reliability
* read heavy vs write heavy
  * cache for read heavy
  * queue for write heavy
* security
