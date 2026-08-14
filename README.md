### Jacob Stephens

**Safe AI automation for revenue-critical legacy systems.** I design, build, and operate production systems end to end — a multi-portal PHP / MySQL reservations platform, multi-tenant AI assistants on Docker, and a Python agent-orchestration host, for a multi-million-dollar specialty-travel business. That's the *Legacy-to-AI Bridge* problem: modernization without a rewrite, agents without blast radius, and human-in-the-loop where it matters.

Most of that work lives in private repositories. The architecture and the reasoning behind it are written up in the **[ETA Platform case study](https://stephens.page/eta-platform.html)** and in **[infrastructure-patterns](https://github.com/JacobStephens2/infrastructure-patterns)** (sanitized ADRs, a threat model for agent sandboxes, and an operational review checklist).

## Shipped apps

Products I've built and shipped end to end — offline-first, client-side encrypted, and released to real users across web, iOS/watchOS, and Android.

| App | What it is | Live | Code |
|---|---|---|---|
| **Chart35** | Privacy-first Creighton Model fertility charting — offline-first PWA, end-to-end encrypted sync, provider sharing; in the App Store / Play / TestFlight, with users via organic search | [chart35.com/creighton](https://chart35.com/creighton) | [chart35-showcase](https://github.com/JacobStephens2/chart35-showcase) (public architecture & privacy slice) |
| **Drome** | Free, local-first iOS tracker for 75-day challenges — one Rust rules engine driving native SwiftUI + WidgetKit, event-sourced | [drome.day](https://drome.day) | showcase coming |
| **Cascade** | Waterfall white-noise player — one headless Rust core driving six native shells across web (PWA), Android, macOS, Windows, iOS, and watchOS; a headless-core + native-UI kata | [cascade.stephens.page](https://cascade.stephens.page) | [cascade](https://github.com/JacobStephens2/cascade) |

Both apps run on the same pattern I use in infra work: one core, native shells, and privacy by construction. Server-side code stays private; the public showcase demonstrates the front end and the architecture.

## In the works

Apps I'm building toward a public release; the code stays private for now, but each has a public home you can follow.

| App | What it is | Where to follow |
|---|---|---|
| **Quadrille** | Lifting log — a native iOS + watchOS weightlifting tracker with a shared core and integrated Watch app, built to ship to the App Store | [quadrille.app](https://quadrille.app) |
| **Nightloch** | Partner-locked digital accountability curfews — WireGuard + AdGuard Home DNS filtering with a Go control plane | [nightloch.app](https://nightloch.app) |
| **Clave** | Cooperative salsa partner-dance card game for two players, with a headless engine and two-device rooms | [clave.dance](https://clave.dance/) |

## Production tools

Command-line and self-hosted tools I built for my own agent + infra workflow, in daily production use.

| Tool | What it is | Code |
|---|---|---|
| **vaulted-agent-launcher** (`va`) | Launches Claude Code, Codex, and Grok with vault-resolved secrets in-process — per-agent blast radius, no `.env` files or vault tokens on disk (1Password, Bitwarden SM, pass, sops; macOS + Linux) | [vaulted-agent-launcher](https://github.com/JacobStephens2/vaulted-agent-launcher) |
| **muxboard** | Flask-embeddable web dashboard over `tmux` for one host or a fleet, live in-browser attach — default-deny auth, attach caps, documented threat model | [muxboard.dev](https://muxboard.dev) · [code](https://github.com/JacobStephens2/muxboard) |
| **skills** | Reusable SKILL.md agent skills for application planning, adversarial review, and adjudication — used across my own Claude Code / Codex workflows | [skills](https://github.com/JacobStephens2/skills) |
| **inkvoke** | Single-binary, agent-friendly Go CLI for OpenAI's image models (`gpt-image-2` by default) — generate from prompts, edit existing images, and run batches from a JSON manifest | [inkvoke.dev](https://inkvoke.dev) · [code](https://github.com/JacobStephens2/inkvoke) |

## Published packages

Small, dependency-free primitives extracted from that production work — each ships as a wire-compatible TypeScript + Go pair, tested against parity vectors so the two produce byte-identical output.

| Package | TypeScript (npm) | Go (pkg.go.dev) |
|---|---|---|
| HMAC webhook verifiers (GitHub / Stripe / Twilio / Mandrill) | [`@stephenspage/webhook-verify`](https://www.npmjs.com/package/@stephenspage/webhook-verify) | [`webhook-verify-go`](https://pkg.go.dev/github.com/JacobStephens2/webhook-verify-go) |
| AES-256-GCM envelope + PBKDF2 vault + zero-knowledge sealed shares | [`@stephenspage/webcrypto-envelope`](https://www.npmjs.com/package/@stephenspage/webcrypto-envelope) | [`webcrypto-envelope-go`](https://pkg.go.dev/github.com/JacobStephens2/webcrypto-envelope-go) |

TypeScript releases are published via GitHub Actions with [npm Trusted Publishing (OIDC)](https://docs.npmjs.com/trusted-publishers/) — no long-lived tokens, provenance statements on every version.

## Upstream contributions

- MySQL 8.4 `caching_sha2_password` auth-handshake fix to [`krowinski/php-mysql-replication#148`](https://github.com/krowinski/php-mysql-replication/pull/148).
- Kimi Code `kimi -p` env-key regression fix (agent-core-v2 auth gate ignored `process.env`) to [`MoonshotAI/kimi-code#2746`](https://github.com/MoonshotAI/kimi-code/pull/2746) (issue [#2745](https://github.com/MoonshotAI/kimi-code/issues/2745)).
- SwarmForge agent-lifecycle bug report: unexpected exit of the cleanup-owner agent triggers an unconditional teardown of every swarm session, killing active workers — reported at [`unclebob/swarm-forge#49`](https://github.com/unclebob/swarm-forge/issues/49) with a proposal to decouple whole-swarm teardown from the cleanup-owner's process lifecycle.

More landing in the [Model Context Protocol](https://modelcontextprotocol.io/) ecosystem — that's where the "safe AI automation" thesis externally validates.

Available for platform-infra roles.

📄 **[Resume](https://resume.stephens.page)** · **[Portfolio](https://stephens.page/portfolio.html)** · **[Available for Staff / Lead platform-infra roles](mailto:jacob@stephens.page?subject=Staff%2FLead%20platform%20role)**

---

*St. Carlo Acutis, pray for us.*
