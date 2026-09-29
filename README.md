# Learning Track: Backend & Systems Engineer

Starting point: ICT Level 6 diploma, basic CLI programming (variables, functions, arrays, pointers), strong networking/Linux/hardware background.

Target: job-ready junior backend/infrastructure engineer, on the path toward distributed systems and eventually AI infrastructure.

Primary language: **Go**. Second language: **Python**. See [`ROADMAP.md`](./ROADMAP.md) for the full reasoning and plan, and [`PROGRESS.md`](./PROGRESS.md) for live status.

## How this repo is organized

```
.
├── ROADMAP.md                          # the full plan, phase by phase, with resources
├── PROGRESS.md                         # checklist — update this as you go
├── phase-0-setup/                      # environment, tooling, habits
├── phase-1-go-fundamentals/            # Go syntax, structs, interfaces, concurrency
├── phase-2-http-networking/            # raw net/http, no framework
├── phase-3-databases/                  # PostgreSQL, SQL, migrations
├── phase-4-infrastructure/             # Docker, CI, Redis/queues
├── phase-5-capstone/                   # notes/design docs for the flagship project
├── phase-6-python-and-distributed-systems/  # Python, Kleppmann notes, k8s, observability
├── phase-7-job-search/                 # resume, application tracker, interview prep
├── projects/                           # actual code for each project (see below)
├── learning-log/                       # one entry per session — non-negotiable habit
└── resources/                          # curated links/books per topic
```

## Projects

Each project gets its own folder under `projects/` with its own README (what it does, why, what it proves), deployed to a public URL once working. See [`ROADMAP.md`](./ROADMAP.md) for the full spec of each.

| # | Project | Proves |
|---|---|---|
| 01 | Concurrent CLI tools | goroutines/channels, real concurrency |
| 02 | Raw HTTP API (no framework) | you understand what a framework abstracts |
| 03 | Postgres-backed API | persistence, real queries, migrations |
| 04 | Dockerized service + CI | containerization, deployment discipline |
| 05 | Capstone: LLM-backed service | backend + AI-era relevance, the flagship piece |

## Non-negotiable habits

1. Commit and log something almost every day — consistency beats binges.
2. Deploy everything publicly — nothing stays laptop-only.
3. Never accept AI-generated code you can't explain line by line.
4. Get human feedback regularly (Exercism mentoring, Discord, code review) — not just AI feedback.
5. Write a short entry in `learning-log/` every session. This is what makes the work visible to employers later.

## Weekly time budget (target 20–25 hrs/week)

- 60% building/coding
- 25% deliberate learning (docs, books)
- 15% writing about it (learning log, READMEs)
