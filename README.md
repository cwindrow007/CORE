# CORE - Chopper Operations Resource Engine

Core is a personal web-based application created to streamline and centralize daily operations and task for select
stores.  It was developed to unify previously separate tools like lane assignments, safe count tracking, lottery ticket 
logging, and internal documentation into a single interface for improved efficiency, accountability, and ease of use.

>**Important:** This project is a personal initiative by Christopher Windrow. It is **not affiliated with or endorsed 
> by Price Chopper, Market 32, or Golub Corporation**.

---

## Acknowledgments

Special thanks to **Tim Dziedzic** for his contributions to the original tools and processes that inspired parts of this project. His work on internal documentation and operational resources helped shape several CORE modules.

___

## Features

### Lane Assignment
- Auto-Generates cashier assignments based on availability and individual constraints.
- Manual override system for supervisors
- Supports designation of "individual" lanes

### Safe Count Logging
- Record daily safe balances
- secure historical archive
- export to PDF or CSV format

### Lottery Ticket Tracker (OCR)
- Scan tickets using OCR (Tesseract.js or image input)
- Logs and summarizes AM/PM Counts.
- Admin access for managing ticket types

### Resource Libary
- Upload and view internal documentation (PDFs, spreadsheets, instructions)
- Includes user guides, department transfer walkthroughs, and reference materials
___

## Tech Stack

| Layer         | Technology Used                    | Purpose                              |
|---------------|-------------------------------------|--------------------------------------|
| **Frontend**  | React + TypeScript                 | Component-based UI framework         |
| **Styling**   | TailwindCSS                        | Rapid and responsive design          |
| **Backend**   | Firebase (Auth + Firestore)        | Authentication & realtime database   |
|               | Optional: Node.js + Express        | Custom API layer (if needed later)   |
| **OCR Engine**| Tesseract.js                       | In-browser OCR for lottery tickets   |
| **Hosting**   | Firebase Hosting or Vercel         | Free, scalable deployment            |
| **Storage**   | Firebase Storage or Google Drive API| For storing internal documents       |
___

### Project Structure Planed

>**NEEDS TO BE FILLED**

___
## Roles & Permissions

| Role        | Capabilities                                            |
|-------------|---------------------------------------------------------|
| Employee    | Submit safe count and lottery scans                     |
| Supervisor  | Override lanes, access logs, view resource library      |
| Admin       | Manage users, ticket types, and full document access    |
___
##  Development Roadmap
> **NEEDS TO BE FILLED**

---

##  Contributions

This is a collaborative, personal tool. If you're a coworker and want to contribute or adapt part of your own documentation/macros into CORE, you're welcome to join. Just reach out to Christopher Windrow directly.

---

## Disclaimer

This software is a personal project developed and maintained by **Christopher Windrow**.  
It is **not affiliated with, endorsed by, or representative of** Price Chopper, Market 32, or Golub Corporation.

Use is voluntary and intended for internal organization at Store #189 only.  
Redistribution or commercial use without explicit permission is not allowed.

---
## License

This project is licensed under the [MIT License](LICENSE) with additional internal-use guidelines.