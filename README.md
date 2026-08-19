### Jacob Stephens

**Safe AI automation for revenue-critical legacy systems.** I'm the sole engineering owner of a multi-million-dollar specialty-travel stack — a multi-portal PHP / MySQL reservations platform, multi-tenant AI assistants on Docker, and a Python agent-orchestration host — and I run the whole thing behind a human merge gate.

- **~80% of measured query load removed** across the reservations platform via three zero-downtime online-DDL indexes (before/after EXPLAIN + slow-log deltas, no customer-visible cutover).
- **Manifest page: 5–7s → ~1s**, SQL / request 2,650 → 183, byte-identical HTML — the caching layer is verified equivalent, not just faster ([case study](https://stephens.page/eta-platform.html)).
- **14 manager-prototyped features shipped through a human merge gate**, zero agent-caused incidents in production ([factory ADR: shared collector seam](https://github.com/JacobStephens2/infrastructure-patterns/blob/main/adr/0021-shared-collector-seam-over-direct-backend-wiring.md), [scoped system user ADR](https://github.com/JacobStephens2/infrastructure-patterns/blob/main/adr/0005-scoped-system-user-over-service-account.md)).
- **14-host observability fleet + 3 enterprise migrations** (Bitbucket → GitHub, WordPress hardening, Tailscale rollout), no customer-visible outage.

Most of that work lives in private repos. The architecture and the reasoning behind it are written up in the **[ETA Platform case study](https://stephens.page/eta-platform.html)** and in **[infrastructure-patterns](https://github.com/JacobStephens2/infrastructure-patterns)** — sanitized ADRs, a threat model for agent sandboxes, and an operational review checklist.

### Public artifacts that prove the thesis

| Repo | What it proves | Evidence |
|---|---|---|
| **[vaulted-agent-launcher](https://github.com/JacobStephens2/vaulted-agent-launcher)** (`va`) | Per-agent blast radius: launches Claude Code, Codex, Grok, and Kimi with vault-resolved secrets in-process — no `.env` files or vault tokens on disk (1Password, Bitwarden SM, `pass`, sops; macOS + Linux) | Design issues [#70](https://github.com/JacobStephens2/vaulted-agent-launcher/issues/70), [#72](https://github.com/JacobStephens2/vaulted-agent-launcher/issues/72) · [installer hosting docs](https://github.com/JacobStephens2/vaulted-agent-launcher/blob/main/docs/hosting-the-installer.md) |
| **[muxboard](https://github.com/JacobStephens2/muxboard)** | Babysitting long-running agents: Flask-embeddable web dashboard over `tmux` for one host or a fleet, live in-browser attach — default-deny auth, attach caps, documented threat model | [muxboard.dev](https://muxboard.dev/) |
| **[infrastructure-patterns](https://github.com/JacobStephens2/infrastructure-patterns)** | Sanitized ADRs and the operational review checklist from the ETA factory — the human merge gate, in writing | [ADR index](https://github.com/JacobStephens2/infrastructure-patterns) |
| **[chart35-showcase](https://github.com/JacobStephens2/chart35-showcase)** | Privacy-by-construction: offline-first PWA, end-to-end encrypted sync, provider sharing. **52 accounts, 40 verified, 47 synced** on [Chart35](https://chart35.com/creighton) via organic search alone | Architecture + privacy slice public; production data stays E2E-encrypted so the server sees only account metadata and encrypted-snapshot sizes |
| **[cascade](https://github.com/JacobStephens2/cascade)** | Headless-core + native-UI kata: one Rust core, **2 shipped shells (Web PWA, Android)**, 4 architected to extend (macOS, Windows, iOS, watchOS) | [cascade.stephens.page](https://cascade.stephens.page/) · [architecture](https://cascade.stephens.page/architecture/) |
| **[k3s-demo](https://github.com/JacobStephens2/k3s-demo)** | Production-grade k8s manifests: probes, resource limits, hardened `securityContext`, HPA, ingress, kustomize; statically validated with kubeconform | [Dockerfile](https://github.com/JacobStephens2/k3s-demo/blob/main/Dockerfile) |

### Upstream contributions

- **MySQL 8.4 `caching_sha2_password` auth-handshake fix** in `krowinski/php-mysql-replication` — [PR #148](https://github.com/krowinski/php-mysql-replication/pull/148). The library's handshake ignored the new default plugin; patched the auth-switch path so binlog readers connect to MySQL 8.4 without downgrading server auth.
- **Kimi Code `kimi -p` env-key regression** in `MoonshotAI/kimi-code` — [PR #2746](https://github.com/MoonshotAI/kimi-code/pull/2746) closing [issue #2745](https://github.com/MoonshotAI/kimi-code/issues/2745). `agent-core-v2`'s auth gate resolved credentials from `args.provider?.env ?? {}` and ignored `process.env`, breaking headless `-p` runs; fixed the resolver to fall through to `process.env`.
- **SwarmForge whole-swarm teardown bug** in `unclebob/swarm-forge` — [issue #49](https://github.com/unclebob/swarm-forge/issues/49). Unexpected exit of the cleanup-owner agent triggered an unconditional teardown of every swarm session; proposed decoupling teardown from the cleanup-owner's process lifecycle.

More landing in the [Model Context Protocol](https://modelcontextprotocol.io/) ecosystem — that's where the "safe AI automation" thesis externally validates.

### Also shipped

<details>
<summary>Products, tools, and published packages — click to expand</summary>

**Products**

- **[Chart35](https://chart35.com/creighton)** — privacy-first Creighton Model fertility charting; App Store / Play / TestFlight ([chart35-showcase](https://github.com/JacobStephens2/chart35-showcase))
- **[Drome](https://drome.day/)** — local-first iOS tracker for 75-day challenges; one Rust rules engine, native SwiftUI + WidgetKit, event-sourced
- **[Cascade](https://cascade.stephens.page/)** — waterfall white-noise player ([cascade](https://github.com/JacobStephens2/cascade))

**Tools in daily production use**

- **[skills](https://github.com/JacobStephens2/skills)** — reusable SKILL.md agent skills for application planning, adversarial review, and adjudication
- **[inkvoke](https://github.com/JacobStephens2/inkvoke)** — single-binary, agent-friendly Go CLI for OpenAI's image models; prompt / edit / manifest-batch ([inkvoke.dev](https://inkvoke.dev/))

**Published packages** — wire-compatible TypeScript + Go pairs, tested against parity vectors for byte-identical output. TypeScript releases publish via [npm Trusted Publishing (OIDC)](https://docs.npmjs.com/trusted-publishers/) — no long-lived tokens, provenance on every version.

| Package | TypeScript (npm) | Go (pkg.go.dev) |
|---|---|---|
| HMAC webhook verifiers (GitHub / Stripe / Twilio / Mandrill) | [`@stephenspage/webhook-verify`](https://www.npmjs.com/package/@stephenspage/webhook-verify) | [`webhook-verify-go`](https://pkg.go.dev/github.com/JacobStephens2/webhook-verify-go) |
| AES-256-GCM envelope + PBKDF2 vault + zero-knowledge sealed shares | [`@stephenspage/webcrypto-envelope`](https://www.npmjs.com/package/@stephenspage/webcrypto-envelope) | [`webcrypto-envelope-go`](https://pkg.go.dev/github.com/JacobStephens2/webcrypto-envelope-go) |

</details>

---

📄 **[Resume](https://resume.stephens.page/)** · **[Portfolio](https://stephens.page/portfolio.html)** · **[Available for Staff / Lead platform-infra roles](mailto:jacob@stephens.page?subject=Staff%2FLead%20platform%20role)**

St. Carlo Acutis, pray for us.
