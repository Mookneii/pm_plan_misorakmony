# Business case: live quizzes for the IT department

## 1. Problem

Lecturers need to mark quiz answers and students may wait for feedback until after class. A live quiz tool can make feedback immediate, reduce repetitive marking and provide reusable evidence of student understanding. The estimates below are illustrative planning assumptions, not measured departmental data.

**Assumptions**
- Lecturers running quizzes: 10.
- Marking time potentially saved per lecturer: 1 hour/week.
- Teaching weeks per year: 30.
- Notional value of one hour: USD 10 (students are unpaid; used for economic comparison, not cash salary).
- Annual marking benefit: 10 × 1 × 30 × USD 10 = **USD 3,000/year**.
- SaaS price: **USD 15 per lecturer per month**, an assumption because current education pricing and local terms have not been verified for this exercise.
- Build effort: 490 hours × USD 10/hour = **USD 4,900 notional one-off cost**. This is an economic cost, not project cash spending.
- Build cash costs: USD 200 in the charter. For long-term comparison, annual hosting is estimated separately at USD 300/year.

## 2. Options

| Option | Description | One-off cost | Annual cost | Annual benefit |
|---|---|---:|---:|---:|
| A | Do nothing: continue current quiz and marking practice | USD 0 | USD 0 | USD 0 incremental benefit |
| B | Buy quiz SaaS at assumed USD 15 per lecturer per month | USD 0 setup assumed | USD 1,800 | USD 3,000 |
| C | Build Realtime Quiz with 490 hours of effort and local data ownership | USD 4,900 notional effort | USD 300 hosting | USD 3,000 marking benefit + USD 1,800 SaaS fee avoided = USD 4,800 gross annual benefit |

The SaaS fee avoided is a comparison benefit only if the department would otherwise buy option B. It is not a cash saving if the department would choose option A.

## 3. Comparison

Net annual benefit = annual benefit − annual recurring cost. Payback = one-off cost / net annual benefit.

| Option | Net annual benefit | Payback (years) | Sensitivity (6 lecturers) |
|---|---:|---:|---|
| B | USD 3,000 − USD 1,800 = **USD 1,200** | No one-off cost; immediate once service starts if benefits exceed fees | USD 1,800 − USD 1,080 = **USD 720/year** |
| C | USD 3,000 + USD 1,800 − USD 300 = **USD 4,500** | USD 4,900 / USD 4,500 = **1.09 years** | USD 1,800 + USD 1,080 − USD 300 = USD 2,580/year; USD 4,900 / USD 2,580 = **1.90 years** |

Sensitivity assumes 6 lecturers × 1 hour/week × 30 weeks × USD 10 = USD 1,800 benefit, and compares the build with six SaaS licences.

## 4. Benefits not priced

- Students receive immediate feedback while learning.
- The team gains practical experience with web development, real-time messaging, testing, deployment and project management.
- The department owns its product roadmap and can control its hosting and data arrangements.
- The platform has no per-student licence fee under the assumed build model.
- The project creates reusable course and portfolio evidence.

## 5. Risks per option

### A — Do nothing
- Marking effort and delayed feedback continue.
- The department misses the opportunity to build internal capability and may face fragmented quiz practices.

### B — Buy SaaS
- Actual education pricing, currency, tax, feature limits and privacy terms may differ from the USD 15/month assumption.
- Vendor dependence may limit data portability or customisation.
- Internet access or vendor outages may disrupt live sessions.

### C — Build
- Campus proxy rules may block WebSocket; test early and use SockJS if needed.
- Late answers may race with question closure, and client clocks may drift.
- PDF export may render Khmer names incorrectly.
- Scope creep or unfamiliar framework versions may put the week 7 MVP at risk.
- The USD 200 cash cap does not represent the economic value of 490 hours of effort.

## 6. Recommendation and review gate

**Recommend Option C, build Realtime Quiz**, provided the sponsor accepts the distinction between the USD 200 cash cap and the USD 4,900 notional effort cost. Estimated economic payback is about 1.09 years for 10 lecturers and about 1.90 years for 6 lecturers. The department also gains learning outcomes and more control over the product and data.

**Review gate:** If the week 7 MVP demo fails to demonstrate all Must features or has unresolved blocking defects, the sponsor should consider switching to Option B for the next semester and re-scope the build as a longer project. Before committing to SaaS, verify a real vendor's education price, data terms and required features. The recommendation and gate are referenced by the charter's purpose and justification.
