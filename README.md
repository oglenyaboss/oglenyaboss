# Lenya Lozhkin

Backend-leaning full stack developer, UrFU MSc candidate (2027). I build event-driven systems: Go, Node, Kafka, Postgres, and I load-test them before I claim they work.

## What I've built

### [avalanche-wms](https://github.com/oglenyaboss/avalanche-wms) — WMS with an on-chain audit trail

University project #2340 at HSE MIEM, defended June 2026. Go + PostgreSQL + Debezium + Kafka + Avalanche Subnet-EVM, React 19 frontend. GPLv3.

Warehouse actions go into Postgres and an outbox table, Debezium reads the WAL, Kafka carries events to a ledger-adapter that batches them into a Solidity contract. One directional, no dual-write, idempotent at every hop.

Numbers I can point at (full reports in [`docs/load-testing/`](https://github.com/oglenyaboss/avalanche-wms/tree/main/docs/load-testing)):

- **1,924 committed state transitions/sec** end-to-end on full backlog drain, 575,210 generated → 575,210 committed, zero loss. Target was 1,500/sec. One item walks four transitions, so that is ~481 items/sec of full lifecycle. The adapter batches, so actual on-chain transactions land at ~1-3/sec.
- **4-validator geo-distributed network** (Moldova, Romania, Netherlands) under real BFT consensus. I started with 3 nodes and hit a wall: killing one leaves 66.67% stake, below the 73.33% observer threshold, so the pipeline froze. Adding a 4th validator got it to 75%, and under kill-1 the network kept finalizing with 0 events lost.
- The geo network commits tens of events/sec against ~1,900 locally. I wrote up [why](https://github.com/oglenyaboss/avalanche-wms/blob/main/docs/load-testing/geo-throughput-rootcause.md): not gas, not WAN RTT, not core count. Mostly cache and swap config on the VPS.

Also in the repo: CDC contract docs, Foundry contract tests, `make up` brings up the whole stack including a local Subnet-EVM node, and [wms-architect](https://github.com/oglenyaboss/wms-architect) is the interactive architecture case.

**[web3wms](https://github.com/oglenyaboss/web3wms)** is the earlier MVP of the same idea: Go + Node microservices over REST and RabbitMQ, MongoDB per service, Ethereum/Ganache for the audit log, Next.js UI. Superseded, kept for the diff.

### HookFactory — webhook and CRM integration platform (DN7, since Oct 2025)

Built solo in about 8 months, now serving ~20 clients. NestJS, Node, Docker, GitHub Actions, Next.js internal UI, ELK. Ingest holds **~830 webhooks/sec**, CRM delivery **~400/sec**. Closed 100+ PRs against it.

### Open source

[Repowise](https://github.com/Repowise/repowise): added OpenRouter as an LLM and embeddings provider. Also maintain pi extensions and OpenCode plugins for LLM coding workflows.

## Stack I actually reach for

| | |
|---|---|
| Backend | Go, Node.js, NestJS, Express |
| Frontend | TypeScript, React 19, Next.js, Vite, shadcn/ui + Radix, Tailwind |
| Data | PostgreSQL, MongoDB |
| Messaging | Kafka, Debezium (CDC), RabbitMQ |
| Chain | Avalanche Subnet-EVM, Solidity |
| Infra | Docker, Docker Compose, GitHub Actions, Grafana + Prometheus |
| Observability | ELK |

## Teaching

HSE MIEM 2025-26: invited teacher and technical curator, external tech lead for a 4-person blockchain team. Architecture, code review, most of the code, plus frontend and load tests.

## Contact

Telegram [@ll_ogl](https://t.me/ll_ogl) · oglenyaboss@icloud.com · [LinkedIn](https://linkedin.com/in/oglenyaboss)
