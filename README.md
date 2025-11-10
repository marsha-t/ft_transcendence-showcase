# ft_transcendence — A Showcase

**ft_transcendence** is a full-stack, real-time multiplayer web application inspired by the classic game *Pong*. It demonstrates end-to-end software engineering across web development, networking, gameplay systems, cybersecurity, and AI.

This repository presents the project’s architecture, system design, and representative code excerpts. The full implementation remains in **active development** as part of the final project at **42 Abu Dhabi**.

Completed components include:
- Core gameplay engine  
- User management and authentication  
- Tournament matchmaking system  
- Frontend design and routing  
- Dockerized infrastructure  
- Cybersecurity safeguards  
- Interactive analytics dashboard  

Ongoing work focuses on refining the AI opponent, enhancing DevOps automation, and preparing for production deployment. The full implementation will be made public upon completion.

---
## 🕹️ Project Overview


**ft_transcendence** is a real-time multiplayer gaming platform built as a single-page web application. It integrates multiple subsystems components,  from a **Fastify backend** to a **TypeScript + Tailwind** frontend, to deliver seamless, secure, and responsive gameplay


| Layer | Description |
|--------|-------------|
| **Frontend** | TypeScript SPA with Tailwind CSS and modular component structure |
| **Backend** | Fastify (Node.js) REST API handling user authentication, matchmaking, scoring |
| **Database** | SQLite with Prisma ORM for persistent data management |
| **DevOps** | Dockerized containers with single-command deployment and microservice-oriented design |
| **Security** | JWT authentication, optional 2FA, HTTPS, and XSS/SQL injection prevention |
| **Gameplay** | Deterministic Pong engine with tournament bracket and AI integration |
| **Analytics** | Interactive dashboard summarizing user and match statistics |

---

## 🧩 System Architecture
```mermaid
graph TD
  %% === CLIENT LAYER ===
  subgraph Client_Layer [<b>Client Layer</b>]
    A[<b>Frontend</b>
    TypeScript 
    Tailwind CSS
    Single Page Application 
    Game Rendering]
  end

  %% === APPLICATION LAYER ===
  subgraph Application_Layer [<b>Application Layer</b>]
    B[<b>Backend</b>
    Fastify - Node.js
    REST API]
  end

  %% === DATA LAYER ===
  subgraph Data_Layer [<b>Data Layer</b>]
    C[<b>SQLite Database</b>
    Accessed via Prisma ORM]
  end

  %% === INFRASTRUCTURE LAYER ===
  subgraph Infrastructure_Layer [<b>Infrastructure Layer</b>]
    F[<b>Dockerized Environment</b>
    Docker Compose
    Nginx Reverse Proxy
    HTTPS]
  end

  %% === CONNECTIONS ===
  Client_Layer --> Application_Layer
  Application_Layer --> Data_Layer
  Data_Layer --> Infrastructure_Layer


  %% === STYLES ===
  classDef client fill:#facc15,stroke:#333,stroke-width:1px,color:#111;
  classDef app fill:#38bdf8,stroke:#333,stroke-width:1px,color:#111;
  classDef data fill:#4ade80,stroke:#333,stroke-width:1px,color:#111;
  classDef infra fill:#a78bfa,stroke:#333,stroke-width:1px,color:#111;

  class A, client;
  class B, app;
  class C data;
  class F, infra;
