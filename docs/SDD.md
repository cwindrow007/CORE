# Software Design Document (SDD)
- **Project Name:** CORE - CHOPPER OPERATIONS RESOURCE ENGINE
- **Version:** INFDEV
- **Author:** Christopher Windrow
- **Date:** May 25, 2025

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
### 3.2 Component-Based Frontend

| Component                 | Responsibility                         |
|--------------------------|------------------------------------------|
| `SafeCountForm.tsx`      | Input and submit safe count values       |
| `LaneAssignmentPage.tsx` | View & override lane assignments         |
| `LotteryForm.tsx`        | Log ticket values, trigger OCR scan      |
| `DocumentViewer.tsx`     | Load/view training or process documents  |
| `Navbar.tsx`             | Route between main modules               |
| `AuthContext.tsx`        | Handle login/logout/auth state globally  |

---

## 4. Data Design

### 4.1 Firestore Collections

| Collection        | Fields                                      | Access Level |
|-------------------|---------------------------------------------|--------------|
| `safeCounts/`     | `amount`, `timestamp`, `userId`             | Employee+    |
| `laneAssignments/`| `date`, `lanes[]`, `assignedBy`, `notes`    | Supervisor+  |
| `lotteryLogs/`    | `shift`, `ticketType`, `quantity`, `image`  | Employee+    |
| `users/`          | `email`, `role`, `storeId`                  | Admin        |

### 4.2 Firebase Auth Roles (custom claims optional)

- `employee`
- `supervisor`
- `admin`

---

## 5. Interface Design

### 5.1 User Interface (UI)

| Page             | Description                                |
|------------------|--------------------------------------------|
| `/login`         | Auth page (email/password login)           |
| `/safe-count`    | Input form + history log for safe counts   |
| `/lane-assign`   | Manual/auto assignment table view          |
| `/lottery`       | OCR scanner or manual entry form           |
| `/docs`          | List and view internal guides              |

### 5.2 External Interfaces

- **Firebase Admin Console** – User and database management
- **OCR Engine** – `Tesseract.js` for parsing ticket numbers
- **Firestore** – JSON NoSQL structure for live reads/writes
- **Firebase Storage** – Uploaded documents/images

---

## 6. Component Design

### 6.1 SafeCountForm

```ts
const SafeCountForm: React.FC = () => {
  // useState to manage form fields
  // useAuth to get current user
  // submit handler: validate + save to Firestore
}
```

---

## 7. Security

| Concern              | Mitigation                                          |
|----------------------|-----------------------------------------------------|
| Data Leaks           | Firebase security rules + role-based access         |
| Auth bypass          | Use route guards + Firebase JWT validation          |
| OCR Abuse            | Limit image size and scan frequency                 |
| Unauthorized Uploads | Restrict access to Firebase Store via storage rules |

---
## 8. Design Considerations

### 8.1 Trade-offs

- Firesbase is fast to set up and scale, but less flexible than a custom backend
- NoSQL design (firestore) limits relational queries but improves speed
- Tesseract.js is client-side, which avoids server cost but may be slower

### 8.2 Performance
- All critical data uses indexed queries in Firestore
- Form input and component rendering are optimized with memoization and lazy loading
___
## 9. Future Enhancements
- Export PDFs or summaries for reporting
- Admin dashboard with user and activity analytics
- Extend lottery system to support full shift reconciliation
- Migrate to a PWA or wrap with Capacitor for mobile port
- Convert Tesseract.JS to a Python ML model

___
## 10. Appendix

- [SPMP](SPMP.md) - Project Management Plan
- [README](../README.md) - Overview and install instructions
- [MIT License](../LICENSE) - MIT License with disclaimer