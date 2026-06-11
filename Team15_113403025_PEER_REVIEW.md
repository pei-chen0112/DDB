# Peer Review Report

> **Instructions:** Complete this form **individually and independently**.
> Do not discuss your ratings with teammates before submitting.
> Submit via EEClass as a **separate, confidential submission** — not in the shared team repo.
> Your teammates will not see this report.
>
> Reference the team's `WORK_ALLOCATION_TEMPLATE.md` when completing this form.

---

## Your Details

| Field | Your answer |
|-------|------------|
| Full Name | (請填寫你的英文或中文全名) |
| Student ID | (請填寫你的學號) |
| Team ID | (請填寫你的組別，例如 Team01) |
| Date submitted | 2026-06-11 |

---

## Rating Scale

| Rating | Meaning |
|--------|---------|
| **5** | Exceeded expectations — delivered more than agreed; helped teammates; consistently high quality |
| **4** | Met expectations fully — delivered exactly what was agreed; on time; good quality |
| **3** | Mostly met expectations — minor shortfalls; one or two items completed late or with help |
| **2** | Partially met expectations — noticeable gaps; teammates had to cover some tasks |
| **1** | Did not meet expectations — significant tasks left incomplete; very limited contribution |

---

## Section A — Self-Assessment

### A1. What did you personally implement?

> *Your answer:*
> I was primarily responsible for the core database architecture, query implementation, and the final design documentation. Specifically, I:
> 1. Designed the complete relational schema (`schema.sql`), ensuring proper 3NF normalization for the seating system and strategic de-normalization for the station lines.
> 2. Implemented complex PostgreSQL transactional queries (`queries.py`), specifically the atomic `execute_booking` and `execute_cancellation` functions with proper rollback mechanisms.
> 3. Implemented and debugged the Neo4j graph algorithms (`queries.py`), ensuring robust error handling for edge cases (e.g., fixing the `query_delay_ripple` 0-hop Cypher syntax issue).
> 4. Authored the comprehensive Database Design Document (Sections 1 through 6).

---

### A2. What challenges did you face?

> *Your answer:*
> One major challenge was dealing with the strict Cypher syntax requirements in Neo4j. During the implementation of the `query_delay_ripple` function, the initial syntax `*1..$hops` caused system crashes when `hops=0`. I had to dive deep into APOC documentation and debug the logic, successfully resolving it by modifying the range to `*0..$hops` to handle boundary cases gracefully. Additionally, compiling the comprehensive Design Document required aligning everyone's technical implementations into a unified academic format.

---

### A3. Self-rating

| Criterion | Rating (1–5) | Justification (1–2 sentences) |
|-----------|-------------|-------------------------------|
| I delivered the tasks assigned to me in the work allocation | 5 | I successfully delivered the core database architecture and managed the heavy documentation workload. |
| The quality of my work was satisfactory | 5 | I fixed critical runtime bugs (like the 0-hop graph query) to ensure we meet all assessment criteria. |
| I communicated well and kept the team informed | 5 | I regularly updated the team on schema changes and query requirements. |
| I met deadlines agreed within the team | 5 | All my assigned components and the final documentation were completed on time. |
| **Overall self-rating** | 5 | I consistently delivered high-quality work and went beyond by ensuring documentation completeness. |

---

### A4. Estimated contribution percentage

> My estimated contribution: **34%**

---

## Section B — Peer Assessments

---

### B1. Assessment of Teammate 1

| Field | Your answer |
|-------|------------|
| Teammate's full name | (請填寫組員1的姓名) |
| Teammate's student ID | (請填寫組員1的學號) |

#### What did this teammate deliver?

> *Your answer:*
> They were primarily responsible for the backend database architecture and querying logic. Specifically, they:
> 1. Designed the Unified Relational Schema (`schema.sql`), ensuring proper normalization, strict ON DELETE cascade/restrict strategies, and correct TIMESTAMPTZ data types.
> 2. Implemented the PostgreSQL seeding script (`seed_postgres.py`) and integrated Argon2 password hashing for secure user credential storage.
> 3. Authored core relational queries (`databases/relational/queries.py`), including atomic transaction logic and dynamic fare calculations.
> 4. Debugged and finalized the Neo4j graph seeding (`seed_neo4j.py`) and APOC Dijkstra routing queries.

