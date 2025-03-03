---
title: "Replication - Designing Data-Intensive Applications"
allowTitleToDifferFromFilename: true
date: "2025-03-03"
authors:
  - "jathurchan"
projects:
  - "105"
  - "111"
includeLinks:
  - "https://a.co/d/1lromnc"
---

### **Replication**

#### **Why?**

- **High availability**: Keeps system running despite machine failures.
- **Disconnected operation**: Enables functionality during network interruptions.
- **Latency**: Places data closer to users for faster access.
- **Scalability**: Distributes reads across replicas to handle higher volumes.

#### **What?**

- Keeping data copies across multiple machines is complex due to replication challenges.

#### **Challenges**

- Handling changes to replicated data.
- Ensuring consistency despite failures and network issues.

#### **Replication Strategies**

1. **Single-leader replication**
   - Clients write to a single leader.
   - Leader streams changes to follower replicas.
   - Reads from followers may be stale.
   - No conflict resolution needed.
1. **Multi-leader replication**
   - Clients can write to any leader.
   - More robust against faults but introduces conflicts.
1. **Leaderless replication**
   - Clients write to multiple nodes.
   - Reads require multiple nodes to detect stale data.
   - Stronger fault tolerance but weak consistency guarantees.

#### **Replication Types (Fault Handling)**

- **Synchronous**: Followers always up-to-date but single node failure blocks writes.
- **Asynchronous**: Faster but may lose recent data if leader fails.

#### **Handling Node Failures**

- **Follower failure**: Catch-up recovery (fetch missing changes from leader).
- **Leader failure**: Failover (detect failure → elect new leader → reconfigure system).

#### **Leader-Based Replication Methods**

- **Statement-based**: Logs executed SQL statements.
- **Write-ahead log (WAL) shipping**: Uses storage engine logs.
- **Logical (row-based) log replication**: Replicates changes at row level.
- **Trigger-based**: Uses database triggers (prone to errors).

#### **Consistency Models (Replication Lag Handling)**

- **Read-after-write**: Users always see their own writes (read from leader).
- **Monotonic reads**: Users don’t see older data after newer data (stick to same replica).
- **Consistent prefix reads**: Ensures logical ordering of related writes (e.g., Q&A).

#### **Solution to Replication Lag**

- **Transactions**: Provide stronger guarantees but reduce performance and availability.

---

### **Multi-Leader Replication**

#### **When to Use?**

- Multi-datacenter operation
- Performance optimization
- Tolerance for outages and network issues
- Offline clients (e.g., calendar apps)
- Collaborative editing (e.g., Google Docs)

#### Challenges

- Concurrent writes in different datacenters create conflicts.

#### **Handling Write Conflicts**

- **Single-leader**: Blocks second write or forces retry.
- **Multi-leader**: Both writes succeed, conflict resolved later.

#### **Conflict Resolution Strategies**

1. **Avoid conflicts** (simplest approach).
2. **Converge to a consistent state**:
   - **Single-leader**: Sequential order (last write wins).
   - **Multi-leader**: No strict ordering → various strategies:
      - Unique write ID (data loss risk).
      - Replica ID preference (data loss risk).
      - Merge values.
      - Application-level conflict handling.
3. **Custom conflict resolution**:
   - **On write**: Detect conflicts early.
   - **On read**: Resolve when reading data.

- **Conflict resolution approaches**:
  - **CRDTs**: Auto-merge sets, maps, counters.
  - **Mergeable persistent data structures**: Tracks history (like Git).
  - **Operational Transform**: Used in collaborative editors (e.g., Google Docs).

#### **Multi-Leader Topologies**

- **All-to-all**: Most flexible.
- **Circular, Star**: Vulnerable to single-node failure.

#### **Limitations**

- Poorly implemented conflict detection (e.g., PostgreSQL BDR, Tungsten replicator).

---

### **Leaderless Replication**

#### **How it Works**

- No leader. Clients send writes to multiple replicas.
- Order of writes not enforced → eventual consistency.

#### **Handling Failures**

- **Single-leader**: Requires failover for writes.
- **Leaderless**: No failover; writes propagate asynchronously.

#### **Catch-up Mechanisms**

1. **Read repair**: Detects and corrects stale replicas during reads.
2. **Anti-entropy process**: Background process synchronizes replicas.

#### **Quorum Reads & Writes**

- **n** = total replicas, **w** = required write confirmations, **r** = required read confirmations.
- Ensuring **w + r > n** improves consistency.
- Typical setup: **n = 3, w = 2, r = 2**.

#### **Conflict Resolution**

- **Version vectors** (track state of each replica per key).
- Ensures correct ordering of updates across nodes.
