# System Architecture & Development Plan

This document outlines the technical architecture, core modules, and the AI-driven development lifecycle (Vibe Coding) for the CRM. The goal is to build a lightweight, scalable, and easily deployable system for furniture workshops.

## 1. System Overview
The platform is designed as a web-based Single Page Application (SPA) with a decoupled backend API. 
* **Client-Side:** Optimized for desktop environments (Windows 11) used by managers in the office, with responsive views for tablets/mobile devices used by craftsmen on the shop floor.
* **Server-Side:** RESTful API handling business logic, document generation, and database interactions.
* **Deployment:** Fully containerized environment ensuring simple self-hosted deployment on any standard VPS.

## 2. Core Modules & Domain Logic
To keep the MVP focused, the system is divided into three isolated domains:

### A. Client & Contract Management (CRM)
* **Lead Tracking:** Kanban-style pipeline from initial inquiry to final measurement.
* **Contract Engine:** Automated PDF generation for client agreements, integrating dynamically with the pricing and materials database.

### B. Inventory & Procurement
* **Material Stock:** Tracking sheet materials (MDF, particleboard), edge banding meters, and hardware.
* **Supplier Orders:** Tracking material procurement states.

### C. Production Pipeline
* **Task Routing:** Moving an order through stages (Cutting -> Edge Banding -> Drilling -> Assembly -> Shipping).
* **Technical Docs:** Attaching 3D models, cut lists, and assembly schemes to specific orders.

## 3. Target Technology Stack
Since the codebase will be generated heavily via AI (Codex/LLMs), we are selecting mature, highly documented frameworks that LLMs understand exceptionally well.

* **Backend:** Python (FastAPI) or Node.js (NestJS) for robust API generation.
* **Frontend:** React.js or Vue 3 with a component library (e.g., Tailwind or MUI) for rapid UI scaffolding.
* **Database:** PostgreSQL for relational data integrity (Crucial for contract and financial data).
* **Infrastructure:** Docker and Docker Compose for seamless containerization and deployment on a Linux VPS.

## 4. AI-Driven "Vibe Coding" Workflow
As a domain expert without a traditional software engineering background, my development loop relies on LLMs:

1. **Architecture Prompting:** Defining data models (e.g., "Create a SQLAlchemy model for a Furniture Order with foreign keys to Materials").
2. **Code Generation:** Using AI assistants to generate the scaffolding, API endpoints, and UI components.
3. **Iterative Refinement:** Testing the generated code locally, feeding error logs back to the LLM for debugging, and refining the business logic.
4. **Security & Linting:** Utilizing AI code-review tools to ensure the generated code adheres to security best practices before merging into the main branch.

This approach not only builds the product but serves as a case study for how AI can lower the barrier to entry for industry-specific open-source software.