#### Did their actual contribution match the agreed work allocation?

> *Your answer (Yes / Mostly / Partially / No — with explanation):*
> Yes, they completed all their assigned tasks effectively and delivered high-quality database scripts.

#### Peer rating for this teammate

| Criterion | Rating (1–5) | Justification (1–2 sentences) |
|-----------|-------------|-------------------------------|
| Delivered the tasks assigned in the work allocation | 5 | They successfully set up the unified schema and security features (Argon2). |
| Quality of their work was satisfactory | 5 | Their work on the seeding scripts laid a solid foundation for the entire project. |
| Communicated well and kept the team informed | 5 | They were highly responsive during database integration. |
| Met deadlines agreed within the team | 5 | All foundational scripts were delivered on time. |
| **Overall rating for this teammate** | 5 | Excellent contribution to the project's backend foundation. |

#### Estimated contribution percentage for this teammate

> My estimate of their contribution: **33%**

---

### B2. Assessment of Teammate 2

| Field | Your answer |
|-------|------------|
| Teammate's full name | (請填寫組員2的姓名) |
| Teammate's student ID | (請填寫組員2的學號) |

#### What did this teammate deliver?

> *Your answer:*
> They were responsible for refining the Relational database module and resolving crucial environment configurations. Specifically, they:
> 1. Refined `schema.sql` to eliminate naming conflicts and ensure data integrity.
> 2. Implemented relational query functions handling both read-only and complex write operations.
> 3. Debugged the `seed_postgres.py` script to align with the schema.
> 4. Successfully resolved tricky environment configuration issues (Docker port mapping Postgres 5433 vs 5432 and local IP connectivity).
> 5. Reviewed and corrected critical syntax errors in the graph module (`databases/graph/queries.py`).

#### Did their actual contribution match the agreed work allocation?

> *Your answer (Yes / Mostly / Partially / No — with explanation):*
> Yes, they stepped up to resolve critical environment and port mapping issues, which was essential for the team to run the system locally.

#### Peer rating for this teammate

| Criterion | Rating (1–5) | Justification (1–2 sentences) |
|-----------|-------------|-------------------------------|
| Delivered the tasks assigned in the work allocation | 5 | They successfully refined the code and fixed environment bugs. |
| Quality of their work was satisfactory | 5 | Their debugging skills (resolving Docker port conflicts) saved the team massive amounts of time. |
| Communicated well and kept the team informed | 5 | Actively helped others troubleshoot local setup issues. |
| Met deadlines agreed within the team | 5 | Consistently resolved blocker bugs rapidly. |
| **Overall rating for this teammate** | 5 | Outstanding problem-solving and code refinement contributions. |

#### Estimated contribution percentage for this teammate

> My estimate of their contribution: **33%**

---

## Section C — Contribution Percentage Summary

| Member | Your estimated % | Notes |
|--------|----------------|-------|
| Yourself | 34% | Core architecture, graph algorithms, comprehensive documentation |
| Teammate 1 | 33% | Schema integration, Argon2 hashing, Neo4j seeding & routing |
| Teammate 2 | 33% | Environment debugging (Docker/Ports), relational queries, code refinement |
| **Total** | **100%** | |

---

## Section D — Overall Team Reflection

### D1. What went well in the team's collaboration?

> *Your answer (2–4 sentences):*
> Our team had an incredibly balanced workload (34/33/33). Everyone pulled their weight and took ownership of highly technical tasks. We effectively divided the backend operations, with each member contributing to both the relational and graph databases while cross-reviewing each other's code to catch bugs early.

---

### D2. What would you do differently if you did this project again?

> *Your answer (2–4 sentences):*
> Because all three of us had to frequently edit the core files (`schema.sql` and `queries.py`), we occasionally stepped on each other's toes regarding syntax and naming conventions. If we did this again, I would establish stricter Git branch management rules (like using independent Feature Branches and Pull Requests) right from day one to avoid merge conflicts.

---

### D3. Is there anything else the markers should know about team dynamics or individual contributions?

> *Your answer (or "Nothing to add"):*
> Nothing to add. The team worked perfectly together.

---

## Declaration

I confirm that this peer review reflects my honest and independent assessment.
I understand it will be kept confidential from my teammates.

**Signed:** (請在這裡打上你的名字) **Date:** 2026-06-11