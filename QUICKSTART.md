# Quickstart: five steps to a governed AI use case

**Version:** 2026-09-16  
**Author:** Samuel Tait  
**Licence:** CC BY 4.0 (see [LICENSE](LICENSE))

Use this checklist before deploying any AI-assisted capability. Each step links to the section of this guide that covers it in detail.

---

## Step 1: Describe the use case precisely

Before assessing the tier, write down:

- What task the AI assists with (be specific about what the AI does and what it does not do).
- Where the output meets the world: does it stay in the user's own work, inform a decision about someone else, go directly to the person it concerns, or prepare an action on an external system or person?
- The outcome for the person or organisation if the AI works correctly.
- The outcome if the AI produces an error that is not caught.
- Who benefits and who could be harmed.

If you cannot answer these five questions, you are not ready to assess the tier.

---

## Step 2: Work through the decision-rights question bank

→ [02-decision-rights/question-bank.md](02-decision-rights/question-bank.md)

Complete all ten sections. Do not skip sections because the use case seems low-risk. At the end, record:

- Whether both entry gates pass (a named accountable role with the competence to exercise the control; affected people identified with a redress route).
- Your provisional tier (Assist / Advise / Act with approval / Restricted).
- The accountable person (role).
- The material governance gaps to close before operation.
- The next review date.

Gaps in sections 3 (action boundary), 7 (human authority), and 8 (controls and escalation) default to the more demanding tier or Restricted until resolved. A failed entry gate is Restricted.

---

## Step 3: Select oversight patterns

→ [03-oversight-patterns/oversight-patterns.md](03-oversight-patterns/oversight-patterns.md)

Select the oversight patterns appropriate for the tier. The minimum:

| Tier | Minimum patterns |
|---|---|
| Assist | Workspace assistant |
| Assist, self-service variant | Workspace assistant (the affected person is the reviewer) + Sampled assurance |
| Advise | Second-reader review + Sampled assurance |
| Act with approval | Approval gate + Constrained execution + Independent monitoring |
| Restricted | Do not deploy |

Multiple patterns may combine. Check the failure modes for each pattern you select.

---

## Step 4: Define stop rules

→ [04-stop-rules/stop-rules.md](04-stop-rules/stop-rules.md)

For each relevant stop-rule category, define:

- The specific observable trigger.
- The detection method (automated or manual).
- The immediate containment action.
- The escalation owner (role, not just a name).
- The evidence to preserve.
- The recovery authority.
- The notification duty.

Include category 13, "No comparable case", in every stop-rule set: where the workflow meets a situation with no comparable precedent, the absence of a matching rule is not permission to proceed.

A use case with no defined stop rules has not completed its governance assessment.

---

## Step 5: Establish baseline measures before deployment

→ [05-adoption-measures/measures.md](05-adoption-measures/measures.md)

Before go-live, record:

- Current cycle time, cost/effort, quality/error rate, and demand volume.
- User or customer experience baseline.
- Risk events (complaints, escalations, errors) in the current process.

Select the adoption, human-control, outcome, risk/equity, and sustainment measures you will track after deployment. Assign a named owner and a review cadence to each.

Do not deploy until the baseline is recorded and the monitoring function is ready to operate.

---

## Minimum governance checklist

Before any AI-assisted capability goes live, confirm:

- [ ] Both entry gates pass and the evidence is recorded.
- [ ] Provisional tier is recorded, with rationale.
- [ ] Accountable person (role) is named and available.
- [ ] All material gaps identified in the question bank are closed.
- [ ] Oversight pattern(s) are implemented and tested.
- [ ] The two pre-deployment tests (consistency under reframing; knows what it does not know) have been run and passed, and the results are on the AI register entry.
- [ ] Stop rules are defined, and the technical or process mechanism to detect and act on each trigger is in place.
- [ ] Baseline measures are recorded.
- [ ] Monitoring function is assigned and operational.
- [ ] A post-deployment review date is set (within 90 days of go-live).
- [ ] For Act with approval: the approval gate has been tested; rollback has been tested; the AI register entry is complete.
- [ ] For any use case affecting rights, essential services, or vulnerable people: specialist review is complete.

---

## What to do if you are unsure of the tier

Assume the output travels further than you think, and assign the tier whose control point sits later (Advise rather than Assist; Act with approval rather than Advise). That tier carries more governance. If you cannot exercise that control, the use case is Restricted until you can. It is easier to relax governance after evidence of safe operation than to recover from a governance failure after deployment.
