# Backend/Systems Engineer Roadmap
### Starting point: ICT Level 6 diploma, basic CLI programming (variables, functions, arrays, pointers), strong networking/Linux/hardware background
### Target: Job-ready junior backend/infrastructure engineer in ~4-7 months of learning, first offer in ~6-11 months total

---

## PHASE 0 — Setup (Days 1-3)

- [ ] Install Go, VS Code + Go extension, Git
- [ ] Create GitHub account, make first commit (even `hello world`)
- [ ] Set your AI-assistant rule now: use it to explain/review code, never to write code you haven't read and understood line by line
- [ ] Create a `learning-log` repo — one entry per session (2-3 sentences: what you built, what broke, what you learned)

**Resources:**
- Go install: https://go.dev/doc/install
- Git basics (if rusty): https://git-scm.com/book/en/v2 (chapters 1-3 only)

---

## PHASE 1 — Go Fundamentals (Weeks 1-2, compressed from 3 since you know variables/functions/arrays/pointers)

**Focus:** Go syntax, structs, interfaces, error handling, goroutines/channels. Don't touch web frameworks yet.

**What to build:** 3-4 small CLI tools using concurrency for something real:
- A concurrent file word-counter (goroutines + channels)
- A simple TCP port scanner (plays directly to your networking background)
- A basic concurrent web scraper/link checker

