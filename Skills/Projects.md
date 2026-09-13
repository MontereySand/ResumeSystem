# Project Archetypes Bank & Swap Catalog

This document serves as a modular project archetype bank. Users can populate these templates with their own real-world projects and swap them into the resume based on the target role and domain.

---

## Permanent Project Rules

1. **Archetype 1 (Primary Hero Project)** always appears first in `Selected Projects`. It anchors the candidate's core engineering strength (e.g., distributed systems, low-level architecture, or complex systems).
2. **Archetype 2 (Platform / Operator / Systems)** is the default second project for platform engineering, MLOps, cloud, backend, and DevOps roles.
3. **The second slot may be swapped** with Archetype 3 or 5 when the job strongly prioritizes real-time systems, networking, or API infrastructure.
4. **Three Selected Projects Maximum:** Keep the resume to at most 3 selected projects to preserve the strict 1-page budget and 14-bullet ceiling.

---

## Reusable Project Archetypes

### Archetype 1: Distributed Systems & Core Infrastructure (Primary Hero Project)

- **Role Alignment:** AI Infrastructure, ML Systems, Distributed Systems, GPU Computing, Low-Latency Engineering.
- **Stack Template:** `[Core Language (e.g. Python, C++, Rust)], [Distributed Framework], [Networking Protocol / Fabric], [Containerization]`
- **Framing & Architecture:** Multi-node cluster or distributed nodes, high-throughput memory pooling, custom protocol acceleration, control planes, and sandboxed testing.
- **Template Bullets:**
  - Achieved \textbf{X$\mu$s} latency by linking X nodes (\textbf{[Protocol, Engine, Fabric]}) and sharding an \textbf{XXXGB} unified memory pool across X worker nodes over \textbf{XX.X Gbps} interconnects
  - Routed workloads to pre-warmed system services with \textbf{Xms} latency by building a local control plane powered by a fine-tuned (\textbf{[Model/Engine]}) Master Engine
  - Reduced p\textbf{XX} latency from \textbf{XX.Xs} to \textbf{X.Xs} and retained \textbf{XX.X\%} accuracy by distilling the \textbf{XXXB} Master into an \textbf{XB} execution model via (\textbf{[Optimization Technique]}) on \textbf{[Database]}-cached architectures
- **Repository Placeholder:** `https://github.com/user/[hero-project]`

---

### Archetype 2: Cloud Platform & Kubernetes Operator (Default Second)

- **Role Alignment:** Platform Engineering, Cloud Infrastructure, Kubernetes, MLOps, SRE, DevOps.
- **Stack Template:** `[Go / Python / Rust], [Kubernetes / Cloud Orchestrator], [Controller Runtime], [CRDs], [Helm], [CI/CD], [Observability]`
- **Framing & Architecture:** Production-grade custom controller reconciling deployment intent into scalable infrastructure, auto-scaling, and health monitoring.
- **Template Bullets:**
  - Automated deployment lifecycles by designing a custom Kubernetes operator reconciling service intent across \textbf{X+} environments
  - Reduced manual provisioning overhead by \textbf{X\%} by developing custom CRDs for automated scaling and health reconciliation
- **Repository Placeholder:** `https://github.com/user/[platform-operator]`

---

### Archetype 3: Real-Time Observability & Gateway Platform

- **Role Alignment:** Backend, Full-Stack, Real-Time Systems, Observability, API Engineering.
- **Stack Template:** `[Backend Framework (FastAPI, Go, Node.js)], [Database], [Message Broker / WebSockets], [Frontend / Dashboard], [Prometheus / Grafana]`
- **Framing & Architecture:** Real-time proxy/gateway with latency percentile tracking, token/event replay, traffic simulation, and interactive telemetry dashboards.
- **Template Bullets:**
  - Processed \textbf{XX,XXX+} events/sec with sub-\textbf{Xms} overhead by architecting an event-driven telemetry ingestion engine
  - Decreased debugging turnaround by \textbf{XX\%} by implementing full-fidelity event replay and real-time observability dashboards
- **Repository Placeholder:** `https://github.com/user/[inference-ops-platform]`

---

### Archetype 4: Transactional Systems & Distributed Ledgers

- **Role Alignment:** Fintech, Payments, Backend Reliability, Distributed Transactions, API Engineering.
- **Stack Template:** `[Language], [In-Memory Cache (Redis)], [Relational Database], [Payment/Billing API], [Idempotency Layer]`
- **Framing & Architecture:** High-throughput transactional billing with in-memory burndown, idempotent relational ledgers, and safe replay queues.
- **Template Bullets:**
  - Prevented double-billing across \textbf{X,XXX+} daily transactions by designing an idempotent ledger with atomic Redis/Lua state burndown
  - Handled \textbf{XXX+} requests/sec under peak load with zero data inconsistencies across distributed payment webhooks
- **Repository Placeholder:** `https://github.com/user/[billing-extension]`

---

### Archetype 5: High-Performance Networking & Config-Driven Tooling

- **Role Alignment:** Networking, Systems Engineering, API Infrastructure, Tooling, Core Backend.
- **Stack Template:** `[Language (Python / Go / C++)], [Configuration Engine], [Transport Protocols], [Test Framework]`
- **Framing & Architecture:** Config-driven gateway/proxy built from scratch; handles circuit breaking, rate limiting, and dynamic traffic routing.
- **Template Bullets:**
  - Engineered a lightweight proxy from scratch achieving sub-\textbf{Xms} parsing latency for \textbf{XX+} routing endpoints
  - Eliminated cascade service failures by building configurable circuit breaking and adaptive rate-limiting modules
- **Repository Placeholder:** `https://github.com/user/[gateway-tooling]`

---

## Role-Specific Swap Matrix

| Target Domain | Slot 1 (Hero) | Slot 2 (Secondary) | Slot 3 (Tertiary) |
| :--- | :--- | :--- | :--- |
| **AI Systems / Infrastructure** | Archetype 1 (Distributed) | Archetype 2 (Operator) | Archetype 3 (Observability) |
| **Backend & Distributed Systems** | Archetype 1 (Distributed) | Archetype 5 (Networking) | Archetype 3 (Observability) |
| **Cloud / Platform / DevOps** | Archetype 1 (Distributed) | Archetype 2 (Operator) | Archetype 5 (Networking) |
| **Fintech & Product Backend** | Archetype 1 (Distributed) | Archetype 4 (Transactional) | Archetype 5 (Networking) |
| **Full-Stack & Product Engineering** | Archetype 1 (Distributed) | Archetype 3 (Observability) | Archetype 4 (Transactional) |

---

## Maintenance & Population Rules
1. **Fill Truthfully:** Replace archetype placeholder brackets (`[...]`) with concrete project accomplishments, truthful metrics, and actual repository URLs.
2. **Format Uniformity:** Maintain the established bullet verbosity (~1.5–2 lines per bullet).
3. **Never Invent Experience:** Do not claim production usage, team size, funding, or metrics that did not exist.