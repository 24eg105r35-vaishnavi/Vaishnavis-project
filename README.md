# STUDENT ACHIEVEMENT PORTAL
> **One place where every certificate, hackathon, medal, paper, internship and prize a student earns is uploaded, verified and never lost again.**

---

## 🛠️ Technology Stack
- **Framework:** Spring Boot 4.x / 3.x (Web, Security, Data JPA, Validation, DevTools)
- **Build System:** Apache Maven
- **Templating:** Thymeleaf (Server-rendered HTML, search-engine indexable, CSRF protected)
- **Styling:** Hand-written Vanilla CSS (~25KB, CSS Grid, Flexbox, Custom Properties) — Zero framework payload
- **Database:** MySQL 8.0 / Embedded H2 (MySQL Mode) with automated seed data
- **Vault:** Local File Vault with SHA-256 Checksum deduplication and integrity sealing
- **Security:** Spring Security with BCrypt hashing, Role-Based Access Control (RBAC), and transactional audit logging

---

## 🚀 Running the Project

```bash
cd backend
mvn spring-boot:run
```

The portal runs on **`http://localhost:8085`** (port configurable in [application.properties](backend/src/main/resources/application.properties)).

## Sample Data

The app seeds synthetic student and verifier records only when `APP_DEMO_PASSWORD` is set. Configure a strong local value before starting the app; all seeded accounts use that value. The seed accounts use reserved `example.edu` addresses and are for local development only.

| Role | Seeded account |
| :--- | :--- |
| Student | `student@example.edu` |
| Faculty verifier | `faculty@example.edu` |
| Sports verifier | `sports.verifier@example.edu` |
| Placement verifier | `placement.verifier@example.edu` |
| Admin | `admin@example.edu` |

PowerShell:

```powershell
$env:APP_DEMO_PASSWORD = "choose-a-strong-local-password"
```

For the MySQL profile, configure `DB_USERNAME` and `DB_PASSWORD` in the environment rather than putting credentials in the properties file.

---

---

## 🎯 Completed Feature Checklist (All 13 Features)

1. **Feature 01: Accounts and Roles** — Student, Faculty, Admin, Placement & Sports verifiers. BCrypt password hashing.
2. **Feature 02: Profile and Portfolio** — Public shareable URL (`/portfolio/STUDENT-001`), SEO JSON-LD schema, privacy gates (Public, College Only, Private), print-ready resume style.
3. **Feature 03: Certificate Upload** — Camera capture scanner (`capture="environment"`), pre-flight file validation, SHA-256 checksum deduplication, isolated file vault.
4. **Feature 04: Hackathons** — Team size, individual role, outcome (Winner/Finalist), project demo URL.
5. **Feature 05: Sports Achievements** — Sport name, format (singles/team), medal position (Gold/Silver/Bronze), routed to Physical Education.
6. **Feature 06: Paper Publications** — Journal/Conference/Patent, DOI number validation, ISSN/ISBN, venue, author position.
7. **Feature 07: Internships** — Company, duration, stipend, work mode, offer letter + completion certificate support.
8. **Feature 08: Competitions** — Coding contests, technical fests, rank secured, prize details.
9. **Feature 09: Faculty Verification** — Pre-filtered queue, side-by-side proof preview workspace, approve/reject/return for correction with reason, append-only verification log.
10. **Feature 10: Centralised Achievement Database** — Full-text search by roll number, student name, branch, category, level; one-click CSV export.
11. **Feature 11: Analytics & Reports** — Zero-framework server-rendered SVG bar charts, NAAC Criterion 5 compliance tables, NBA criteria, permanent snapshot archiver.
12. **Feature 12: Notifications** — In-database notification queue, unread count badge in header, mark as read drawer.
13. **Feature 13: Admin Console** — Configurable category schemas, configurable scoring weight matrix (Section 13), verifier routing, immutable audit log table.
