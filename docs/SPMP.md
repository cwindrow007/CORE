# Software Project Management Plan (SPMP)
**Project Name:** Core- Chopper Operations Resource Engine
**Developer:** Christopher Windrow
**Contributors** Tim Dziedzic (Contributor to orginal concepts and tools)
**Version:** V0.0.1
**Date:** May 12th, 2025

---

## 1. Overview
Core is a centralized web application designed to support daily operational workflows at grocery store locations, starting with Store #189. It brings together features like lane assignment, safe count logging, lottery ticket tracking (including OCR), and internal documentation tools in one responsive platform.

---
## 2. Project Organization
### 2.1 Roles and Responsibilities

|Role                | Name               | Responsibility     |
|--------------------|--------------------|--------------------|
|Project Lead        | Christopher Windrow|Planning, development, testing |                   |
|Contributor         | Tim Dziedzic       |Legacy system design, guidance |
|Reviewer            | TBD                |Feedback, use-case validation  |

---
## 3. Managerial process Plans

### 3.1 Deelopment Methodology
Agile-lite with Github Issues and Milestone-based sprints.
Each sprint targts one major feature/module(Safe Count, Lane Assign, Lottery OCR, Docs).

### 3.2 Tools
|Type             |Tool                |
|-----------------|--------------------|
|Code Repository  | Github             |
|Project Board    | Github Projects    |
|Issue Tracking   | Github Issues      |
|Documentation    | Markdown (.md files in `/docs/`) |
|Hositng          | Firebase or Vercel |
|Collaboration    | Github + optional Discord/Chat |
---
## 4. Technical Process Plans

### 4.1 Technology Stack
| Layer        | Stack                           |
|--------------|---------------------------------|
| Frontend     | React + TypeScript + TailwindCSS|
| Backend      | Firebase (Auth  + Firestore)    |
| OCR Engine   | Teseract.js                     |
|Testing       | Jest + React Testing Library    |
|Deployment    | Firesbase Hosting or Vercel     |
|Future Mobile | Responsive Web + PWA or Capacitor |

### 4.2 Development Environmnt
- Node.js with Vite
- Firebase project configurd for Auth and Firestore
- Github for code + issues tracking
---

## 5. Work Breakdown Structure

### Sprint 1 – MVP Foundation (May 9 – May 16)
- [ ] Set up repo, TailwindCSS, Firebase, Routing
- [ ] Safe Count: Input form, Firestore integration, basic export
- [ ] Add SPMP + SDD documents
- [ ] Set up GitHub Issues + Project Board

### Sprint 2 – Lane Assignment & Navigation (May 17 – May 24)
- [ ] Build lane assignment UI
- [ ] Add override logic + store roles
- [ ] Add navigation bar with mobile support

### Sprint 3 – Lottery OCR (May 25 – June 2)
- [ ] Add manual lottery form
- [ ] Integrate Tesseract.js OCR
- [ ] Add ticket type editor for admins

---

## 6. Risk Management

| Risk | Likelihood | Mitigation |
|------|------------|------------|
| Time constraints (school/work) | Medium | Work in sprints, break into small issues |
| Firebase costs | Low | Use free tier and optimize reads/writes |
| Feature creep | Medium | Stick to scoped sprints and backlog extra ideas |
| Mobile usability issues | Medium | Build mobile-first with Tailwind responsiveness |

---

## 7. Appendix

- See [README.md](../README.md) for project overview and links
- [SDD.md](./SDD.md) contains technical design
- License: MIT (with disclaimer of no corporate affiliation)
