### Jacob Stephens

**Safe AI automation for revenue-critical legacy systems.** I design, build, and operate production systems end to end — a multi-portal PHP / MySQL reservations platform, multi-tenant AI assistants on Docker, a Python agent-orchestration host, and an internal FastAPI / Next.js platform to replace a SaaS vendor — the stack a multi-million-dollar specialty-travel business runs on. That's the *Legacy-to-AI Bridge* problem: modernization without a rewrite, agents without blast radius, and human-in-the-loop where it matters.

Most of that work lives in private repositories. The architecture and the
reasoning behind it are written up in the **[ETA Platform case study](https://stephens.page/eta-platform.html)**
and in **[infrastructure-patterns](https://github.com/JacobStephens2/infrastructure-patterns)** (sanitized ADRs, a threat model for agent sandboxes, and an operational review checklist).

## Published packages

Small, dependency-free primitives extracted from production use — each ships as a wire-compatible TypeScript + Go pair, tested against parity vectors so the two produce byte-identical output.

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

Outside work I ship cross-platform apps with a privacy-first bent — client-side
encryption, offline-first storage, and one core driving many native shells.
A few are pinned below.

---

<sub>*St. Carlo Acutis, pray for us.*</sub>
