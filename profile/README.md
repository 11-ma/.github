# 🌍 11 Million Acres | Engineering Standards for the Planet

**The Stewardship Blueprint: Human-AI Synergy**

Welcome to the 11 Million Acres development ecosystem. This monorepo serves as our "Source of Truth" for building software that powers solar installation management and renewable energy asset tracking at scale.

---

## Vision

To engineer the "Art of the Impossible" by building the digital operating system for a decentralized, global energy grid—transforming how humanity generates, manages, and values sustainable power to ensure a resilient planet.

## Mission

We practice "Ground-Truth Engineering" to deliver scalable, AI-enhanced platforms—from construction pipelines to utility intelligence. By rigorously synthesizing physical asset data with financial logic, we empower stakeholders with a "God's eye view" of energy infrastructure, enabling rapid market expansion and verified data sovereignty.

## Strategic Pillars

To support this Vision and Mission, the engineering strategy is built on three pillars:

### 1. Stewardship & Rigor (The "How")

We treat code with conservation-grade rigor. Whether using Rust for memory safety or requiring human approval for AI mutations, we prioritize architecture for longevity over temporary shortcuts.

### 2. Data-Driven Sovereignty (The "What")

We do not just aggregate data; we synthesize and verify it. By moving from legacy "postcard" billing to AI-driven utility intelligence, we turn imperfect utility data into a verified asset class.

### 3. Human-AI Synergy (The "Who")

We leverage AI not to replace human oversight, but to amplify it. Our systems, like `powerbuilder.ai`, are designed to flag outliers—such as billing exceptions or operational inefficiencies—while keeping the human engineer as the ultimate owner of performance and security.

---

## 📦 Repository Structure

| Repository | Stack | Description |
|------------|-------|-------------|
| **[dagql](./dagql)** | Rust, PostgreSQL | Directed Acyclic Graph Query Language - our core data layer |
| **[powerbuilder](./powerbuilder)** | React, TypeScript, Vite | Solar installation management frontend |
| **[powerbuilder.ai](./powerbuilder.ai)** | Python, FastAPI, Google Gemini | AI assistant service with approval-gated mutations |

---

## 🔧 dagql — Graph Query Engine

A high-performance query language for Directed Acyclic Graph databases built on PostgreSQL.

**Key Features:**
- SDL-based schema definition with GraphQL-like syntax
- Variable-length path traversal with depth constraints
- Type inheritance (Single/Joined Table Inheritance)
- Built-in RBAC, audit logging, and crypto extensions
- Auto-migrations and schema generation

```bash
# Start the server
cd dagql && docker-compose up -d

# Connect with CLI
make cli
```

**Binaries:** `dagql-server`, `dagql-cli`, `dagql-typegen`, `dagql-gbnf`, `dagql-pydantic`

---

## ⚡ powerbuilder — Frontend Application

React-based solar installation management dashboard built with Vite and TailwindCSS.

**Capabilities:**
- Organization, Site, Project, and Asset hierarchy management
- Phase and milestone tracking with Kanban workflows
- Google Maps integration for site visualization and weather data
- Real-time AI assistant integration
- Firebase authentication with RBAC enforcement

```bash
cd powerbuilder && npm install && npm run dev
```

---

## 🤖 powerbuilder.ai — AI Assistant Service

FastAPI service providing AI-powered assistance via Google Gemini with human-in-the-loop mutation approval.

**Features:**
- Streaming chat responses via SSE
- Structured outputs for action proposals
- Approval gates for data mutations
- Direct DAGQL integration for context-aware responses

```bash
cd powerbuilder.ai && poetry install && uvicorn main:app --reload
```

---

## 🍃 Core Philosophy: Ground-Truth Engineering

We apply conservation-grade rigor to our code:

1. **Verification First** — Treat AI-generated code as a hypothesis. Verify with tests, edge-case analysis, and peer review.
2. **Modular Stewardship** — Write AI-friendly code with descriptive naming and modular patterns.
3. **Architecture for Longevity** — Prioritize readable, maintainable logic over clever syntax.
4. **Human Ownership** — The responsibility for performance and security rests with the human committer.

---

## 💻 Tech Stack Standards

| Language | Standards |
|----------|-----------|
| **Rust** (dagql) | Memory safety via borrow checker, exhaustive `match` statements, audited crate dependencies |
| **TypeScript** (powerbuilder) | Strict mode, discriminated unions for complex data (GeoJSON, graph nodes) |
| **Python** (powerbuilder.ai) | Type hints required, Pydantic models for validation |
| **PostgreSQL/PostGIS** | Primary spatial data store, manual execution plan review for complex queries |

---

## 🛠️ Development Environment

**Requirements:**
- Docker & Docker Compose
- Rust 2024 edition (`rustup`)
- Node.js 20+ with npm
- Python 3.13+ with Poetry
- PostgreSQL 16 (via Docker)

**IDE Recommendations:** Cursor, VS Code with Copilot, or similar AI-assisted editors.

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

**AGENTS.md:** Each repository should define domain-specific context for AI agents. Symlink to `CLAUDE.md`, `GEMINI.md`, `.cursorrules` as needed.

---

## 📚 Quick Reference

```bash
# Start full stack locally
docker-compose -f dagql/docker-compose.yml up -d
cd powerbuilder && npm run dev
cd powerbuilder.ai && uvicorn main:app --port 8000

# Run dagql tests (447+ tests)
cd dagql && cargo test

# Generate TypeScript types from schema
cd dagql && cargo run --bin dagql-typegen -- ../powerbuilder/schema.dagql
```

---

## ❓ Support

- **Discussions:** GitHub Discussion board
- **Leads:** Tag @11MA-Dev-Leads for review

---

© 2026 11 Million Acres | Engineering for a Resilient Planet

