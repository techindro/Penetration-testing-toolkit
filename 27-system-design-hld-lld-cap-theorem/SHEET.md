# 📐 Module 27: System Design (HLD/LLD), CAP Theorem & Distributed Systems

Essential System Design concepts, High-Level Architecture patterns, CAP Theorem tradeoffs, Caching strategies, and Load Balancing required for system design interviews.

---

## ⚖️ 1. The CAP Theorem

In any distributed data store, you can choose at most **two** of the following three guarantees:

- **C - Consistency:** Every read request receives the most recent write or an error.
- **A - Availability:** Every non-failing node returns a non-error response (without guarantee of latest data).
- **P - Partition Tolerance:** System continues operating despite network message drops between nodes.

$$\text{Distributed System Choice: CP (e.g. MongoDB/HBase) OR AP (e.g. Cassandra/DynamoDB)}$$

---

## ⚡ 2. Caching Strategies & Eviction Policies

### Caching Strategies:
1. **Cache-Aside (Lazy Loading):** Application queries cache first; on miss, queries DB and updates cache.
2. **Write-Through:** Application writes to cache and DB synchronously.
3. **Write-Behind (Write-Back):** Application writes to cache immediately; cache asynchronously writes to DB in background.

### Eviction Policies:
- **LRU (Least Recently Used):** Discards items not accessed for the longest time.
- **LFU (Least Frequently Used):** Discards items accessed least number of times.

---

## 🌐 3. Load Balancing & Horizontal Scaling

- **Horizontal Scaling (Scale-Out):** Adding more server instances (e.g., EC2 instances behind AWS ALB).
- **Vertical Scaling (Scale-Up):** Adding more RAM/CPU to a single server machine.
- **Load Balancing Algorithms:**
  - **Round Robin:** Distributes requests sequentially across servers.
  - **Least Connections:** Routes request to server with fewest active connections.
  - **Consistent Hashing:** Minimizes key remapping during node scale-in/scale-out in distributed caches.
