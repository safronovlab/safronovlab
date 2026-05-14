<div align="center">
# OLEG SAFRONOV

**Full-cycle engineer**
**Senior Backend · AI Integration**

`Production-ready systems from scratch: architecture → code → deployment → security`

**Specialty:** AI/LLM integrations · Multi-model pipelines · Business process automation

</div>

---

<div align="center">

| 4 | 4 | 4 | 5 |
|:---:|:---:|:---:|:---:|
| **years**<br>commercial | **contracts**<br>5.0 rating | **client**<br>countries | **portfolio**<br>projects |

**USA · United Kingdom · Canada · Poland**

</div>

---

### Download portfolio

A full version of this portfolio is available as a print-ready A4 PDF.

**[Download portfolio (PDF, English)](portfolio-ENG.pdf)**

---

## About

Senior Backend engineer working in Python. I cover the full cycle: design, code, tests, deployment, monitoring, support. 4 years of commercial experience, 5 completed projects for clients in the USA, United Kingdom, Canada and Poland.

**How I work.** Documentation and tests come first, then code. Every project ships with a runbook.

**Backend and architecture.** Python (FastAPI, Django, Flask), async I/O on asyncpg, httpx, aiohttp, aiogram, uvloop. Queues: Celery, RQ, Dramatiq, Redis, RabbitMQ. APIs: REST, gRPC, GraphQL, WebSockets. Auth: JWT, OAuth2, OpenID Connect. Clean Architecture, Hexagonal, DDD where it fits.

**Data and quality.** PostgreSQL, MySQL, ClickHouse, MongoDB, Redis, S3. Vector DBs for RAG: pgvector, Pinecone, Weaviate, Chroma. Tests on pytest up to 320 per project, static analysis (mypy strict, pyright, ruff, bandit), pre-commit hooks, PR review.

**AI and agents.** I work with Anthropic Claude (Opus, Sonnet, Haiku) through Claude API, Claude Code and Claude Agent SDK. I set up MCP servers. I build multi-agent systems with tool use and function calling in production. RAG with vector DBs, two-pass filtering, prompt caching, quality and cost evaluation against metrics. I integrate AI into existing products and business processes.

**Frontend and specialties.** React 19, Next.js 14, TypeScript, Tailwind, PWA when the project needs full-stack work. Computer Vision: OpenCV, scikit-image, LAB color, Delta-E. Web3: Polkadot.js, Bittensor RPC.

**DevOps.** I handle infrastructure myself. AWS, Hetzner, DigitalOcean, Docker, basic Kubernetes, Terraform, Ansible. Reverse proxy: nginx, Traefik. CI/CD: GitHub Actions, GitLab CI.

**Security.** Background in information security (Russian University of Transport, honors degree). I apply it on security-critical work: Fernet/AES encryption, HMAC webhook signatures, RLS policy audits, threat modeling, server hardening (SSH keys, fail2ban, ufw, AppArmor), secret management with Vault and SOPS.

**Rust.** Performance-critical modules in Rust (Tokio, Serde).

---

## Technology stack

### Backend — primary expertise
```
Python 3.12 · FastAPI · Django · Flask · aiogram 3 · aiohttp · httpx
asyncpg · SQLAlchemy · Tortoise ORM · Pydantic v2 · msgspec · uvloop
Clean Architecture · Hexagonal · DDD
```

### APIs · queues · brokers
```
REST · gRPC · GraphQL · WebSockets · Server-Sent Events
Celery · RQ · Dramatiq · RabbitMQ · Redis Pub/Sub
JWT · OAuth2 · OpenID Connect
```

### AI · agents
```
Anthropic Claude · Claude Code · Claude Agent SDK
MCP servers · Tool use · Function calling · Multi-agent
OpenRouter · RAG · pgvector · Prompt eval
Business automation
```

### Data · storage
```
PostgreSQL · MySQL · ClickHouse · MongoDB · Redis
Upstash · SQLite (WAL) · Supabase · S3 / MinIO · Alembic
```

### Frontend
```
React 19 · Next.js 14 · TypeScript · Tailwind CSS
Vite · TanStack Query · Web Workers · PWA · Recharts
```

### DevOps · infrastructure
```
AWS · Docker · Kubernetes · Terraform · Ansible
Hetzner · DigitalOcean · Coolify · Vercel
nginx · Traefik · Caddy · Linux / Ubuntu · Let's Encrypt
```

### CI/CD · observability
```
GitHub Actions · GitLab CI
Prometheus · Grafana · Loki · Sentry · OpenTelemetry
Structured logging · pre-commit hooks
```

### Security · quality
```
Fernet / AES · Server hardening · HMAC / Webhooks · Vault / SOPS
mypy strict · pyright · ruff · bandit · RLS audit · Threat modeling
```

