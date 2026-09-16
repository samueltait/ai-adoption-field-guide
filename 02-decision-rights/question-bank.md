# Decision-rights question bank

**Version:** 2026-09-16  
**Last reviewed:** 2026-09-16  
**Author:** Samuel Tait  
**Licence:** CC BY 4.0 (see [LICENSE](../LICENSE))

---

## Purpose

Work through these questions before deploying an AI-assisted workflow. The answers determine a provisional tier, identify the accountable and approving roles, and surface the material governance gaps that must be closed before operation begins. Unanswered material questions default to escalation or Restricted until they are resolved.

The output is a single assessment record for the use case.

**What "decision rights" means here.** In this bank the phrase covers the whole allocation of authority over an AI-assisted workflow: who is accountable, who approves, who operates, who monitors, and who can stop the capability. Some task-allocation frameworks use it more narrowly, for final authority alone, alongside initiative and control as separately allocated elements (see [GLOSSARY.md](../GLOSSARY.md) and [REFERENCES.md](../REFERENCES.md) entry [10]). If your organisation uses the narrower sense, record which sense you mean in the assessment record so the two are not conflated.

---

## How to use this bank

1. Complete all ten sections in order. Do not skip sections because a use case seems low-risk.
2. At each section, note whether the answer supports a lower tier, a higher tier, or Restricted.
3. Where questions cannot be answered, note the gap and treat it as a reason to apply the more conservative tier.
4. Record the provisional tier at the end, with the name of the person accountable for the assessment.
5. Revisit the assessment when any of the change-control conditions in section 10 occur.

---

## Section 1: Purpose and service ownership

**What outcome is this AI capability intended to produce?**  
Describe the specific task the AI assists with and the benefit to the organisation or the people it serves. Be concrete: what changes, for whom?

**Who owns the service that this AI capability operates within?**  
Name the service or function owner: the person accountable for overall outcomes, not just the technology.

**Who is the decision owner for the specific actions this AI capability informs or executes?**  
Identify the person (or role) who has authority to make the decision or take the action that the AI output feeds into. This is the accountable person for the AI-assisted step.

**What happens if this capability is unavailable?**  
Describe the fallback: manual process, delayed service, or no service. The fallback informs the urgency and risk tolerance.

---

## Section 2: Affected parties and harm potential

**Who can benefit from this capability?**  
Be specific about the population: volume, characteristics, and how they interact with the output.

**Who can be harmed by an error, bias, or misuse of this capability?**  
Consider direct users, third parties affected by decisions, and groups who are not present in the process but are affected by its outputs.

**Does the output affect rights, eligibility, money, safety, reputation, or access to services?**  
For each that applies, describe the mechanism: how does the AI output translate into that effect?

**Are any affected people in a vulnerable group: children, people with disability, people experiencing financial hardship, people who are not fluent in the language of the interface, or others who may face additional harm?**  
If yes, what additional protections are required?

**Is there a feedback pathway for affected people to raise concerns, correct errors, or seek redress?**  
Describe it. If one does not exist, it must be created before deployment at Advise and above.

---

## Section 3: Action boundary

**Where does the output meet the world?**  
Does it stay in the user's own work (Assist), inform a decision about someone else (Advise), go directly to the person it concerns (Assist, self-service variant), or prepare an action on an external system or person (Act with approval)? This is the primary tier question.

**Is the AI drafting, recommending, approving, or executing?**  
Select the most consequential role the AI plays in the workflow. If it does more than one, assess the most consequential.

**What external systems, records, or people can the AI capability affect?**  
List them. For each, note whether the AI writes to, reads from, or triggers that system.

**What is the maximum scope of a single undetected error?**  
How many records, people, transactions, or communications can be affected before an error is identified and contained?

**Is there a technical mechanism that prevents the AI from executing a consequential action without human authorisation?**  
If yes, describe it and confirm it has been tested. If no, and the use case is at Act with approval, this is a blocking gap.

---

## Section 4: Data authority

**What data does the AI capability use?**  
List sources, formats, and whether data is retrieved at runtime or embedded in the model or prompt.

**Under what authority is this data used?**  
Identify the legal basis, consent, contractual permission, or policy that authorises each data source for this purpose.

**What data is prohibited from use in this capability?**  
State the data types, fields, or categories that must never be included in the AI input or output.

**Are any of the following categories present: health, financial, biometric, children's data, criminal record, or immigration status?**  
If yes, what additional controls are required and in place?

**What happens to output that contains data from a prohibited category or that exceeds the approved purpose?**  
Describe the detection and containment mechanism.

---

## Section 5: Reversibility and reach

**Can an error be detected before it causes harm?**  
By whom, using what signal, in what timeframe?

**If an error reaches an external system, person, or record, can it be corrected?**  
Describe the correction mechanism, the time required, and the residual harm after correction.

