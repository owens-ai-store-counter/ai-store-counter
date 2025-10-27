# 🧭 AI Store Counter Microservice Application

This repository serves as the **central documentation hub** for the ** AI Store Counter Microservice Application** project — a Go-based microservice Application designed to count customers entering and leaving retail stores using AI-assisted computer vision.

The route repo contains **project-wide documentation, design notes, and links** to the individual service repositories.
It does **not contain service code**, but rather connects and coordinates all related components.

---

## 📘 Overview

**AI Store Counter Microservice Application** is a modular microservice architecture that processes still frames from in-store cameras to estimate foot traffic.
Each service handles a specific function — from frame collection and classification to counting, analytics, and optional customer re-identification.

Core goals:
- Real-time entry/exit detection
- Multi-store headcount management
- Daily counter resets
- Event storage and analytics
- Scalable Azure deployment

For full technical details, see:
- [ARCHITECTURE.md](./docs/ARCHITECTURE.md)
- [DATA_MODEL.md](./docs/DATA_MODEL.md)
- [AZURE_DEPLOYMENT.md](./docs/AZURE_DEPLOYMENT.md)

---

## 🧩 Related Repositories

| Service                               | Description                                                                                         | Repository                                                                                     |
| ------------------------------------- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **`location-service-api`**            | Manages store location metadata and configuration for each retail site.                             | [→ location-service-api](https://github.com/owens-ai-store-counter/location-service-api)       |
| *(upcoming)* `counter-service-worker` | Manages the the store customer count operations. (add customers, remove customers, reset customers) | [→ location-service-worker](https://github.com/owens-ai-store-counter/location-service-worker) |

---

## 🏗️ System Architecture

The StoreCounterService ecosystem is designed as a distributed set of Go-based services, deployable to **Azure Service Fabric** or **Kubernetes (AKS)**.
Each service communicates via HTTP/JSON or Azure messaging (Service Bus/Event Hubs).

High-level workflow:
1. **Camera → collector-service:** sends still frames or pointers to stored images.
2. **classifier-service:** labels each frame as `front` or `back` of head.
3. **counter-service:** interprets labelled events and updates per-store counters.
4. **analytics-service:** aggregates data for reporting and dashboards.
5. **location-service-api:** provides configuration and metadata for each store location.

---

## 🗂️ Repository Contents

``` folder Structure
/
├── docs/
│ ├── ARCHITECTURE.md
│ ├── DATA_MODEL.md
│ ├── AZURE_DEPLOYMENT.md
│ └── diagrams/
│ └── system-overview.png
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```


---

## ⚙️ Development & Contribution

This route repository is **documentation-first** — no runtime code is expected here.
Use it to:
- Add or update system-level docs
- Link new service repos
- Propose architectural decisions (via ADRs)
- Track cross-service initiatives via GitHub Projects or Issues

Contributions and discussions are welcome. Please follow the guidelines in [CONTRIBUTING.md](./CONTRIBUTING.md).

---

## 👥 Maintainers

- **Project Owner:** Steve Owens
- **Contributors:** Open to collaborators interested in distributed systems, Go microservices, or Azure AI integration.

---

## 🏷️ Repository Info

**Repo name :** `ai-store-counter`
**Description:**
> Central documentation and coordination hub for the **AI Store Counter Microservice Application** — includes architecture, design notes, and links to component repositories.

---

**Next Step:**
➡️ Start building out [`location-service-api`](https://github.com/owens-ai-store-counter/location-service-api) as the first live microservice — managing store metadata and configuration used by other components.

https://github.com/owens-ai-store-counter/ai-store-counter