### Computer vision · Web3
```
OpenCV · scikit-learn · scikit-image · NumPy
LAB K-means · Delta-E 2000
Polkadot.js · Bittensor RPC · Wallet integrations
```

### Rust — performance-critical modules
```
Tokio · Serde
```

---

## Selected projects

### Case 01 / 05 — AI Gateway

`USA · San Jose, CA · Silicon Valley` `2.5 months` `Tech company · B2B SaaS`

**Async API gateway between business logic and LLM providers**

**The brief.** The client needed a single intelligent proxy layer between their internal services and external LLM providers (through Portkey). Goals: centralized logging, guardrail policies, key encryption, web admin UI. No existing codebase. Started from an empty folder.

**What I built.**
- Designed Clean Architecture with 4 layers (domain → services → infrastructure → api). Each layer free of external dependencies.
- Implemented async API end-to-end on FastAPI + httpx + SQLAlchemy Async + aiosqlite (PostgreSQL-ready).
- Added Fernet encryption for provider API keys in the database. Keys never sit in plaintext.
- Built the guardrail system with policies, cloud sync, runtime enable / disable.
- Built the web admin UI for managing providers, policies, log review and statistics.
- Deployed on AWS (EC2, security groups, SSL, monitoring) plus webhook signature verification through X-Webhook-Secret. Handed over full access and runbook.
- Covered the code with ~120 tests (unit + integration), pre-commit hooks with mypy strict, ruff, bandit. Tests written before code based on the contract in ARCHITECTURE.md.

**Outcome.** ~120 tests · 4 architecture layers · 100% production-ready (AWS + UI + docs)

> "Quality work delivered, on time. Oleg is great to work with."
> — Client review · 5.0 / 5.0 · AWS / DevOps engagement

---

### Case 02 / 05 — Bulk Recolor

`USA · Lititz` `3.5 months` `Streetwear / sneaker brand · E-commerce`

**Computer vision tool for batch design recoloring**

**The brief.** The client (a streetwear brand with weekly drops) had a v1 recolor tool that broke on three categories of images. The job: replace it with v2 that fixes all three failures and runs in production. Fixed-price contract.

**What I built.**
- Diagnosed three failure modes in v1: whole-image bleed, dotted edge artifacts, cross-design hex drift.
- Built three algorithms with regression tests on the 6 previously failing designs:
  - Connected-region flood fill (`cv2.floodFill`) instead of global hex match: bleed fixed.
  - Edge-aware blending that respects alpha boundaries: fringe artifacts fixed.
  - LAB-space K-means clustering + Delta-E 2000 palette mapping: cross-design drift fixed.
- Built the full-stack app: FastAPI backend + React 19 frontend (Vite, Tailwind) + RQ queue on Redis + nginx reverse proxy.
- Added click-fix mode: user clicks the bad region, backend flood-fills just that connected component.
- Covered the code with ~320 tests (unit + integration + acceptance) and shipped everything as a Docker Compose stack.

**Outcome.** ~320 tests · < 60s end-to-end (20 designs on 2 GB VPS) · < 200ms click-fix latency

> "Oleg picked up where our previous developer left off and delivered a much more reliable tool. He took the time to understand the specific failure modes, asked the right questions, and built something that actually works for our workflow."
> — Client review · 5.0 / 5.0

---

### Case 03 / 05 — TaoScope

`Poland · EU` `3.5 months` `Web3 / Blockchain · LIVE: taoscope.com`

**Real-time Bittensor blockchain explorer**

**The brief.** The client needed a full-featured public explorer for the Bittensor network with real-time data on subnets, validators, miners, prices and historical metrics. From scratch, first line of code to an optimized production deployment accessible globally.

**What I built.**
- Built a Next.js 14 app with App Router on TypeScript: 10+ pages, server API routes, PWA with offline mode.
- Integrated the blockchain: WebSocket client to Bittensor mainnet through Polkadot.js API, custom Bittensor types, auto-reconnect with fallback RPC.
- Set up dual-layer caching: Upstash Redis (edge) + in-memory fallback. TTLs per data type: 30s / 60s / 120s / 300s.
- Connected 3 wallets: Polkadot.js, Talisman, SubWallet. USD portfolio, stake balance, delegations.
- Added historical charts for price and emissions (24h / 7d / 30d / 90d / 1y), delegation calculator with compound interest.
- Shipped to production through Vercel (PWA-installable, service worker, offline fallback) and covered the code with ~80 tests (Vitest unit + Playwright e2e), TypeScript strict, ESLint. API route contracts documented before implementation.

