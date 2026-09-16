# Adoption and benefits-realisation measures

**Version:** 2026-09-16  
**Last reviewed:** 2026-09-16  
**Author:** Samuel Tait  
**Licence:** CC BY 4.0 (see [LICENSE](../LICENSE))

---

## Purpose

These measures help an organisation establish whether an AI capability is being used as intended, whether human control is functioning, and whether the intended benefits have actually been realised, net of the costs of control, adoption, and any harms that occurred.

Measuring usage is not the same as measuring benefit. This framework distinguishes them.

---

## Before you measure: establish a baseline

No measure is meaningful without a pre-deployment baseline. Capture the following *before* the AI capability goes live:

| Baseline metric | How to capture |
|---|---|
| Cycle time for the target task | Time study or records analysis across a representative period |
| Cost or effort per unit of the target task | Staff time, rework, escalation, error-correction costs |
| Quality or error rate | Review of completed work: defects, complaints, rework, or override rates in the manual process |
| Demand volume | Number of requests, cases, or interactions per period |
| User or customer experience | Survey, complaint rate, or time-to-resolution in the pre-AI process |
| Risk events | Frequency of errors, near-misses, complaints, or escalations in the pre-AI process |
| Rework rate | Proportion of completed work requiring correction |

Without a baseline, benefits claims are asserted, not evidenced.

---

## Measure set

### 1. Adoption measures

These measures assess whether the AI capability is being used, by whom, in what way, and whether that use is appropriate.

| Measure | Definition | Data source | Cadence | Owner |
|---|---|---|---|---|
| Eligible-user activation rate | Proportion of users who have used the capability at least once, of those who are authorised and have been trained | Usage logs, training records | Monthly | Service owner |
| Appropriate-use rate | Proportion of AI-assisted interactions that fall within the defined scope of the use case | Audit sample or automated scope check | Monthly | Risk or quality function |
| Repeat use | Proportion of activated users who use the capability regularly (e.g. weekly) | Usage logs | Monthly | Service owner |
| Completion rate | Proportion of AI-assisted interactions that are completed by the user, versus abandoned | Usage logs | Monthly | Service owner |
| Training and competency completion | Proportion of users who have completed required training, by role | Training records | Quarterly | L&D or service owner |
| Abandonment rate | Rate at which users start but do not complete an AI-assisted interaction | Usage logs | Monthly | Service owner |
| Workflow coverage | Proportion of eligible interactions that are AI-assisted, of the total that could be | Records analysis | Quarterly | Service owner |

**Interpretation:** Low activation or high abandonment may indicate a usability problem, a trust deficit, or a gap between the capability and the actual workflow. High inappropriate-use rates indicate a governance or training failure.

---

### 2. Human control measures

These measures assess whether human oversight is functioning as required.

| Measure | Definition | Data source | Cadence | Owner |
|---|---|---|---|---|
| Review time | Time between AI output and the reviewing person's decision or action | Audit logs or workflow timestamps | Monthly | Oversight function |
| Override rate | Proportion of AI outputs that the reviewing person rejected, modified, or escalated | Decision records | Monthly | Oversight or quality function |
| Override reason categories | Classification of why overrides occurred: error in output, missing information, policy conflict, or other | Decision records (manual tagging or structured field) | Monthly | Oversight function |
| Escalation rate | Proportion of AI-assisted interactions that were escalated to a higher authority | Escalation logs | Monthly | Oversight function |
| Approval latency (Act with approval) | Time between the AI preparing an action and the approver authorising it | Approval-gate logs | Monthly | Oversight function |
| Rollback events | Number of approved actions that were subsequently rolled back, and time to rollback | Audit logs, rollback records | Monthly | Oversight function |
| Unresolved exceptions | Number of stop-rule activations that have not been resolved within the defined timeframe | Stop-rule and escalation logs | Weekly | Oversight function |

**Interpretation:** A very low override rate may indicate automation bias rather than high quality. A rising override rate may indicate model drift or scope creep. An approval latency that consistently exceeds the workflow's time budget indicates the approval structure needs redesign.

---

### 3. Outcome and benefit measures

These measures assess whether the intended operational or user outcomes have been achieved.

