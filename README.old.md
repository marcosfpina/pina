# Marcos Ferreira

<div align="center">
  <h3>Staff Security Engineer | Distributed Systems Architect | NixOS Maintainer</h3>
  <p>
    <a href="mailto:sec@voidnx.com"><img src="https://img.shields.io/badge/Email-sec%40voidnx.com-blue?style=flat-square&logo=gmail" alt="Email" /></a>
    <a href="https://linkedin.com/in/marcosfpina"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin" alt="LinkedIn" /></a>
    <a href="https://github.com/marcosfpina"><img src="https://img.shields.io/badge/GitHub-Follow-181717?style=flat-square&logo=github" alt="GitHub" /></a>
  </p>
  <p>
    <em>Building systems that survive crashes, resist attacks, and explain themselves.</em>
  </p>
</div>

---

## 👨‍💻 Engineering Philosophy

I don't just "use" tools; I dissect and rebuild them. My work focuses on **hermetic infrastructure**, **durable execution**, and **defense-in-depth**. I specialize in translating complex distributed patterns (Circuit Breakers, Event Sourcing, Vector Similarity) into production-grade implementations using Rust, TypeScript, and Nix.

> *"Code is a liability. Architecture is an asset."*

---

## 🔬 Featured Engineering Audits

### 1. [SecureLLM-MCP](https://github.com/kernelcore/securellm-mcp) — Enterprise AI Gateway
**Role:** Architect & Lead Developer | **Stack:** TypeScript, SQLite (WAL), NixOS, Prometheus

A production-hardened implementation of the Model Context Protocol. Unlike standard wrappers, this server implements core distributed systems primitives from scratch.

*   **Custom Semantic Cache Engine:** Implemented a vector similarity search engine (`src/middleware/semantic-cache.ts`) using raw `Float32Array` operations and cosine similarity logic, bypassing heavy vector DB dependencies. Features a deterministic character-frequency fallback for CPU-only environments.
*   **Resiliency Patterns:** Built a stateful **Circuit Breaker** (`src/middleware/circuit-breaker.ts`) with half-open states and exponential backoff to protect downstream LLM providers from cascading failures.
*   **Concurrency Control:** Utilized `Mutex` locks for thread-safe SQLite statistics updates during high-throughput concurrent tool execution.

### 2. [Neutron](https://github.com/kernelcore/neutron) — Durable ML Orchestration
**Role:** Systems Architect | **Stack:** Python, Temporal.io, Ray, DSPy

An adaptive machine learning pipeline that rejects static DAGs (Airflow) in favor of durable, code-first workflows.

*   **Durable Execution:** leveraged `temporalio` decorators (`@workflow.defn`) to maintain pipeline state across worker crashes. The system can resume a multi-day training run exactly where it left off, persisting stack traces and local variables.
*   **Agentic Optimization:** Integrated **DSPy** adapters (`dspy_adapter.py`) to programmatically optimize prompt weights using a Bayesian signature optimizer, bridging the gap between "prompt engineering" and "software engineering".
*   **Hybrid Compute:** Orchestrates stateful actors on a **Ray** cluster for heavy GPU lifting while maintaining control flow in lightweight Temporal workers.

### 3. [NixOS HyperLab](https://github.com/kernelcore/nixos-hyperlab) — Declarative Datacenter
**Role:** Infrastructure Engineer | **Stack:** Nix, KVM/QEMU, Docker, Arion

A 226-module monorepo enforcing 100% reproducibility from the kernel up.

*   **Layered OCI Builds:** Replaced standard Docker builds with **nix2container**, implementing a custom layering strategy that separates runtime dependencies from application code, reducing CI/CD push times by ~80%.
*   **Modular Architecture:** Designed a decoupled module system (`ai-stack.nix`, `gpu-compute.nix`) allowing hot-swappable capability injection into host configurations.
*   **VFIO/IOMMU Passthrough:** Declarative KVM configuration for near-native GPU performance in Windows/macOS guests, managed entirely through Nix expressions.

---

## 🛠️ Technology Landscape

<div align="center">

| **Systems & Runtime** | **Distributed Patterns** | **Security & Observability** |
| :--- | :--- | :--- |
| ![Rust](https://img.shields.io/badge/Rust-Memory_Safety-000000?style=flat-square&logo=rust) ![TypeScript](https://img.shields.io/badge/TypeScript-Strict_Mode-3178C6?style=flat-square&logo=typescript) | **Event Sourcing** (NATS/Kafka) | **Threat Modeling** (STRIDE) |
| ![Nix](https://img.shields.io/badge/Nix-Hermetic_Builds-5277C3?style=flat-square&logo=nixos) ![Python](https://img.shields.io/badge/Python-AST_Manipulation-3776AB?style=flat-square&logo=python) | **Circuit Breakers** & **Rate Limiting** | **eBPF Tracing** & **Syscall Filters** |
| **Temporal.io** (Durable Workflows) | **Vector Similarity** (Cosine/Euclidean) | **Prometheus** & **Grafana** (Metrics) |

</div>

---

## 📈 Impact Metrics

*   **Performance:** Reduced LLM tool execution costs by **50-70%** via custom semantic caching logic.
*   **Efficiency:** Accelerated OCI container builds from **minutes to seconds** using Nix store layer optimization.
*   **Security:** Achieved **100/100** security score on infrastructure audits through immutable root filesystems and declarative AppArmor profiles.

---

<div align="center">
  <a href="mailto:sec@voidnx.com"><b>Request Full Technical Audit</b></a>
</div>
