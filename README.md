# Hi, I'm Lenya

Full-stack web developer and 1st-year Master's student.  
I build practical systems with clear architecture, containerized environments, and production-style APIs.

## 💼 Recent work (production case study)

- **Event-driven webhook processing platform (work project, private)**
  - Purpose: ingest webhooks from multiple sources and deliver normalized events into a CRM
  - Architecture: microservices + event streaming (**Kafka**), event-sourcing approach
  - Stack: **NestJS**, Node.js, Docker, GitHub Actions (CI/CD), Next.js (internal UI), ELK for observability
  - Load test results: **~830 webhooks/sec ingestion**, **~400 webhooks/sec delivery** (CRM outbound)
  - Ownership: designed, implemented, tuned, and load-tested end-to-end

## 🚀 Featured project

- **[avalanche-wms](https://github.com/oglenyaboss/avalanche-wms)** — Blockchain-backed Warehouse Management System with an auditable, on-chain history of warehouse operations. *University project #2340, defended June 2026.*
  - **Go** WMS core + a dedicated **ledger-adapter** service mirroring warehouse events on-chain (outbox pattern — no dual-write)
  - **CDC pipeline:** PostgreSQL → **Debezium** → **Kafka** → ledger-adapter → smart contract
  - On-chain layer: **Avalanche Subnet-EVM** + Solidity (`BatchMappingWMS`) — selected over Hyperledger Fabric for EVM-native tooling and a reproducible, fully-containerized testnet
  - **Geo-distributed** validator network across 3 countries (🇲🇩 🇷🇴 🇳🇱) under real BFT consensus — survives a validator going down (2-of-3 still finalizes)
  - Load- & stress-tested end-to-end — sustained **~1,900 events/sec** with **zero message loss** on full-backlog drain (detailed throughput/latency reports in the repo)
  - Frontend: **React 19** + **TypeScript** (Vite, Feature-Sliced Design, **shadcn/ui** + Tailwind, Zustand)
  - **Docker Compose** for local bring-up · **GPLv3**

- **[web3wms](https://github.com/oglenyaboss/web3wms)** — earlier prototype of the same idea (MVP iteration).
  - Microservices over **REST** + **RabbitMQ**, **MongoDB** per-service storage
  - On-chain audit via **Ethereum (Ganache)** + smart contracts
  - Frontend: **Next.js** + **Mantine UI**

## 🎓 University project (HSE MIEM, 2025/2026)

- **Project #2340 — “Blockchain-based warehouse accounting system”** — [project card](https://cabinet.miem.hse.ru/project/2340/) · code: **[avalanche-wms](https://github.com/oglenyaboss/avalanche-wms)**
  - Goal: a functional prototype of a blockchain warehouse-accounting system to improve reliability and transparency of stock records
  - Delivered: smart-contract coverage of the warehouse flow (**receiving · putaway · picking · shipping**), a blockchain integration service, and a web UI
  - Platform decision: **Avalanche Subnet-EVM** chosen over Hyperledger Fabric (EVM tooling, reproducible container-native testnet, geo-distributed validators)
  - Defended within the **2026-06-08 – 2026-06-19** window

### #2340 architecture (concise)
- **Smart-contract layer** (`BatchMappingWMS` — warehouse-flow state on-chain) + **application layer** (Go services, CDC/outbox) + **UI layer** (React)
- Event path: warehouse action → PostgreSQL → Debezium CDC → Kafka → ledger-adapter → Subnet-EVM
- Tech: **Go**, **TypeScript / React**, **PostgreSQL**, **Kafka**, **Avalanche Subnet-EVM**

## 🛠️ Tech stack

**Backend:** Go, Node.js, NestJS, Express  
**Frontend:** TypeScript, React, Next.js, Vite, shadcn/ui, Mantine UI, Tailwind  
**Databases:** PostgreSQL, MongoDB  
**Messaging / streaming:** Kafka, Debezium (CDC), RabbitMQ  
**Blockchain:** Avalanche Subnet-EVM, Solidity, Ethereum (Ganache for MVP)  
**Infrastructure:** Docker, Docker Compose, GitHub Actions  
**Observability:** ELK

## 🔬 Currently exploring

<div align="left">
  <img src="https://img.shields.io/badge/-Go-00ADD8?style=for-the-badge&logo=go&logoColor=white" alt="Go" />
  <img src="https://img.shields.io/badge/-Apache%20Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white" alt="Kafka" />
</div>

## 📫 Contact

- Telegram: https://t.me/ll_ogl  
- Email: oglenyaboss@icloud.com

## 📊 GitHub stats

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=oglenyaboss&show_icons=true&theme=tokyonight" alt="GitHub Stats" />
</div>
