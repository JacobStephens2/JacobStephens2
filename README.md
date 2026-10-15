## Jacob Stephens

**Software factories, AI agent infrastructure, and hands-on engineering leadership.**

My current focus is **[thirdshift](https://thirdshift.app/)**, an open-source software factory in Rust that takes GitHub issues through implementation, review, and CI to pull requests.

As Head of Engineering at Educational Travel Adventures, I lead an engineering team and remain hands-on with the reservations, payments, Linux fleet, and AI-agent infrastructure of a multi-million-dollar specialty-travel business.

[Start here](https://stephens.page/) · [thirdshift](https://thirdshift.app/) · [Portfolio](https://stephens.page/portfolio.html) · [Resume](https://stephens.page/resume/) · [LinkedIn](https://www.linkedin.com/in/jacob-c-stephens) · [Contact](https://stephens.page/contact.html)

### Current work: thirdshift

- A deterministic Rust engine supports **six coding-agent harnesses** and coordinates standards and spec reviews, CI checks, and bounded repair loops.
- Dependency-aware parallel tickets run in separate Git worktrees. Failed runs preserve their work for continuation; merging is explicitly configured.
- I test the assumptions behind the factory. **[Fresh Eyes Beat a Second Family](https://stephens.page/blog/fresh-eyes-beat-a-second-family/paper/)** reports 183 replayed code-review sessions, with fresh-session controls, acceptance bars, and limitations.

[Source & architecture](https://github.com/JacobStephens2/thirdshift) · [Project](https://thirdshift.app/)

### Production impact

- **Removed ~80% of measured database query time** with three online indexes, guided by production measurements and verified with query plans.
- **Cut manifest load time from 5–7 seconds to ~1 second** and SQL statements per request from **2,650 to 183**, while preserving byte-identical HTML.
- Built isolated Docker sandboxes for non-engineering managers; the marketing workflow alone has produced **30+ pull requests merged by engineering**.
- **Instrumented 14 hosts** with Prometheus, Grafana, and Alertmanager, covering host metrics, database replication, uptime, and TLS expiry.

Most of this code is private. The **[ETA platform case study](https://stephens.page/blog/one-engineer-platform-production-systems/)** documents the problems, decisions, and measured outcomes; **[infrastructure-patterns](https://github.com/JacobStephens2/infrastructure-patterns)** shares sanitized architecture decisions, threat models, and operational review practices.

### Selected engineering work

| Project | What to look for |
| --- | --- |
| **[thirdshift](https://github.com/JacobStephens2/thirdshift)** | Rust orchestration for unattended issue-to-PR delivery: dependency scheduling, review and CI gates, repair loops, and resumable work. |
| **[infrastructure-patterns](https://github.com/JacobStephens2/infrastructure-patterns)** | Production architecture decisions and their trade-offs: tenant isolation, agent identity, deployment, and human review. |
| **[vaulted-agent](https://github.com/JacobStephens2/vaulted-agent)** | Rust launcher that resolves vault secrets into agent processes, with per-agent secret manifests and optional prompt authentication. [Product](https://vaultedagent.com/) |
| **[voice-agent-scheduling](https://github.com/JacobStephens2/voice-agent-scheduling)** | TypeScript telephone agent for Google Calendar booking: signed webhooks, explicit caller confirmation, durable reconciliation to prevent duplicate events, and bounded call costs. |
| **[muxboard](https://github.com/JacobStephens2/muxboard)** | Python dashboard for tmux sessions across a host or fleet, with browser attach, default-deny authentication, and a documented threat model. [Product](https://muxboard.dev/) |

### Product engineering

- **[Chart35](https://github.com/JacobStephens2/chart35-showcase)** - Offline-first charting with end-to-end encrypted sync across web, iOS, and Android. The public showcase explains the architecture and privacy boundaries. [Product](https://chart35.com/creighton)
- **[Thereish](https://github.com/JacobStephens2/thereish)** - A realtime couch word game in Elixir and Phoenix LiveView. Pure game rules stay separate from room processes and model calls. [Play](https://thereish.app/game) · [Write-up](https://stephens.page/blog/the-machine-grades-it-never-rules/)
- **[Cascade](https://github.com/JacobStephens2/cascade)** - A waterfall sound player with one headless Rust core and six platform shells: web, Android, macOS, Windows, iOS, and watchOS. [Architecture](https://cascade.stephens.page/architecture/) · [Apps](https://cascade.stephens.page/apps)
- **[Drome](https://github.com/JacobStephens2/drome)** - A local-first challenge tracker built for my sister, who used it through her 75-day challenge. An event-driven Rust rules engine powers native SwiftUI and WidgetKit; day-boundary math is property-tested. [Product](https://drome.day/)
- **[Sotto for Android](https://github.com/JacobStephens2/sotto-android)** - On-device text-to-speech in Kotlin with resumable narration. The local build has no `INTERNET` permission; shared test vectors keep its text pipeline equivalent to the [Python service](https://github.com/JacobStephens2/sotto).

### Upstream contributions

- **Merged and released:** [Per-profile hidden-folder support](https://github.com/sotashimozono/obsidian-remote-ssh/pull/535) in `obsidian-remote-ssh`, making selected hidden directories browsable over SSH, including agent worktrees, while preserving configuration and ignore rules. Shipped and credited in [v1.1.8](https://github.com/sotashimozono/obsidian-remote-ssh/pull/557).
- **Merged:** [MySQL 8.4 authentication fix](https://github.com/krowinski/php-mysql-replication/pull/148) in `php-mysql-replication`, enabling binlog readers to connect without downgrading server authentication.
- **Reported and validated:** [Herdr / Muse stale working-state bug](https://github.com/herdrdev/herdr/issues/3951), with reproduction evidence and workaround verification. A Herdr maintainer confirmed the bug; the Muse team shipped the fix in **Muse Code 1.2.1**.

### Published libraries in TypeScript and Go

Each library ships in both languages against shared cross-language test fixtures:

| Library | TypeScript | Go |
| --- | --- | --- |
| HMAC webhook verification | [webhook-verify](https://github.com/JacobStephens2/webhook-verify) · [npm](https://www.npmjs.com/package/@stephenspage/webhook-verify) | [webhook-verify-go](https://github.com/JacobStephens2/webhook-verify-go) |
| AES-256-GCM encryption envelopes | [webcrypto-envelope](https://github.com/JacobStephens2/webcrypto-envelope) · [npm](https://www.npmjs.com/package/@stephenspage/webcrypto-envelope) | [webcrypto-envelope-go](https://github.com/JacobStephens2/webcrypto-envelope-go) |

<details>
<summary>More projects</summary>

- **[voice-agent](https://github.com/JacobStephens2/voice-agent)** - A personal TypeScript prototype for voice-led operations and coding-agent delegation, with passkey authentication, restricted capabilities, durable task evidence, and human-reviewed promotion. Live telephone and code-change flows remain under attended acceptance testing.
- **[Quadrille](https://github.com/JacobStephens2/quadrille)** - Local-first Flutter workout tracker with SQLite persistence, optional sync, and wall-clock rest timers. The reusable [countdown-ring](https://github.com/JacobStephens2/countdown-ring) package was extracted from it.
- **[Clave](https://github.com/JacobStephens2/clave)** - Cooperative salsa card game with a headless TypeScript rules engine, server-authoritative rooms, and transactional SQLite persistence. [Play](https://clave.dance)
- **[k3s-demo](https://github.com/JacobStephens2/k3s-demo)** - A separate, non-production Kubernetes learning environment with probes, resource limits, ingress, and kustomize.

</details>

---

St. Carlo Acutis, pray for us.
