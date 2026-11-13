# Research Commercialisation & Semantic Matching Platform (res-handler)

[![Language](https://img.shields.io/badge/Language-Go%20(Golang%201.25)-00ADD8?style=for-the-badge&logo=go&logoColor=white)](https://golang.org/)
[![AI & Vector](https://img.shields.io/badge/Vector%20Search-pgvector%20%7C%20Azure%20OpenAI-412991?style=for-the-badge)](https://github.com/Abdulqader-Alshihabi/res-handler)
[![Database](https://img.shields.io/badge/Database-PostgreSQL%2015-336791?style=for-the-badge&logo=postgresql&logoColor=white)](https://github.com/Abdulqader-Alshihabi/res-handler)
[![Architecture](https://img.shields.io/badge/Architecture-Go%20SSR%20%2B%20htmx-black?style=for-the-badge)](https://htmx.org/)
[![Cloud](https://img.shields.io/badge/Cloud-Docker%20%7C%20Azure%20Container%20Apps-0089D6?style=for-the-badge)](https://github.com/Abdulqader-Alshihabi/res-handler)

Institution: Institute of Research and Consulting Studies — Islamic University of Madinah  
Category: Enterprise Research Commercialisation, Knowledge Transfer & AI Vector Matching Engine  
Role: Backend & AI Search Software Engineer  

---

## Institutional Notice and IP Confidentiality

> [!IMPORTANT]
> Institutional Project Notice:  
> This repository serves as an Architectural Case Study and Technical Specification for the Islamic University Research Commercialisation and Semantic Matching Engine. In strict adherence to institutional data governance, academic non-disclosure policies, and cloud infrastructure security, production database backups, proprietary faculty datasets, and Azure production secrets are hosted within the university's private cloud infrastructure.

---

## Executive Summary

The Research Commercialisation & Interdisciplinary Intelligence Platform (`res-handler`) is a high-performance enterprise system engineered to bridge academic innovation, cross-departmental collaboration, and market commercialization demand. The platform aggregates the university's complete research corpus, targets relevant industrial and governmental partners, uncovers latent interdisciplinary research synergies, and forms the foundation for 17 specialized institutional Expert Houses (بيوت خبرة).

Engineered with Go (Golang 1.25), htmx, PostgreSQL, and `pgvector`, the platform eliminates client-side JavaScript bundle overhead through high-speed server-rendered HTML with reactive DOM swaps. It provides an AI-driven Reverse Problem-to-Solution semantic matching engine alongside an Interdisciplinary Cross-Pollination Engine that matches disparate faculty competencies (e.g., Computer Science scholars publishing in NLP with Arabic Linguistics researchers exploring computational text analysis) to propose joint high-impact research initiatives and commercial consulting services.

---

## System Architecture

```
┌────────────────────────────────────────────────────────────────────────┐
│                   External Client & Partner Browser                    │
│  - Presentation: Native Arabic-first (RTL) Layout                      │
│  - Interactivity: htmx (Reactive partial HTML swaps without JSON bloat)│
│  - Styling: Tailwind CSS & Lucide Vector Icons                         │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │  HTTP / TLS (Sub-50ms SSR Latency)
                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│                    Go Microservice (Golang 1.25)                       │
│  - Router: Chi HTTP Router (Layered: internal/handlers, render, auth)  │
│  - Embeddings Client: Azure OpenAI Embeddings API (internal/embed)     │
│  - Security & Middleware: Role-Based Access, CSRF, Tokenized Sessions  │
│  - Curated Link Engine: Tokenized private sharing without login friction│
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │
                                   ▼  SQL Queries & Vector Cosine Distance
┌────────────────────────────────────────────────────────────────────────┐
│                  PostgreSQL Database & pgvector Storage                │
│  - Vector Embeddings: High-dimensional embeddings with HNSW indexing   │
│  - Core Entities: Researchers, Publications, Research Tickets (Cards)  │
│  - Schema Migrations: Automated zero-downtime database migrations      │
└────────────────────────────────────────────────────────────────────────┘
```

---

## Technical Highlights & Key Engineering Modules

### 1. High-Performance Go + htmx Architecture
- Implemented a server-side rendered (SSR) application in Go, achieving sub-50ms time-to-first-byte (TTFB) and rendering latencies without requiring complex client-side single-page app dependencies.
- Leveraged `htmx` for dynamic, reactive UI updates, delivering instantaneous search filtering, ticket bookmarking, and modal displays via server-rendered HTML partials.
- Clean separation of concerns across Go packages (`internal/handlers`, `internal/render`, `internal/embed`, `internal/middleware`).

### 2. AI-Powered Reverse Problem-to-Solution & Interdisciplinary Cross-Pollination
- Built a high-dimensional vector discovery engine using PostgreSQL with the `pgvector` extension and 1,536-dimensional embeddings.
- **Interdisciplinary Cross-Pollination:** Automatically analyzes faculty publication clusters across different colleges to identify cross-departmental synergies—for instance, connecting computer science researchers developing Arabic computational models with Arabic language professors doing digital linguistics to establish multidisciplinary grants.
- **Targeted Industry Commercialization:** Profiles corporate sectors and maps commercial enterprise problem statements to published university research, transforming raw academic literature into actionable commercial Research Tickets («بطاقات بحثية»).
- **17 Specialized Institutional Expert Houses (بيوت خبرة):** Grouped faculty capability matrices to structure and launch 17 university-certified consulting houses, positioning academic talent for high-value external contracts.

### 3. Tokenized Curated Sharing for External Partners
- Developed a secure, tokenized URL dispatch system allowing university consultants to bundle curated collections of research tickets for external ministries and corporate executives.
- External decision-makers can inspect, review, and evaluate targeted research cards through private, cryptographically generated access links with zero account creation friction.

### 4. Cloud Deployment & Containerization
- Containerized via micro-optimized Docker images running on Microsoft Azure Container Apps.
- Enforced automated CI/CD deployment pipelines on Git merges.
- Integrated schema migration safeguards (`go run . migrate up`) ensuring backward and forward database compatibility.

---

## Technology Stack

| Layer | Technologies and Libraries |
| :--- | :--- |
| **Backend Language** | Go (Golang 1.25) |
| **Routing & Middleware** | Chi Router (`github.com/go-chi/chi/v5`) |
| **Frontend Rendering** | Go HTML Templates, htmx, Tailwind CSS |
| **Database & Vector Store** | PostgreSQL 15+, pgvector |
| **AI Embeddings** | Azure OpenAI Embeddings Client |
| **Container & Cloud** | Docker, Azure Container Apps, Azure Blob Storage |
| **Testing & Tooling** | Go Standard Library `testing`, Air (live reload), Taskfile |

---

## Engineering Credits

**Abdulqader Alshihabi**  
Computer Science Graduate | Software & AI Engineer  
- Portfolio: [https://abdulqader-alshihabi.github.io/](https://abdulqader-alshihabi.github.io/)  
- GitHub: [@Abdulqader-Alshihabi](https://github.com/Abdulqader-Alshihabi)  
- Email: [abdulqader.moh.2003@gmail.com](mailto:abdulqader.moh.2003@gmail.com)  
