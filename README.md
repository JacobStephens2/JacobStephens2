## Jacob Stephens

**Platform engineer building production systems, developer tools, and safe AI automation.**

I work across application code, databases, infrastructure, and operations. At Educational Travel Adventures, I lead a two-engineer team and remain hands-on with the reservations platform that supports a multi-million-dollar specialty-travel business. My work spans modernizing a legacy PHP / MySQL stack, improving reliability and performance, and building tools that let people use coding agents with clear boundaries and human review.

[Resume](https://resume.stephens.page/) · [Portfolio](https://stephens.page/portfolio.html) · [LinkedIn](https://www.linkedin.com/in/jacob-c-stephens) · [Contact](https://stephens.page/contact.html)

Interested in **hands-on Senior / Staff platform and agent-platform roles**, and technical lead opportunities with substantial individual engineering work.

### Production impact

- **Removed ~80% of measured database query time** with three online indexes, guided by production measurements and verified with query plans.
- **Cut manifest load time from 5–7 seconds to ~1 second** and SQL statements per request from **2,650 to 183**, while preserving byte-identical HTML.
- **Shipped 14 manager-prototyped features** through engineering review and hardening. Managers prototype in Docker sandboxes; a human reviews changes before production.
- **Instrumented 14 hosts** with Prometheus, Grafana, and Alertmanager, covering host metrics, database replication, uptime, and TLS expiry.

Most of this code is private. The **[ETA platform case study](https://stephens.page/blog/one-engineer-platform-production-systems/)** documents the problems, decisions, and measured outcomes; **[infrastructure-patterns](https://github.com/JacobStephens2/infrastructure-patterns)** shares sanitized architecture decisions, threat models, and operational review practices.

### Selected engineering work

| Project | What to look for |
| --- | --- |
| **[infrastructure-patterns](https://github.com/JacobStephens2/infrastructure-patterns)** | Production architecture decisions and their trade-offs: tenant isolation, agent identity, deployment, and human review. |
| **[Tracewake](https://github.com/JacobStephens2/tracewake)** | Coding-agent orchestration from a labeled issue to a draft PR, with isolated execution, bounded runs, and human-controlled merges. **v0 in development.** [Design](https://github.com/JacobStephens2/tracewake/blob/main/SPEC.md) · [Decisions](https://github.com/JacobStephens2/tracewake/tree/main/docs/adr) |
| **[vaulted-agent](https://github.com/JacobStephens2/vaulted-agent)** | Rust launcher that resolves vault secrets into agent processes, with per-agent secret manifests and optional prompt authentication. [Product](https://vaultedagent.com/) |
| **[muxboard](https://github.com/JacobStephens2/muxboard)** | Python dashboard for tmux sessions across a host or fleet, with browser attach, default-deny authentication, and a documented threat model. [Product](https://muxboard.dev/) |

### Product engineering

- **[Chart35](https://github.com/JacobStephens2/chart35-showcase)** — Offline-first charting with end-to-end encrypted sync across web, iOS, and Android. The public showcase explains the architecture and privacy boundaries. [Product](https://chart35.com/creighton)
- **[Cascade](https://github.com/JacobStephens2/cascade)** — A waterfall sound player with one headless Rust core and six platform shells: web, Android, macOS, Windows, iOS, and watchOS. [Architecture](https://cascade.stephens.page/architecture/) · [Apps](https://cascade.stephens.page/apps)

### Upstream contributions

- **Merged:** [MySQL 8.4 authentication fix](https://github.com/krowinski/php-mysql-replication/pull/148) in `php-mysql-replication`, enabling binlog readers to connect without downgrading server authentication.
- **PR submitted:** [Kimi Code credential-resolution fix](https://github.com/MoonshotAI/kimi-code/pull/2746) for headless runs that ignored environment-provided credentials.
- **Diagnosed and reported:** [Herdr / Muse stale working-state bug](https://github.com/herdrdev/herdr/issues/3951); the Muse team shipped the idle-report fix in Muse Code 1.2.1.

<details>
<summary>Published libraries and more projects</summary>

TypeScript and Go libraries with cross-language test fixtures:

| Library | TypeScript | Go |
| --- | --- | --- |
| HMAC webhook verification | [webhook-verify](https://github.com/JacobStephens2/webhook-verify) · [npm](https://www.npmjs.com/package/@stephenspage/webhook-verify) | [webhook-verify-go](https://github.com/JacobStephens2/webhook-verify-go) |
| AES-256-GCM encryption envelopes | [webcrypto-envelope](https://github.com/JacobStephens2/webcrypto-envelope) · [npm](https://www.npmjs.com/package/@stephenspage/webcrypto-envelope) | [webcrypto-envelope-go](https://github.com/JacobStephens2/webcrypto-envelope-go) |

- **[Drome](https://drome.day/)** — Local-first iOS challenge tracker with a Rust rules engine, SwiftUI, and WidgetKit.
- **[k3s-demo](https://github.com/JacobStephens2/k3s-demo)** — A separate, non-production Kubernetes learning environment with probes, resource limits, ingress, and kustomize.

</details>

---

St. Carlo Acutis, pray for us.
