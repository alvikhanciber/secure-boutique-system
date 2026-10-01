# secure-boutique-system
A security-first boutique management system built with role-based access controls and encrypted databases.
# Secure Boutique Management System (SBMS)

A production-ready, security-first **Boutique Management System** built to handle custom client measurements, inventory lifecycle pipelines, and role-based operational order tracking. Designed with robust defensive engineering practices to safeguard Personally Identifiable Information (PII) and mitigate modern web vulnerabilities.

## 🚀 Key Features & Architecture
- **Role-Based Access Control (RBAC):** Granular routing separating capabilities for Owners (Admin), Designers, and Tailors.
- **Dynamic Measurement Tracking:** A version-controlled data ledger mapping evolving client body dimensions over time.
- **State-Machine Workflow:** Smooth operational pipeline tracking orders from Fabric Sourcing ➡️ Cutting ➡️ Stitching ➡️ Trials ➡️ Completed.

## 🛡️ Cybersecurity & Defensive Implementations
This project was engineered from the ground up to demonstrate enterprise-level application security standards:
* **Cryptographic Data Hashing:** User passwords are encrypted using **Argon2 / Bcrypt** to eliminate clear-text exposures.
* **PII Encryption at Rest:** Client measurements, phone numbers, and addresses are encrypted at the column level using **AES-256-GCM** algorithms.
* **SQL Injection (SQLi) Mitigation:** 100% database interactions utilize **Parameterized Queries / Prepared Statements** via an ORM layer.
* **Immutable Audit Logging:** Critical business actions (e.g., balance updates, order status shifts) are written to write-once logs with secure timestamps for compliance monitoring.

## 💻 Tech Stack
- **Backend:** Python (FastAPI / Django)
- **Database:** PostgreSQL (Relational multi-tenant layout)
- **Security Tools:** OWASP ZAP (Vulnerability scanning), Python Cryptography library

## 📈 Database Schema Diagram
[ Client ] 1 ── 🔑 Encrypted Link ── ⚡ Many [ Measurement History ]
│
└── 1 ── 🛒 Has Many ── 1 [ Orders ] ── 📊 Pipeline State

## 🛠️ Installation & Setup
1. Clone the repository:
   ```bash
   git clone https://github.com
   ```
2. Install secure dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Set up your environment variables (`.env`) for AES encryption keys and DB credentials (never commit this file).
4. Run the development server:
   ```bash
   unicorn main:app --reload
