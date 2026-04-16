+++
title = "Engineering @ Sprinklr"
date = 2023-06-01
draft = false
description = "Driving enterprise-scale GraphQL migrations and event-driven architecture for high-concurrency engagement feeds."
tags = ["GraphQL", "Kafka", "Spring WebFlux", "gRPC", "Kubernetes", "MongoDB"]
+++

## Enterprise-Scale Engagement Architecture

During my 6-year tenure at **Sprinklr**, I focused on re-architecting legacy monolithic systems into high-performance, event-driven microservices. My work centered on the **Engagement** and **Display** modules, which serve as the backbone for real-time customer interaction at enterprise scale.

### Key Engineering Milestones

#### 1. Strategic GraphQL Migration
I led the migration of legacy Engagement feed APIs to **GraphQL**, resulting in a **15% reduction in response time** and a **25% decrease in network payload**.
- Designed and built robust GraphQL resolvers that enabled seamless data aggregation from multiple heterogeneous sources.
- Maintained strict performance SLAs for high-traffic endpoints.

#### 2. High-Throughput Event-Driven Core
Engineered an event-driven architecture using **Apache Kafka** pub-sub message queues to power real-time updates across the platform.
- Scaled processing to over **10,000 messages per second**.
- Implemented end-to-end observability and event tracing to ensure reliable delivery and easier debugging of complex distributed flows.

#### 3. Reactive Performance Optimization
Achieved a **10% increase in request responsiveness** for business-critical Engagement paths.
- Leveraged **gRPC** for low-latency inter-service communication.
- Implemented **Spring WebFlux** for non-blocking, reactive processing.
- Optimized caching strategies and established continuous profiling practices to prevent regressive performance degradation.

#### 4. Data Strategy & MongoDB Optimization
Optimized **MongoDB** via progressive sharding driven by event tracing data.
- Reduced query latency by **15%** for "third pane," macro, and publisher happy paths.
- Improved overall responsiveness for 14 key Governance asset classes.

#### 5. Infrastructure & Resilience
Spearheaded cloud-based approaches to handle skewed workloads using **AWS Lambda** and **EC2**, reducing infrastructure costs by **10%**.
- Achieved **near-zero-downtime deployments** and **triple 9 (99.9%) availability** across Kubernetes production environments.
- Established automated testing frameworks (TestNG, Gatling, REST Assured) via Jenkins CI/CD, increasing test coverage to 80% and reducing regressions by 20%.

---

### Tech Stack
- **Backend**: Java (Spring Boot, WebFlux), gRPC, GraphQL
- **Data**: Kafka, MongoDB, Redis
- **Infrastructure**: AWS (Lambda, EC2, EKS), Kubernetes, Docker
- **Observability**: ELK Stack (Elasticsearch, Logstash, Kibana)
- **CI/CD**: Jenkins, Git
