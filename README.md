<h1 align="center">Priyank Agrawal</h1>

<p align="center">
  <b>AI / LLM Engineer</b> · Production multi-agent systems, RAG, and agentic workflows
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/priyank-aggrawal/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://www.priyankagrawal.in"><img src="https://img.shields.io/badge/Portfolio-111111?style=flat-square&logo=vercel&logoColor=white" alt="Portfolio"></a>
  <a href="mailto:priyankagrawal76660@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
  <a href="https://dev.to/priyank_agrawal"><img src="https://img.shields.io/badge/Dev.to-0A0A0A?style=flat-square&logo=devdotto&logoColor=white" alt="Dev.to"></a>
</p>

---

## Overview

I'm an AI/LLM engineer with **3+ years** shipping production systems, currently building agentic AI at **Planet Sustech**. My work centers on **multi-agent orchestration, typed tool-calling, and RAG** — the unglamorous engineering that makes LLMs behave like reliable systems rather than demos.

I care about the parts that decide whether an agent survives contact with production: deterministic tool boundaries, server-derived analytics that kill hallucination, structured extraction from messy real-world inputs, and orchestration that degrades gracefully. Most of my recent systems run on **LangGraph** and **AWS Bedrock**, backed by NestJS/FastAPI services and Postgres/MongoDB.

---

## Production Agentic Systems

Systems I've designed and shipped at **Planet Sustech** — ESG/climate domain, real users, real data.

### KarbonIQ — Conversational ESG Agent
A supervisor-routed agent (**AWS Bedrock · LangGraph**) exposing **21 typed tool-calling functions** for natural-language ESG querying. Instead of NL-to-query generation, every answer flows through **server-derived analytics**, which eliminates LLM hallucination on numbers. Auto-generates executive dashboards with Excel/PDF export and **RBAC across 4 roles**. Cut manual analysis time by **~70%**.

### AI Data-Ingestion Agent
A **vision + OCR** pipeline (Bedrock) that extracts ESG metrics from **8+ document formats** — PDF, Excel, scanned images, email — and auto-calculates **Scope 1/2/3 emissions** at **95% extraction confidence**. Deployed on **AWS ECS Fargate**.

### ESG Benchmarking Agent
Ingests **BRSR/XBRL filings for 987+ listed companies** to produce **SASB-weighted peer scoring**, percentile rankings, gap-to-leader analysis, and 5 AI-generated improvement recommendations per company.

### Supplier Due-Diligence Agent
Scrapes supplier data from public sources, **auto-builds custom assessments** for data gaps, and runs an **autonomous follow-up sub-agent** to chase responses — targeting **~60% faster** supplier onboarding.

---

## How I Architect Agents

A representative multi-agent pattern from my work — supervisor routing, specialized agents, a typed tool boundary, and analytics derived on the server rather than by the model.

```mermaid
flowchart TD
    U([Executive / User]) -->|natural language| R{Intent Router}
    R --> S[Supervisor Agent]

    S --> Q[Query Agent]
    S --> B[Benchmarking Agent]
    S --> I[Ingestion Agent]
    S --> D[Due-Diligence Agent]

    Q --> T[[Typed Tool-Calling Layer]]
    T --> DB[(ESG Data Store)]
    I --> V[Bedrock Vision + OCR]
    B --> X[BRSR / XBRL Filings]
    D --> W[Public Web Sources]

    Q --> O[Server-Derived Analytics]
    O --> RESP([Dashboards · Excel · PDF])
```

**Principles I build by:** typed tools over free-form generation · compute answers server-side, let the model orchestrate · sub-agents for autonomous follow-through · RBAC and auditability from day one.

---

## Selected Projects

| Project | What it is | Stack |
|---|---|---|
| **[NextRole](https://github.com/Priyank032/ai-career-copilot)** | 7-agent conversational job-search & career-coaching system with intent classification, multi-turn context management, and SSE streaming (90%+ routing accuracy) | `FastAPI` · `Next.js` · `LangChain` · `Groq LLaMA 3.3` · `Supabase` |
| **ESG Analytics Chatbot** | RAG assistant converting natural language into MongoDB aggregation pipelines at 95%+ accuracy | `Node.js` · `LangChain` · `MongoDB` · `RAG` |
| **Speedbox** | Serverless logistics platform — microservices on Lambda, OAuth 2.0, auto-scaling to 10k+ concurrent requests, 99.9% uptime | `AWS Lambda` · `Cognito` · `SNS` · `PostgreSQL` |

---

## Tech Stack

<details open>
<summary><b>AI / LLM</b></summary>
<br>

![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![AWS Bedrock](https://img.shields.io/badge/AWS%20Bedrock-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-F55036?style=flat-square&logo=groq&logoColor=white)
![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)

**Focus:** Multi-Agent Orchestration · Typed Tool-Calling · RAG · Intent Routing · Structured Extraction · Prompt Engineering

</details>

<details>
<summary><b>Backend & APIs</b></summary>
<br>

![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-6DA55F?style=flat-square&logo=node.js&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=flat-square&logo=fastapi&logoColor=white)
![Express](https://img.shields.io/badge/Express-404D59?style=flat-square&logo=express&logoColor=white)
![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=flat-square&logo=graphql&logoColor=white)

</details>

<details>
<summary><b>Data & Infra</b></summary>
<br>

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat-square&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=flat-square&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DD0031?style=flat-square&logo=redis&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white)

**AWS:** Lambda · ECS Fargate · Bedrock · SNS · SES · Cognito &nbsp;|&nbsp; **CI/CD:** GitHub Actions

</details>

<details>
<summary><b>Frontend & Realtime</b></summary>
<br>

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![Socket.io](https://img.shields.io/badge/Socket.io-010101?style=flat-square&logo=socket.io&logoColor=white)

</details>

---

## Experience

**Software Engineer — AI/LLM** · Planet Sustech Private Limited · *Aug 2024 – Present*
Built KarbonIQ and a suite of production ESG agents on AWS Bedrock + LangGraph. Owned agent architecture end to end — from tool-calling design and structured extraction to RBAC and deployment — and mentor a team of interns.

**Associate Software Developer** · Antino Labs Private Limited · *Feb 2023 – Aug 2024*
Engineered a Resource Management System for 400+ employees (Node.js, PostgreSQL, real-time analytics) and a social platform with AI-driven matching and Socket.IO/Agora realtime — 10k+ downloads in 4 months, +30% engagement.

---

## GitHub

<div align="center">

![Stats](https://github-readme-stats.vercel.app/api?username=Priyank032&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=true&hide=stars)

</div>

---

<p align="center">
  <b>Open to:</b> AI/LLM Engineering · Agentic Systems · Full-Stack (AI focus)<br>
  📍 Bhopal, Madhya Pradesh, India &nbsp;·&nbsp; 🎓 B.Tech CSE, IPS College of Technology & Management (CGPA 8.2)
</p>
