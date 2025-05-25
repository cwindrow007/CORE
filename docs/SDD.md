# Software Design Document (SDD)
**Project Name:** CORE - CHOPPER OPERATIONS RESOURCE ENGINE
**Version:**
**Author:** Christopher Windrow
**Date:** May 25, 2025

---

## 1. Introduction
### 1.1 Purpose
This document outlines the software architecture and design for CORE - a centralized web application used to streamline day-to-day operation task at Store #189, 
including safe count tracking, lane assignments, lotter management with OCR, and access to training documents.

### 1.2 Scope
CORE will be a responseive, Firebase-backend web application built with React and TypeScript. Its design supports modular growth and  potential reuse across similar
retrail environments. While insitially created for personal use at Store #189, this application is structured to support portability and future expansion.

---
## 2. System Overview

### 2.1 Core Modules 
- **Safe Count Modules** - Input and track daily safe balances.
- **Lane Assignment Module** - Automatically assign and manually adjust cashier lanes.
- **Lottery Tracker Module** - Log tickets and scan counts using OCR
- **Document Center** - View guides and internal documentation
---

# 3. System Architecture 
### 3.1 System Architecture Diagram
```
graph TD
  User[User (Employee / Supervisor / Admin)]
  A[React Frontend (Vite + Tailwind)]
  B[Firebase Authentication]
  C[Firestore Database]
  D[Firebase Storage]
  E[Tesseract.js OCR Engine]

  User --> A
  A --> B
  A --> C
  A --> D
  A --> E
```
