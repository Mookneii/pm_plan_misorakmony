# Post-mortem: CampusPay wallet (fictional case)

## 1. Timeline and sources

This analysis uses the fictional CampusPay scenario supplied in the Lab-01 brief; there are no external sources for its fictional events.

| # | When | Event | Source |
|---|---|---|---|
| 1 | Project start | A university asks its IT unit to build a cashless payment app for canteen purchases and library fines within one semester. | Fictional case from Lab-01 |
| 2 | Initiation | The head of finance sponsors the idea by email but does not attend project reviews. | Fictional case from Lab-01 |
| 3 | Early planning | The lead developer also acts as project manager and coder. | Fictional case from Lab-01 |
| 4 | Requirements gathering | Requirements expand from canteen payments to bus tickets and parking after a survey. | Fictional case from Lab-01 |
| 5 | Before launch | No end-to-end test with real card terminals is performed. | Fictional case from Lab-01 |
| 6 | Launch day | Terminals reject 40% of payments and the canteen queue doubles. | Fictional case from Lab-01 |
| 7 | Three days after launch | The app is withdrawn. | Fictional case from Lab-01 |
| 8 | Five months later | A reduced version relaunches for canteen payments only. | Fictional case from Lab-01 |

## 2. Classification and organisation

**Project / programme:** CampusPay was primarily a project to deliver a new payment app. The added bus-ticket and parking requirements expanded scope; the scenario does not establish separately governed projects with shared programme benefits.

**Structure and PM authority:** The lead developer combined project management and coding responsibilities. This weakened separation between delivery, independent testing and oversight, and the scenario does not show authority to reject extra scope.

**Sponsor, charter, PMO:** A nominal sponsor existed by email, but the head of finance did not participate in reviews. The scenario provides no evidence of an approved charter, measurable success criteria or a project management office (PMO).

## 3. Success criteria

The stated criterion was essentially “launch in September.” A date alone is not a sufficient definition of success. Missing measures included terminal transaction success rate, end-to-end test coverage, maximum queue time, reconciliation, security, user acceptance, recovery procedures and reliability.

The team ignored users who experienced longer queues, finance staff who needed reliable and reconcilable payments, and operations staff who needed a tested deployment and support process. The launch date was met, but the product did not deliver its expected benefit reliably.

## 4. Process groups and knowledge areas

| Process group | What went wrong or was skipped |
|---|---|
| Initiating | Sponsorship was only an email commitment, with no evidence of a charter defining authority, scope boundaries or measurable outcomes. |
| Planning | Scope expanded to bus tickets and parking without evidence of impact analysis, a revised baseline, or agreed budget and schedule. |
| Executing | The team did not conduct an end-to-end test with real card terminals before release. |
| Monitoring and controlling | The sponsor did not attend reviews and no control caught the 40% terminal failure risk before launch. |
| Closing | The launch had to be withdrawn; no planned acceptance, handover or lessons-learned review is described before launch. |

**Three knowledge areas most responsible**

1. **Scope management:** Requirements expanded from canteen and library use to buses and parking, with no evidence of formal change control. The later reduced-scope relaunch supports this finding.
2. **Quality management:** No real-terminal test occurred before launch, and 40% of payments failed on day one. Acceptance testing should have verified real payment flows and terminal compatibility.
3. **Stakeholder management:** The finance sponsor did not attend reviews, and the lead developer carried both PM and coding roles. People able to approve scope, validate operations and challenge readiness were not effectively engaged.

## 5. Ethics

**Decision examined:** Launching without testing real card terminals exposed students and staff to avoidable disruption. **Responsibility** required testing and risk escalation; **respect** required considering users waiting in queues; **fairness** required reliable access for all users; and **honesty** required reporting readiness and uncertainty accurately rather than treating a calendar date as proof of success.

## 6. What our project will do differently

| # | Commitment (We will ...) | Measured by | By week | Charter line |
|---|---|---|---|---|
| 1 | We will obtain formal sponsor approval before treating the plan as authorised. | Signed charter, named PM, approved scope and budget | 1 | Section 10 approval; milestone week 1 |
| 2 | We will protect the MVP from uncontrolled scope additions. | Must features traced to acceptance criteria; changes logged and sponsor-approved | 3 and reviewed at week 7 | Section 3 scope; section 9 PM authority; milestone week 7 |
| 3 | We will demonstrate the complete Must-feature flow before declaring the MVP successful. | Week 7 demo checklist passes, CI green, no unresolved blocking defects | 7 | Objective O1; milestone week 7 |
| 4 | We will test realistic load, latency and timer behaviour before inviting pilot students. | 100 simulated students; p95 latency ≤500 ms; timer drift <200 ms; test report reviewed | 12 | Objectives O3 and O4; section 8 risks |
| 5 | We will not run the pilot until data handling and operational handover are ready. | Data approval, 80% line coverage, accessibility checks, runbook and backup/recovery evidence | 13 | Objective O5; section 7 constraints; milestones weeks 13-14 |