**Resources:**
1. **Tour of Go** (free, official, do this first) — https://go.dev/tour/
2. **"Learning Go" by Jon Bodner** (O'Reilly) — the best current book, go deep on chapters covering interfaces, error handling, and concurrency
3. **Gophercises** (free) — https://gophercises.com/ — exercise-driven, built specifically for learning Go by building
4. **Exercism Go track** (free, includes mentor feedback) — https://exercism.org/tracks/go — this solves the "learning in isolation" problem directly
5. Skim **Effective Go** (official docs) for idioms once basics feel comfortable — https://go.dev/doc/effective_go

**Checkpoint:** You should be able to explain goroutines vs OS threads, and why Go's explicit error handling exists, without looking anything up.

---

## PHASE 2 — Raw HTTP/Networking in Go (Weeks 3-4)

**Focus:** Build an HTTP server using only `net/http`, no framework — understand what a framework abstracts before you use one.

**What to build:** A REST API with 3-4 endpoints (no database yet — in-memory storage is fine), with proper routing, JSON encoding/decoding, and status codes.

**Resources:**
1. `net/http` official docs — https://pkg.go.dev/net/http (you have the networking background to actually read this properly)
2. **"Let's Go" by Alex Edwards** — excellent, practical, teaches real HTTP service patterns in Go without unnecessary framework dependency: https://lets-go.alexedwards.net/
3. HTTP protocol refresher if needed: MDN HTTP docs — https://developer.mozilla.org/en-US/docs/Web/HTTP

**Checkpoint:** You can explain what happens between a client sending a request and your Go server responding, at the byte/socket level, not just "the framework handles it."

---

## PHASE 3 — Databases (Weeks 5-7)

**Focus:** PostgreSQL fundamentals, SQL, indexing basics, migrations, connection pooling.

**What to build:** Turn your Phase 2 API into a real persisted service — CRUD backed by Postgres, at least one non-trivial query (a join, an aggregation).

**Resources:**
1. Official PostgreSQL tutorial — https://www.postgresql.org/docs/current/tutorial.html
2. **"The Art of PostgreSQL" by Dimitri Fontaine** — deeper, excellent for understanding *why*, not just syntax
3. Go + Postgres: `database/sql` docs + `pgx` driver docs — https://github.com/jackc/pgx
4. Migrations tool: `golang-migrate` — https://github.com/golang-migrate/migrate

**Checkpoint:** You can explain what an index does and why a query is slow without one, and you've written migrations by hand at least once.

---

## PHASE 4 — Infrastructure Basics (Weeks 8-10)

**Focus:** Docker (containerize your API), basic CI, and ONE of Redis or a simple queue — not both.

**What to build:** Dockerfile + docker-compose for your API + Postgres running together locally. GitHub Actions workflow that runs tests on push. Add Redis for caching or rate-limiting on one endpoint.

**Resources:**
1. Docker "Get Started" official docs — https://docs.docker.com/get-started/ (sufficient, no course needed)
2. GitHub Actions docs — https://docs.github.com/en/actions/quickstart
3. Redis docs, "Introduction to Redis" — https://redis.io/docs/latest/develop/get-started/

**Checkpoint:** You can explain the difference between an image and a container, and why a Dockerfile builds in layers.

---

## PHASE 5 — Capstone Project (Weeks 11-16)

**Build ONE of these as your flagship, fully deployed to a public URL:**
1. **Distributed job queue** — workers pulling from a queue, retry/backoff, dead-letter handling (best pure-distributed-systems proof)
2. **LLM-backed API service** — Go backend calling an LLM API, basic RAG (embeddings + vector search), proper timeout/retry handling for the flaky upstream (best AI-era relevance proof)

Recommendation given your goals: do the **LLM-backed service**, since it proves both backend competence AND AI-era relevance in one project.

**Resources:**
1. Anthropic API docs (use directly, skip courses) — https://docs.claude.com
2. OpenAI API docs (alternative/comparison) — https://platform.openai.com/docs
3. Vector search basics: pgvector (Postgres extension, keeps your stack consistent) — https://github.com/pgvector/pgvector
4. Deployment: Railway or Fly.io (cheap, simple, Docker-native) — https://fly.io/docs/ or https://docs.railway.com/

**Deliverable:** Deployed live URL + README explaining every architecture decision + you can defend every line if asked in an interview.

---

## PHASE 6 — Months 5-7: Python + Distributed Systems Depth

**Python (parallel track, 30-45 min/day, ramping up):**
1. **"Python Crash Course" by Eric Matthes** — fast fluency
2. Then immediately apply it: scripting against your own APIs, then LLM API usage in Python too (compare to your Go implementation)

**Distributed systems intuition (1 chapter/week, don't binge):**
1. **"Designing Data-Intensive Applications" by Martin Kleppmann** — the single best book for this; start in month 3-4, finish by month 7

**Kubernetes (start light, month 6-7 not earlier):**
1. **Kubernetes the Hard Way** by Kelsey Hightower (free, GitHub) — https://github.com/kelseyhightower/kubernetes-the-hard-way — teaches what k8s actually does, not just `kubectl apply`
2. Deploy your capstone project onto a local cluster (`kind` or `minikube`)

**Observability:**
1. Prometheus "getting started" — https://prometheus.io/docs/prometheus/latest/getting_started/
2. Grafana "getting started" — https://grafana.com/docs/grafana/latest/getting-started/
3. Apply both to your own deployed service, not a sample app

---

## PHASE 7 — Months 8+: Job Search (runs in parallel with continued building)

**Days 1-30 of search phase:**
- Finish 2 portfolio-quality projects (your capstone + one more)
- Clean up GitHub: pin best repos, write real READMEs
- Rewrite resume around what you built, not courses you took

**Ongoing:**
- Target: 100-200 tailored applications over several months, not a burst of 20
- Prioritize: small startups, companies in IT/infrastructure-adjacent industries (your existing domain), remote-first companies known to hire juniors (GitLab, Zapier, Shopify, Cloudflare)
- Get community feedback throughout — Exercism mentoring, Go/backend Discord communities, code review from real humans
- Practice explaining trade-offs out loud for your capstone project before interviews — this is what 2026 junior interviews actually test

**Resources:**
- r/golang, Gophers Slack community (for feedback + networking)
- "Designing Data-Intensive Applications" — keep referencing this during system-design interview prep

---

## WEEKLY TIME BUDGET (20-25 hrs/week target)

| Activity | % of time |
|---|---|
| Building/coding | 60% |
| Deliberate learning (docs, books) | 25% |
| Writing about it (learning log, README) | 15% |

---

## NON-NEGOTIABLE HABITS THROUGHOUT

1. Commit and log something almost every day — consistency beats binges
2. Deploy everything publicly — nothing stays laptop-only
3. Never accept AI-generated code you can't explain
4. Get human feedback regularly, not just AI feedback
5. Don't skip the "write about it" step — it's what makes effort visible to employers
