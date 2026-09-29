# Roadmap

Timeline estimate: ~4–7 months of learning, ~6–11 months to first offer including the job search, given your existing diploma and basics.

---

## Phase 0 — Setup (Days 1–3)

**Folder:** `phase-0-setup/`

- [ ] Install Go, VS Code + Go extension, Git
- [ ] Push this repo to GitHub, make first commit
- [ ] Set your AI-assistant rule: use it to explain/review code, never to write code you haven't read and understood line by line
- [ ] Start `learning-log/` — one entry per session

**Resources:**
- Go install — https://go.dev/doc/install
- Git basics (if rusty) — https://git-scm.com/book/en/v2 (chapters 1–3)

---

## Phase 1 — Go Fundamentals (Weeks 1–2)

**Folder:** `phase-1-go-fundamentals/` · **Project:** `projects/01-concurrent-cli-tools/`

Focus: syntax, structs, interfaces, error handling, goroutines/channels. No web frameworks yet.

Build 3–4 CLI tools using real concurrency:
- Concurrent file word-counter (goroutines + channels)
- TCP port scanner (plays to your networking background)
- Concurrent link checker / simple web scraper

**Resources:**
1. Tour of Go (free, official, do first) — https://go.dev/tour/
2. *Learning Go* by Jon Bodner (O'Reilly) — deep on interfaces, error handling, concurrency
3. Gophercises (free) — https://gophercises.com/
4. Exercism Go track (free, mentor feedback) — https://exercism.org/tracks/go
5. Effective Go (idioms, once basics feel comfortable) — https://go.dev/doc/effective_go

**Checkpoint:** Explain goroutines vs OS threads, and Go's explicit error handling, without looking anything up.

---

## Phase 2 — Raw HTTP/Networking in Go (Weeks 3–4)

**Folder:** `phase-2-http-networking/` · **Project:** `projects/02-raw-http-api/`

Focus: build an HTTP server using only `net/http`. No framework — understand what a framework abstracts before using one.

Build: REST API, 3–4 endpoints, in-memory storage, proper routing/JSON/status codes.

**Resources:**
1. `net/http` official docs — https://pkg.go.dev/net/http
2. *Let's Go* by Alex Edwards — https://lets-go.alexedwards.net/
3. MDN HTTP docs (protocol refresher) — https://developer.mozilla.org/en-US/docs/Web/HTTP

**Checkpoint:** Explain what happens between a client request and your server's response at the socket level.

---

## Phase 3 — Databases (Weeks 5–7)

**Folder:** `phase-3-databases/` · **Project:** `projects/03-postgres-backed-api/`

Focus: PostgreSQL, SQL, indexing, migrations, connection pooling.

Build: turn Phase 2's API into a persisted service — CRUD + at least one non-trivial query (join or aggregation).

**Resources:**
1. Official PostgreSQL tutorial — https://www.postgresql.org/docs/current/tutorial.html
2. *The Art of PostgreSQL* by Dimitri Fontaine
3. `pgx` driver docs — https://github.com/jackc/pgx
4. `golang-migrate` — https://github.com/golang-migrate/migrate

**Checkpoint:** Explain what an index does and why a query is slow without one; you've written migrations by hand.

---

## Phase 4 — Infrastructure Basics (Weeks 8–10)

**Folder:** `phase-4-infrastructure/` · **Project:** `projects/04-dockerized-service/`

Focus: Docker, basic CI, ONE of Redis or a simple queue.

Build: Dockerfile + docker-compose (API + Postgres), GitHub Actions running tests on push, Redis for caching/rate-limiting on one endpoint.

**Resources:**
1. Docker "Get Started" — https://docs.docker.com/get-started/
2. GitHub Actions quickstart — https://docs.github.com/en/actions/quickstart
3. Redis "Introduction" — https://redis.io/docs/latest/develop/get-started/

**Checkpoint:** Explain image vs container, and why a Dockerfile builds in layers.

---

## Phase 5 — Capstone Project (Weeks 11–16)

**Folder:** `phase-5-capstone/` · **Project:** `projects/05-capstone-llm-service/`

Build: Go backend calling an LLM API, basic RAG (embeddings + vector search via pgvector), proper timeout/retry handling for the upstream API. Deployed to a public URL.

**Resources:**
1. Anthropic API docs — https://docs.claude.com
2. OpenAI API docs (comparison) — https://platform.openai.com/docs
3. pgvector — https://github.com/pgvector/pgvector
4. Fly.io deploy docs — https://fly.io/docs/ · or Railway — https://docs.railway.com/

**Deliverable:** deployed live URL, README with every architecture decision explained, fully defensible in an interview.

---

## Phase 6 — Python + Distributed Systems Depth (Months 5–7)

**Folder:** `phase-6-python-and-distributed-systems/`

Python (30–45 min/day, parallel track):
1. *Python Crash Course* by Eric Matthes
2. Apply immediately: script against your own APIs, then redo the LLM integration in Python for comparison

Distributed systems (1 chapter/week, don't binge):
1. *Designing Data-Intensive Applications* by Martin Kleppmann — start month 3–4, finish by month 7

Kubernetes (month 6–7, not earlier):
1. Kubernetes the Hard Way — https://github.com/kelseyhightower/kubernetes-the-hard-way
2. Deploy your capstone onto a local cluster (`kind` or `minikube`)

Observability:
1. Prometheus getting started — https://prometheus.io/docs/prometheus/latest/getting_started/
2. Grafana getting started — https://grafana.com/docs/grafana/latest/getting-started/
3. Apply both to your own deployed service

---

## Phase 7 — Job Search (Month 8+, runs parallel with continued building)

**Folder:** `phase-7-job-search/`

Days 1–30: finish 2 portfolio-quality projects, clean up GitHub (pin best repos, real READMEs), rewrite resume around what you built.

Ongoing: 100–200 tailored applications over months, not a burst of 20. Target small startups, IT/infrastructure-adjacent companies, known junior-friendly remote-first companies (GitLab, Zapier, Shopify, Cloudflare). Get human code review throughout. Practice explaining your capstone's trade-offs out loud.

**Resources:** r/golang, Gophers Slack — for feedback and networking.

---

## Non-negotiables (repeat from README)

1. Commit and log almost daily.
2. Deploy everything publicly.
3. Never accept AI code you can't explain.
4. Get human feedback, not just AI feedback.
5. Write the learning log entry every session.