| Measure | Definition | Data source | Cadence | Owner |
|---|---|---|---|---|
| Cycle-time change | Change in the time to complete the target task, compared to the pre-AI baseline | Records analysis | Quarterly | Service owner |
| Avoided rework | Reduction in the rate or volume of rework, compared to baseline | Quality or rework records | Quarterly | Quality function |
| Service quality | Change in error rates, complaint rates, or quality indicators relevant to the service, compared to baseline | Quality records, complaint logs | Quarterly | Service owner |
| Accessibility or satisfaction | Change in the experience of the people using or affected by the service, compared to baseline | Survey, net promoter, or time-to-resolution | Quarterly | Service owner |
| Capacity released | Measured reduction in staff time required for the target task | Time study or records analysis | Quarterly | Service owner |
| Capacity redeployed | Demonstration that released capacity has been directed to other value-creating work (not merely absorbed) | Records analysis, manager attestation | Annually | Executive sponsor |
| Realised financial benefit | Quantified financial benefit where evidenced: cost reduction, revenue, or avoided cost, net of AI operating costs and control costs | Finance records | Annually | Finance or executive sponsor |

**Critical distinction:** Gross savings (the gross reduction in time or cost for the AI-assisted task) are not the same as realised benefit (the net organisational outcome after all costs, including oversight, correction, and adoption costs). Report both, separately.

---

### 4. Risk and equity measures

These measures assess whether the AI capability is causing harm, disproportionate impact, or control failures.

| Measure | Definition | Data source | Cadence | Owner |
|---|---|---|---|---|
| Harmful-error rate | Rate of errors that caused measurable harm to an affected person (not just quality defects) | Complaints, escalations, risk events | Monthly | Risk function |
| Complaints and appeals | Number of complaints and appeals about AI-assisted outputs or decisions, and the proportion upheld | Complaints records | Monthly | Complaints or risk function |
| Privacy and security events | Number of data or security incidents involving the AI capability | Incident logs | Monthly | Security and privacy function |
| Outcome differences across population groups | Whether AI-assisted outputs or decisions differ systematically across groups defined by a protected characteristic (age, gender, disability, cultural background, or others relevant to the service) | Records analysis, audit sample | Quarterly | Equity or risk function |
| Stop-rule activations | Number of stop-rule activations by category, and the proportion resolved within the defined timeframe | Stop-rule logs | Monthly | Oversight function |

**Interpretation:** The absence of complaints is not evidence of the absence of harm, especially for population groups that may have less power or capacity to complain. Active monitoring is required.

---

### 5. Sustainment measures

These measures assess whether the capability remains fit for purpose over time.

| Measure | Definition | Data source | Cadence | Owner |
|---|---|---|---|---|
| Control-test pass rate | Proportion of scheduled control tests (approval gate, stop-rule, rollback) that pass | Test records | Quarterly | Technical or quality function |
| Model and prompt change frequency | Number of changes to the model, prompt, or data configuration, indicating ongoing tuning and the need for reassessment | Change log | Monthly | Technical owner |
| Drift indicators | Change in output distribution, quality signals, or population characteristics that may indicate model or data drift | Monitoring system | Monthly | Technical or quality function |
| Operating cost | Total cost of operating the AI capability per period, including licensing, compute, oversight, and correction costs | Finance records | Quarterly | Service or finance owner |
| Benefit persistence | Whether the benefits measured at the first post-deployment review are sustained or eroding | Outcome measures, repeated at each review | Annually | Executive sponsor |

---

## Measure ownership and governance

Each measure must have:

- A **definition** (what is counted and how)
- A **baseline** (the pre-deployment value)
- A **data source** (where the data comes from)
- A **cadence** (how often it is reviewed)
- A **target or decision threshold** (what level triggers a response)
- A **segmentation rule** where relevant (e.g. by user group, population sub-group, or service line)
- A **named owner** (the role responsible for reviewing and acting on the measure)

Measures that no one reviews are not controls.

---

## Reporting

Produce a brief summary of adoption, control, outcome, risk/equity, and sustainment measures at each scheduled review. The summary should state:

- Which measures are within expected range, with trend direction
- Which measures have crossed a threshold and what response was taken
- Which measures could not be collected and why
- Whether the provisional tier remains appropriate

The summary is retained as part of the use-case governance record.
