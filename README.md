# Hi, I'm Lenya

Full-stack web developer and 1st-year Master's student.  
I build practical systems with clear architecture, containerized environments, and production-style APIs.

## 🚀 Featured (public) project

- **[web3wms](https://github.com/oglenyaboss/web3wms)** — Warehouse Management System + equipment tracking with an auditable transfer history.
  - Microservices communicating via **REST** and **RabbitMQ**
  - **MongoDB** as primary storage (separated by service databases)
  - MVP on-chain audit via **Ethereum (Ganache)** + smart contracts
  - **Docker Compose** for local deployment
  - Frontend: **Next.js** + **Mantine UI**

### web3wms architecture (short)
- Services:
  - **auth-service** (Go) — auth, roles, user profiles, ETH address mapping
  - **warehouse-service** (Go) — inventory, transactions, invoices, master data
  - **tracking-service** (Node.js/Express) — equipment lifecycle + blockchain integration
  - **notification-service** (Go) — notifications (MVP: in-memory; DB reserved for later)
  - **analytics-service** (Go) — minimal stub (not in compose)
- Messaging (RabbitMQ):
  - `equipment.created` → tracking-service
  - `equipment.transferred` → notification-service
- Storage (MongoDB):
  - `warehouse_auth`, `warehouse_inventory`, `warehouse_tracking`

## 🎓 Current university project (HSE MIEM, 2025/2026)

- **Project #2340 — “Blockchain-based warehouse accounting system”**  
  https://cabinet.miem.hse.ru/project/2340/  
  - Goal: build a functional prototype of a blockchain system for warehouse accounting to improve reliability and transparency.  
  - Expected deliverables (per project passport): smart contracts for **receiving**, **putaway**, **picking**, **shipping**; a blockchain application (based on **Hyperledger Fabric or an alternative**); and a **user interface**.  
  - Milestones: start **2025-11-04**, defense window **2026-06-08 – 2026-06-19**.

### #2340 architecture (concise, safe to state)
- Modular prototype: **smart-contract layer** (warehouse flow contracts) + **application layer** (API/services) + **UI layer**.  
- Tech direction: **Go** + **JavaScript** (and related tooling) as stated in tags.  
- DLT platform: **Hyperledger Fabric (or alternative)** under evaluation.  

## 🛠️ Tech stack

**Backend:** Go, Node.js, NestJS, Express  
**Frontend:** TypeScript, React, Next.js, Mantine UI  
**Databases:** MongoDB  
**Messaging:** RabbitMQ, Kafka  
**Blockchain:** Ethereum (Ganache for MVP), Hyperledger Fabric (evaluation)  
**Infrastructure:** Docker, Docker Compose

## 🔬 Currently learning

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
