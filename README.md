### Jacob Stephens

**Safe AI automation for revenue-critical legacy systems.** I design, build, and operate production systems end to end — a multi-portal PHP / MySQL reservations platform, multi-tenant AI assistants on Docker, a Python agent-orchestration host, and an internal FastAPI / Next.js platform to replace a SaaS vendor — the stack a multi-million-dollar specialty-travel business runs on. That's the *Legacy-to-AI Bridge* problem: modernization without a rewrite, agents without blast radius, and human-in-the-loop where it matters.

Most of that work lives in private repositories. The architecture and the reasoning behind it are written up in the **[ETA Platform case study](https://stephens.page/eta-platform.html)** and in **[infrastructure-patterns](https://github.com/JacobStephens2/infrastructure-patterns)** (sanitized ADRs, a threat model for agent sandboxes, and an operational review checklist).

## Shipped apps with real users

Products I've built and shipped end to end — offline-first, client-side encrypted, and released to real users across web, iOS/watchOS, and Android.

| App | What it is | Live | Code |
|---|---|---|---|
| **Chart35** | Privacy-first Creighton Model fertility charting — offline-first PWA, end-to-end encrypted sync, provider sharing; in the App Store / Play / TestFlight, with users via organic search | [chart35.com/creighton](https://chart35.com/creighton) | [chart35-showcase](https://github.com/JacobStephens2/chart35-showcase) (public architecture & privacy slice) |
| **Drome** | Free, local-first iOS tracker for 75-day challenges — one Rust rules engine driving native SwiftUI + WidgetKit, event-sourced | [drome.day](https://drome.day) | showcase coming |

Both apps run on the same pattern I use in infra work: one core, native shells, and privacy by construction. Server-side code stays private; the public showcase demonstrates the front end and the architecture.

## Published packages

Small, dependency-free primitives extracted from that production work — each ships as a wire-compatible TypeScript + Go pair, tested against parity vectors so the two produce byte-identical output.

| Package | TypeScript (npm) | Go (pkg.go.dev) |
|---|---|---|
| HMAC webhook verifiers (GitHub / Stripe / Twilio / Mandrill) | [`@stephenspage/webhook-verify`](https://www.npmjs.com/package/@stephenspage/webhook-verify) | [`webhook-verify-go`](https://pkg.go.dev/github.com/JacobStephens2/webhook-verify-go) |
| AES-256-GCM envelope + PBKDF2 vault + zero-knowledge sealed shares | [`@stephenspage/webcrypto-envelope`](https://www.npmjs.com/package/@stephenspage/webcrypto-envelope) | [`webcrypto-envelope-go`](https://pkg.go.dev/github.com/JacobStephens2/webcrypto-envelope-go) |

TypeScript releases are published via GitHub Actions with [npm Trusted Publishing (OIDC)](https://docs.npmjs.com/trusted-publishers/) — no long-lived tokens, provenance statements on every version.

## Upstream contributions

- MySQL 8.4 `caching_sha2_password` auth-handshake fix to [`krowinski/php-mysql-replication#148`](https://github.com/krowinski/php-mysql-replication/pull/148).

More landing in the [Model Context Protocol](https://modelcontextprotocol.io/) ecosystem — that's where the "safe AI automation" thesis externally validates.

📄 **[Resume](https://resume.stephens.page)** · **[Portfolio](https://stephens.page/portfolio.html)** · **[Available for Staff / Lead platform-infra roles](mailto:jacob@stephens.page?subject=Staff%2FLead%20platform%20role)**

---

<sub>*St. Carlo Acutis, pray for us.*</sub>
