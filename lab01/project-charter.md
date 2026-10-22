# Project charter: Realtime Quiz platform

| Field | Value |
|---|---|
| Version | 1.0 (draft for sponsor approval) |
| Date | 2026-09-29 |
| Sponsor | Head of the IT department |
| PM | [Supervising lecturer's name], supervising lecturer |

## 1. Purpose and justification

Lecturers spend time marking quizzes, and students may wait for feedback until after class. Realtime Quiz will let instructors author multiple-choice quizzes, host timed live sessions, and provide immediate feedback and a live leaderboard. The project aims to reduce marking effort, improve student engagement and provide a reusable teaching tool within 14 weeks and a USD 200 cash cap. See [`business-case.md`](business-case.md) for the investment comparison and review gate.

## 2. Objectives and success criteria

| # | Objective (what will be true) | Success criterion (number + week) |
|---|---|---|
| O1 | Deliver the MVP with quiz authoring, timed sessions, scoring, feedback, authentication and leaderboards. | All Must features pass the acceptance checklist at the week 7 demo. |
| O2 | Demonstrate a pilot session for students. | At least 50 students participate, with 0 unresolved blocking defects, by week 14. |
| O3 | Deliver real-time updates within the latency target. | Broadcast latency is at most 500 ms at the 95th percentile in the 100-simulated-student load test by week 12. |
| O4 | Verify capacity and authoritative timer behaviour. | One instance supports 20 sessions × 100 participants on 2 vCPU and 2 GB RAM, with client timer drift under 200 ms, by week 12. |
| O5 | Deliver maintainable and accessible software. | Line coverage is at least 80%, CI is green on every merge, and keyboard access/WCAG AA contrast checks pass by week 13. |

## 3. High-level scope

### In scope
- Multiple-choice quiz authoring and editing.
- Timed live quiz sessions with a six-character joining code.
- Real-time student participation and answer submission.
- Instant feedback, scoring and live leaderboards.
- Authentication and role-based access for instructors and students.
- Multiple concurrent quiz sessions.
- Responsive web interface and keyboard-accessible controls.
- Analytics and CSV/PDF result export, subject to schedule and MVP priority.

### Out of scope
- Native iOS or Android applications.
- Question types other than multiple choice, including free-text answers.
- Video conferencing.
- Learning Management System (LMS) integration.
- Multi-node scaling or distributed deployment.
- Chat during sessions and a shared question bank unless approved as stretch work.

## 4. Milestones

| Week | Milestone | Ends process group |
|---|---|---|
| 1 | Charter approved, team formed and initial stakeholders identified | Initiating |
| 3 | Scope, schedule, budget, quality plan, risk register and deployment design baselined | Planning |
| 5 | Quiz authoring, accounts and security implemented; live-session core in progress | Executing |
| 7 | MVP demo: all Must features demonstrated | Executing |
| 10 | Analytics/export and selected polish features integrated; test plan updated | Executing |
| 13 | Hardening complete; load test, accessibility review, data approval and runbook ready | Monitoring and controlling |
| 14 | Pilot with 50 students, lessons learned, handover and closure | Closing |

## 5. Budget summary

**Effort**
- Students: 4 × 14 weeks × 8 h/week = **448 h**
- Project manager: 14 weeks × 3 h/week = **42 h**
- Total planned effort: 448 h + 42 h = **490 person-hours**

**Cash**
- Hosting: 4 months × USD 25/month = USD 100
- Domain: 1 × USD 15 = USD 15
- Optional paid tools: 1 allowance × USD 60 = USD 60
- Cash subtotal before reserve: USD 100 + USD 15 + USD 60 = USD 175
- Reserve: USD 25, equal to 25 / 175 × 100 = **14.3% of pre-reserve cash lines**
- Total cash budget: USD 175 + USD 25 = **USD 200**

Hosting duration and domain/tool prices are planning assumptions to confirm before spending. Effort is separate from cash spending; the business case evaluates its notional economic value.

## 6. Assumptions
- Four students can contribute 8 hours each per week and the supervising lecturer can contribute 3 hours per week.
- The department provides timely feedback and a sponsor who attends week 7 and week 13 decision gates.
- A Linode VPS at gicitc.com can be provisioned within the cash cap.
- The campus network permits WebSocket traffic or a SockJS fallback is acceptable.
- Pilot participants and test accounts are available before week 14.

## 7. Constraints
- The project runs for 14 weeks from 2026-09-29; the pilot must occur in week 14.
- The MVP demo must take place in week 7.
- Cash spending must not exceed USD 200 without written sponsor approval.
- The team consists of four students with a combined planned contribution of 448 hours.
- Deployment uses one server instance; multi-node scaling is excluded.
- Secrets must not be committed to the repository.

## 8. High-level risks
- Campus proxy restrictions may block WebSocket; test early and use SockJS fallback if needed.
- Late answers may race with question closure and client clocks may drift; make the server timer authoritative and test boundary cases.
- PDF export may render Khmer names incorrectly; test representative names.
- Newer Spring Boot/Spring Security versions may have limited tutorial coverage; validate dependencies early.
- Could features may expand scope and threaten the week 7 MVP; protect the Must-feature baseline.

## 9. Project manager authority

The PM may assign work, schedule meetings, approve technical choices within the agreed architecture, manage the risk log and re-plan within the 490 planned person-hours and USD 200 approved cash cap. The PM may not independently increase scope, move the week 7 MVP demo or week 14 pilot, exceed the cash cap, or waive a Must-feature criterion. Those changes require the sponsor's written approval. The PM will escalate material risks and proposed baseline changes to the sponsor within five working days.

## 10. Approval

Sponsor: ______________________________  Date: ______________

Project manager: _______________________  Date: ______________
