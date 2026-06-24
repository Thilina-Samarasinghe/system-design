# System Design: Complete Reference Guide

> [!TIP]
> 🚀 Quick Link: Access the complete **[Git Commands Reference & Cheat Sheet](./git-commands.md)**.

This workspace contains a comprehensive, interactive, and visually rich reference guide for **System Design**. The guide is designed as a single, self-contained HTML dashboard that acts as a cheat sheet and a structured roadmap for mastering high-scale software architecture.

## 📂 Project Structure
*   **[index.html](./index.html)**: The main interactive dashboard containing the System Design reference material, comparison tables, key architectural formulas, and a 15-step master learning path.
*   **[git-commands.md](./git-commands.md)**: A complete reference guide and cheat sheet for Git, including remote repository setup instructions for syncing to your target GitHub repository.


---

## ❓ What Is This?

This project is an **all-in-one interactive reference center** for software engineers, system architects, and interview candidates looking to build, design, and scale large systems. It consolidates scattered architecture concepts into **9 key domains** within a single responsive web interface:

1.  **Core Infrastructure & Networking**: DNS, Load Balancing (L4 vs. L7), API Gateways, CDNs, Forward vs. Reverse Proxies, TCP/UDP/HTTPs protocols, and security basics (TLS, JWT, Rate Limiting).
2.  **Data Storage & Management**: SQL vs. NoSQL comparisons, Database Indexes (B-Tree vs. Hash), Partitioning/Sharding strategies, Replication (Active-Passive vs. Active-Active), Distributed Filesystems (HDFS/S3), and Bloom Filters.
3.  **Caching & Performance**: Multi-tier caching (Client, CDN, App, DB), caching strategies (Cache-aside, Write-through, Write-back), and cache eviction policies (LRU, LFU, TTL).
4.  **Distributed Systems**: CAP Theorem, Quorum arithmetic ($W + R > N$), Leader/Follower consensus, Heartbeats, and Checksums.
5.  **Communication & Messaging**: Long-Polling vs. WebSockets vs. SSE, Message Queues vs. Service Buses (Kafka vs. RabbitMQ), Push vs. Pull models, and Event-Driven architecture.
6.  **Architecture Patterns**: Microservices vs. Serverless trade-offs, and Stateful vs. Stateless architectures.
7.  **Data Processing & Formats**: Batch vs. Stream processing, and XML vs. JSON vs. Binary formats (Protobuf, Avro).
8.  **Application-Level Concepts**: Full-Text Search engines (Elasticsearch), Notification Systems (Fan-out on write/read), and Distributed Coordination (ZooKeeper, etcd, Consul).
9.  **15-Step Learning Roadmap**: A sequential path from basic networking to production-level containerization, orchestration, and monitoring.

---

## 💎 Why Is It Important?

### 1. Centralized Knowledge Repository
System design concepts are notoriously vast, scattered across hundreds of tech blogs (Netflix, Uber, system-design-primer), textbooks, and online courses. This guide synthesizes these complex ideas into clean, visual summaries with zero fluff.

### 2. Side-by-Side Trade-off Analysis
In system design, **there are no perfect solutions, only trade-offs**. This guide features clear, digestible comparison tables (e.g., SQL vs. NoSQL, WebSockets vs. SSE, Forward vs. Reverse Proxies) that let you compare options instantly.

### 3. Structural 15-Step Mastery Path
Rather than showing a random cluster of concepts, the guide lays out a logical learning progression:
*   **Foundation**: DNS $\rightarrow$ HTTP $\rightarrow$ REST $\rightarrow$ SQL Databases
*   **Scale Basics**: Caching $\rightarrow$ Load Balancer $\rightarrow$ CDN $\rightarrow$ Auth
*   **Containers & Queues**: Docker $\rightarrow$ Message Queues
*   **Architecture**: Microservices $\rightarrow$ Kubernetes $\rightarrow$ Distributed Systems
*   **Production**: Cloud Platforms $\rightarrow$ Monitoring & Observability

### 4. Interactive UX & Modern Aesthetics
Built with modern dark-mode styling, smooth animations, color-coded visual hierarchy, and an interactive top navigation bar, this reference sheet provides an elegant reading experience. Being a single HTML file, it runs locally in any browser offline.

---

## 🚀 How to Use It
1. Open **[index.html](./index.html)** in any web browser.
2. Use the **Navigation Pills** at the top to instantly jump to specific domains.
3. Hover over the cards and interactive nodes in the roadmap to see animated feedback and highlight paths.
4. Keep it open as a secondary monitor cheat sheet during practice design sessions or architectural brainstorming.