**Outcome.** 100+ subnets monitored real-time · 10+ pages including wallet · LIVE at [taoscope.com](https://taoscope.com)

> "Oleg shipped the full Bittensor explorer on time. The Polkadot.js integration was the tricky part and he handled it cleanly. Site has been running in production for months with minimal maintenance on our side."
> — Client review · 5.0 / 5.0

---

### Case 04 / 05 — Production Incident Response · SEV-1

`United Kingdom · Huddersfield` `1 month` `Community SaaS platform · 180K+ users`

**Forensic diagnosis and recovery plan for a revenue decline**

**The brief.** The client experienced an unexpected revenue decline of 50 to 60 percent over 35 days. The source was unclear: SEO problem, technical failure, or an algorithmic penalty from Google. I was hired to run the forensic investigation and deliver an engineering recovery plan.

**What I did.**
- Ran root cause analysis across the Next.js + Supabase + Netlify + Klaviyo + Stripe stack.
- Identified two independent root causes overlapping in the same time window:
  - Phase 1 (35 days): failed production build, frontend stuck in infinite loading.
  - Phase 2 (6 days): legacy Supabase API keys auto-disabled, Edge Functions stopped working (100% failure rate).
- Audited Supabase RLS policies, inventoried Edge Function secrets, reviewed failed Stripe captures.
- Correlated GSC data, server logs, edge logs and Stripe logs against the incident timeline.
- Delivered the Diagnostic Report: 4 sections + 4 appendices, repair strategy, SRE risk assessment.

**Outcome.** 2 independent root causes · 41 days analyzed · recovery plan delivered to a 180K+ user platform

> "Could not recommend Oleg enough. He understood the issue, was fast, precise, and knew exactly which parts of our infrastructure needed to be investigated to solve our revenue issue."
> — Client review · 5.0 / 5.0

---

### Case 05 / 05 — AI Lead Filter Bot

`Canada · Kitchener` `2.5 months` `Tech client · Sales automation`

**Multi-model AI engine for filtering incoming leads with Telegram delivery**

**The brief.** The client needed an AI system for automatic filtering of incoming leads from an external source, with two-stage analysis to save on tokens, delivering relevant results into Telegram. It had to fit a minimal VPS, including full server setup and security hardening.

**What I built.**
- Designed a two-pass AI pipeline with different models per stage:
  - Stage 1: cheap / fast model, rough filtering of clearly irrelevant leads.
  - Stage 2: premium model, deep analysis only on items that passed stage 1 (~20-30% of traffic).
- Performance engineering to the limit: asyncpg without ORM (binary protocol, prepared statements), msgspec instead of Pydantic (×3 faster), uvloop, slotted-frozen dataclasses.
- Single HTTP stack: aiogram serves the built-in `aiohttp.web` for both Telegram polling and webhook (no FastAPI on top).
- Covered the code with ~140 tests (unit + integration through testcontainers with real Postgres). Tests written before code based on PIPELINE.md and DATABASE.md. Static analysis: mypy strict, ruff, bandit, radon, vulture, xenon.
- Deployed on VPS with Docker multi-stage + Coolify, full server hardening, runbook for operations.

**Outcome.** 50 MB resident memory in production · p99 webhook ingestion < 50ms · p95 end-to-end through LLM stages < 30s

> "Solid execution end-to-end. Oleg owned the architecture, the code, and the deployment. The bot runs on minimal resources and the runbook he left made handoff smooth. Easy to work with across time zones."
> — Client review · 5.0 / 5.0

---

## Client testimonials

**4 contracts · 5.0 average · all positive reviews**

> ★★★★★ **5.0** — Forensic Search Analyst for Revenue & Google Traffic Diagnosis
>
> "Could not recommend Oleg enough. He understood the issue, was fast, precise, and knew exactly which parts of our infrastructure needed to be investigated to solve our revenue issue."
>
> `Solution Oriented` · `Accountable for Outcomes` · `Detail Oriented` — Client review · UK · Apr 2026

> ★★★★★ **5.0** — Tool Development for Bulk Image Upload and Color Management
>
> "Oleg picked up where our previous developer left off and delivered a much more reliable tool. He took the time to understand the specific failure modes, asked the right questions, and built something that actually works for our workflow."
>
> `Reliable` · `Detail Oriented` · `Accountable for Outcomes` — Client review · USA · Apr 2026

> ★★★★★ **5.0** — AWS · DevOps Engineering
>
> "On time deliverable with quality."
>
> `Reliable` · `Committed to Quality` · `Accountable for Outcomes` — Client review · USA · Apr 2026

> ★★★★★ **5.0** — AWS · DevOps Engineering
>
> "Quality work delivered, on time. Oleg is great to work with."
>
> `Reliable` · `Collaborative` · `Committed to Quality` — Client review · USA · Mar 2026

---

## Get in touch

**Ready to discuss your project.**

```
Telegram     @safronov_oleg
Email        safronovoleg1@gmail.com
GitHub       github.com/safronovlab
```

<sub>Oleg Safronov · Senior Backend · AI Integration · 2026</sub>
