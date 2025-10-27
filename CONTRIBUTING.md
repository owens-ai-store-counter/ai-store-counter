# 🤝 Contributing to the AI Store Counter Microservice Application

Welcome! 👋
Thank you for your interest in contributing to the **AI Store Counter Microservice Application** project.

This repository (`ai-store-counter`) is the **central documentation and coordination hub** for the entire microservice ecosystem.
It contains the system’s **architecture documentation**, **design standards**, and **links** to the individual service repositories — not runtime service code.

Your contributions here help guide and unify development across all services in the suite.

---

## 🧭 Purpose of This Repository

This repository is **documentation-first**.
It exists to:

- Maintain system-wide documentation under `/docs/`
- Define and evolve the project’s architecture and data models
- Coordinate between related microservices
- Track high-level initiatives across the ecosystem
- Serve as the single entry point for understanding the overall project

---

## 🧱 Repository Structure

```
/
├── docs/
│   ├── ARCHITECTURE.md        # System design and service flow
│   ├── DATA_MODEL.md          # Core data entities and relationships
│   ├── AZURE_DEPLOYMENT.md    # Deployment guidance for Azure
│   └── diagrams/
│       └── system-overview.png
├── CONTRIBUTING.md            # This file
├── LICENSE
└── README.md                  # High-level overview and service links
```

---

## 🧩 How to Contribute

### 1. Fork and Clone the Repository

```
git clone https://github.com/owens-ai-store-counter/ai-store-counter.git
cd ai-store-counter
```

Then create a new branch for your work:
```
git checkout -b docs/update-architecture
```

---

### 2. Make Your Changes

Depending on what you’re working on:

- **Documentation:** Add or edit files under `/docs/`
- **Architecture updates:** Modify or expand `ARCHITECTURE.md`, `DATA_MODEL.md`, or `AZURE_DEPLOYMENT.md`
- **Service links:** Update the “Related Repositories” table in `README.md`
- **New proposals:** Draft a new Architecture Decision Record (ADR) under `/docs/adr/`

---

### 3. Commit and Push Your Changes

Use clear, conventional commit messages:

```
git add .
git commit -m "docs: add architecture overview and update related repositories"
git push origin docs/update-architecture
```

---

### 4. Open a Pull Request (PR)

Go to your fork on GitHub and open a **Pull Request** to `main`.

Include:
- A short summary of the change
- The reason for the change
- Links or references if applicable (e.g., related issues or ADRs)

Tag the maintainers (`@SteveOwens` or others) for review.

---

## 🧠 Proposing Architectural Changes

For significant updates that affect multiple services (like event schema changes, new APIs, or architectural adjustments):

1. Open a GitHub **Issue** titled:
   `RFC: <short summary of your proposal>`
2. Use the issue to discuss and refine your idea.
3. When ready, create an **Architecture Decision Record (ADR)** in `/docs/adr/`, using this pattern:

   ```
   /docs/adr/0001-descriptive-title.md
   ```

Each ADR should document:
- The context or problem
- The proposed solution
- Alternatives considered
- The final decision and rationale

---

## 🧾 Adding a New Service Repository

When you create a new microservice in the `owens-ai-store-counter` organization:

1. Create the new repository (e.g., `counter-service-worker`).
2. Add it to the **Related Repositories** table in this repo’s `README.md`, like so:

   ```
   | `counter-service-worker` | Manages store customer count operations. | [→ counter-service-worker](https://github.com/owens-ai-store-counter/counter-service-worker) |
   ```

3. Include a concise `README.md` in the new repo describing:
   - Purpose
   - Primary API endpoints or functions
   - Integration points with other services
   - Deployment notes

---

## 🧪 Documentation Guidelines

When writing or updating documentation:

- Use **Markdown (`.md`)** with clear section headings.
- Keep explanations short, structured, and easy to navigate.
- Store diagrams under `/docs/diagrams/` (use `.png`, `.svg`, or Mermaid syntax).
- Use **relative links** between markdown files.
- Use consistent naming (e.g., `AI Store Counter`, not variations).

Example relative link:
```
See [DATA_MODEL.md](./docs/DATA_MODEL.md) for entity definitions.
```

---

## 🧰 Development Conventions (for service repos)

Although this repo contains documentation only, the **AI Store Counter** services follow these general conventions:

- **Language:** Go ≥ 1.20
- **Formatting:** `gofmt` and `golangci-lint`
- **Testing:** `go test ./...`
- **Branching:** feature branches merged through Pull Requests
- **CI/CD:** GitHub Actions or Azure DevOps pipelines
- **Deployment:** Azure Kubernetes Service (see `AZURE_DEPLOYMENT.md`)

Refer to each service’s own `CONTRIBUTING.md` for service-specific coding rules.

---

## 👥 Communication

- **Issues:** For documentation updates, proposals, or architectural discussions
- **Pull Requests:** For concrete edits or new docs
- **Discussions:** For open-ended design or direction topics

We aim to review contributions within a few business days.

---

## 🪪 License

By contributing to this repository, you agree that your contributions will be licensed under the same terms as this project.
See the [LICENSE](./LICENSE) file for details.

---

Thank you for helping shape the **AI Store Counter Microservice Application**!
Your contributions ensure the system remains clear, scalable, and well-documented.
