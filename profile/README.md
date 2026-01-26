# 🌍 11 Million Acres | Engineering Standards for the Planet

**The Stewardship Blueprint: Human-AI Synergy**

Welcome to the 11 Million Acres development ecosystem. This monorepo serves as our "Source of Truth" for building software that powers solar installation management and renewable energy asset tracking at scale.

---

## Vision

To engineer the "Art of the Impossible" by building the digital operating system for a decentralized, global energy grid—transforming how humanity generates, manages, and values sustainable power to ensure a resilient planet.

## Mission

We practice "Ground-Truth Engineering" to deliver scalable, AI-enhanced platforms—from construction pipelines to utility intelligence. By rigorously synthesizing physical asset data with financial logic, we empower stakeholders with a "God's eye view" of energy infrastructure, enabling rapid market expansion and verified data sovereignty.

## Strategic Pillars

### 1. Stewardship & Rigor (The "How")

We treat code with conservation-grade rigor. Whether using Rust for memory safety or requiring human approval for AI mutations, we prioritize architecture for longevity over temporary shortcuts.

### 2. Data-Driven Sovereignty (The "What")

We do not just aggregate data; we synthesize and verify it. By moving from legacy "postcard" billing to AI-driven utility intelligence, we turn imperfect utility data into a verified asset class.

### 3. Human-AI Synergy (The "Who")

We leverage AI not to replace human oversight, but to amplify it. Our systems, like `powerbuilder.ai`, are designed to flag outliers—such as billing exceptions or operational inefficiencies—while keeping the human engineer as the ultimate owner of performance and security.

---

## 📦 Monorepo Structure

```
11ma/
├── apps/                    # Frontend applications
│   ├── powerbuilder/        # Solar O&M management frontend
│   └── powertrader/         # Energy trading frontend
├── packages/                # Shared libraries
│   ├── ui/                  # Shared UI components (Radix + shadcn/ui)
│   └── shared/              # Shared types (generated from dagql)
├── services/                # Backend services
│   ├── dagql/               # Rust DAG query engine + PostgreSQL
│   └── powerbuilder.ai/     # Python/FastAPI AI assistant
└── docs/                    # Documentation
```

| Workspace | Package | Stack | Description |
|-----------|---------|-------|-------------|
| `apps/powerbuilder` | `@11ma/powerbuilder` | React 19, TypeScript 5.9, Vite 7 | Solar installation management frontend |
| `apps/powertrader` | `@11ma/powertrader` | React 19, TypeScript 5.9, Vite 7 | Energy trading management frontend |
| `packages/ui` | `@11ma/ui` | React 19, TailwindCSS 4, Radix | Shared UI component library |
| `packages/shared` | `@11ma/shared` | TypeScript | Shared types (auto-generated from dagql) |
| `services/dagql` | `@11ma/dagql` | Rust, PostgreSQL 16 | Directed Acyclic Graph Query Language |
| `services/powerbuilder.ai` | `@11ma/powerbuilder-ai` | Python, FastAPI, Gemini | AI assistant with approval-gated mutations |

---

## 🔧 dagql — Graph Query Engine

A high-performance query language for Directed Acyclic Graph databases built on PostgreSQL.

**Key Features:**

- SDL-based schema definition with GraphQL-like syntax
- Variable-length path traversal with depth constraints
- Type inheritance (Single/Joined Table Inheritance)
- Built-in RBAC, audit logging, and crypto extensions
- Auto-migrations and TypeScript type generation

**Binaries:** `dagql-server`, `dagql-cli`, `dagql-typegen`, `dagql-gbnf`, `dagql-pydantic`

---

## ⚡ powerbuilder — Frontend Application

React-based solar installation management dashboard built with Vite and TailwindCSS.

**Capabilities:**

- Organization, Site, Project, and Asset hierarchy management
- Phase and milestone tracking with Kanban workflows
- Google Maps integration for site visualization and weather data
- Real-time AI assistant integration
- Firebase authentication with DAGQL RBAC enforcement

---

## 🤖 powerbuilder.ai — AI Assistant Service

FastAPI service providing AI-powered assistance via Google Gemini with human-in-the-loop mutation approval.

**Features:**

- Streaming chat responses via SSE
- Structured outputs for action proposals
- Approval gates for data mutations
- Direct DAGQL integration for context-aware responses

---

## 🍃 Core Philosophy: Ground-Truth Engineering

We apply conservation-grade rigor to our code:

1. **Verification First** — Treat AI-generated code as a hypothesis. Verify with tests, edge-case analysis, and peer review.
2. **Modular Stewardship** — Write AI-friendly code with descriptive naming and modular patterns.
3. **Architecture for Longevity** — Prioritize readable, maintainable logic over clever syntax.
4. **Human Ownership** — The responsibility for performance and security rests with the human committer.

---

## 💻 Tech Stack

| Layer | Technology |
|-------|------------|
| **Data Layer** | Rust + PostgreSQL 16 (dagql) |
| **Frontend** | React 19 + TypeScript 5.9 + Vite 7 |
| **UI Library** | TailwindCSS 4 + Radix UI + shadcn/ui (`@11ma/ui`) |
| **AI Service** | Python + FastAPI + Google Gemini |
| **Auth** | Firebase (identity) + DAGQL RBAC (data access) |
| **Monorepo** | pnpm workspaces + Turborepo |

---

## 🛠️ Development Environment

**Requirements:**

- Node.js 20+ with pnpm 9+
- Rust (latest stable)
- Python 3.11+ with Poetry
- Docker & Docker Compose
- PostgreSQL 16 (via Docker)

**Quick Start:**

```bash
# Install all dependencies
pnpm install

# Start DAGQL backend (PostgreSQL + server)
make dagql-up

# Run frontend
pnpm dev --filter @11ma/powerbuilder

# Run AI service
pnpm dev --filter @11ma/powerbuilder-ai
```

**Common Commands:**

```bash
pnpm dev                                  # Run all services
pnpm build                                # Build all workspaces
pnpm test                                 # Run tests across all workspaces
pnpm lint                                 # Lint all workspaces
pnpm --filter @11ma/powerbuilder dev      # Run specific app
make dagql-test                           # Run DAGQL tests
make dagql-cli                            # Connect CLI to running server
```

**Service Ports:**

| Service | Port |
|---------|------|
| PowerBuilDER (frontend) | 5173 |
| DAGQL (backend) | 8080 |
| PowerBuilDER AI | 8000 |
| OAuth service | 8888 |

---

## 🔒 Security & Ethics

- **Data Sovereignty** — Never input PII, private landowner details, or sensitive location data into public LLMs.
- **Hallucination Audits** — Always verify AI-suggested dependencies via `npm`, `pip`, or `cargo` before merging.
- **Secrets Management** — Use `trufflehog` or similar to prevent credential leaks.
- **Approval Gates** — All AI-proposed mutations require explicit human approval via the powerbuilder.ai service.

---

## 🤝 Contributing

We use **Conventional Commits** for clear project history.

**PR Requirements:**

1. State if AI was used (e.g., "Logic generated by Claude 3.5, verified via manual tests")
2. Include verification checklist: Unit tests ✓ | Linting ✓ | Security scan ✓
3. Follow the "Clean Campsite" rule: Leave the code better than you found it

**AGENTS.md:** Each package has its own `AGENTS.md` with domain-specific guidance for AI coding assistants.

---

## ❓ Support

- **Discussions:** GitHub Discussion board
- **Leads:** Tag @eng-leads

---

© 2026 11 Million Acres | Engineering for a Resilient Planet