**What is the maximum number of people or actions that can be affected by a single error before it is detected and contained?**  
Record the number and the detection point. This is an input to whether the control mechanism is adequate, not a tier setting on its own.

**What is the reputational, financial, or service-continuity consequence of a visible error?**  
Describe the worst plausible scenario and the organisation's tolerance for it.

---

## Section 6: Evidence and uncertainty

**What is the evidence base for the AI output?**  
Describe the data and reasoning the AI draws on. Is the source visible to the reviewing person?

**How does the system behave when it encounters missing, conflicting, or out-of-distribution input?**  
What does it output? Does it flag uncertainty or proceed silently?

**What is the known error rate or quality range for outputs in this context?**  
If no measurement exists, explain how it will be established before deployment.

**Is there a mechanism for the AI to express uncertainty, request more information, or decline to answer?**  
Describe it, or note its absence.

**What validation method does the reviewing person use to assess an AI output?**  
The method must match the competency of the person and the consequence of the decision.

---

## Section 7: Human authority

**Who may authorise the action or decision that the AI output feeds into?**  
Name the role (not just the person). The role must have formal delegated authority for this class of action.

**Who may override an AI output or recommendation?**  
Name the role and describe how an override is recorded.

**Who may pause or suspend the AI capability without escalating for permission?**  
Name the role and confirm that person has the technical access to effect the pause.

**Who may investigate an error, complaint, or anomaly?**  
Name the role and the process for initiating an investigation.

**Who may retire or decommission the use case?**  
Name the role and confirm a decommission plan exists.

**Is each of these people available within the timeframe required by the workflow?**  
If any role cannot be filled within the required window, the control mechanism cannot be exercised: move the control point, redesign the workflow, or treat the use case as Restricted.

---

## Section 8: Controls and escalation

**Which conditions must stop the AI from processing further or executing an action?**  
List the stop rules for this use case. For each, specify:
- The trigger condition (observable, not assumed)
- How the trigger is detected (automated or manual)
- The immediate containment action
- The escalation owner
- The evidence to preserve
- The recovery authority

See [04-stop-rules/stop-rules.md](../04-stop-rules/stop-rules.md) for the category set.

**Are there mandatory escalation triggers from the risk tier model that apply to this use case?**  
Review the list in [01-risk-tiers/risk-tier-model.md](../01-risk-tiers/risk-tier-model.md) and confirm which apply.

**What must be recorded for each AI-assisted action or decision?**  
Describe the audit record: what is captured, where, by whom, and how long it is retained.

**Can the audit record be accessed by an accountable person, auditor, or affected party in the event of a dispute?**  
Confirm access controls and retrieval process.

---

## Section 9: Monitoring and review

**Which quality, accuracy, and harm signals will be monitored?**  
List the measures. For each, specify the data source, the person responsible for monitoring, the review frequency, and the threshold that triggers a response.

**Which adoption measures will be tracked?**  
See [05-adoption-measures/measures.md](../05-adoption-measures/measures.md) for the measure set.

**What override and escalation patterns will be monitored?**  
The override rate is a signal about output quality and reviewer confidence. Who reviews it, and what rate triggers a review?

**Who reviews the monitoring data?**  
Name the role and the cadence. Monitoring that no one acts on is not a control.

**When will the first post-deployment review occur?**  
Specify a date, not just a period. The first review should occur within 90 days of deployment.

**What would cause an extraordinary review between scheduled reviews?**  
List the conditions.

---

## Section 10: Change control

**Which changes require the assessment to be repeated before resuming operation?**

The following changes require a new assessment or formal review of this document:

- Substituting or updating the AI model or a prompt that materially changes output behaviour.
- Adding, removing, or changing a data source.
- Extending the workflow to a new user group, population, or geographic scope.
- Scaling volume significantly beyond what was assessed.
- Adding a new action or output type not covered by this assessment.
- Organisational changes that affect the accountable, approving, or monitoring roles.
- A new legal, regulatory, or policy obligation that applies to this use case.
- A material error, complaint, or control failure.

**Who has authority to approve a change without a new assessment?**  
Minor operational changes (phrasing, formatting) may not require reassessment; this authority should be named and bounded.

**Is this use case registered in the organisation's AI register?**  
If yes, confirm the register entry is current. If no, create an entry before deployment at Act with approval.

---

## Provisional tier and sign-off

| Field | Record |
|---|---|
| Use case name | |
| Assessed by | |
| Assessment date | |
| Provisional tier | Assist / Advise / Act with approval / Restricted |
| Tier rationale | (key factors from sections 1-10) |
| Material gaps identified | (gaps to close before operation) |
| Next review date | |
| Accountable person (role) | |
| Accountable person (name) | |

Unanswered material questions in sections 1-10 must be recorded as gaps. Gaps in sections 3, 7, and 8 default to the more demanding tier or Restricted until resolved. A failed entry gate (no accountable role with the competence to exercise the control; affected people not identified or without a redress route) is Restricted.
