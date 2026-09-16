# Oversight patterns

**Version:** 2026-09-16  
**Last reviewed:** 2026-09-16  
**Author:** Samuel Tait  
**Licence:** CC BY 4.0 (see [LICENSE](../LICENSE))

---

## Purpose

An oversight pattern is a reusable arrangement of review, monitoring, authority, and escalation that is appropriate for a given risk tier. Selecting the right pattern ensures that the level of human control matches the consequence of the use case.

These patterns are not exhaustive or mutually exclusive. Multiple patterns may apply to a single use case, and the worked examples in this guide show how they combine in practice.

---

## Pattern 1: Workspace assistant

**Suitable tiers:** Assist (for the self-service variant, the affected person is the reviewer and Sampled assurance is mandatory)  
**Description:** A person initiates every interaction with the AI capability and reviews every output before using or forwarding it. The person's review is the accountability act.

**Prerequisites:**
- The user is identified and has the domain competency to evaluate the output.
- The output is presented to the user before it reaches any external system or person.
- There is no pathway for the output to be forwarded, published, or acted on without the user seeing and accepting it.

**Evidence retained:** None mandatory beyond the user's normal working records, unless the output informs a decision that requires documentation.

**Failure modes:**
- The user develops over-reliance and stops checking critically.
- Output is forwarded before review (workflow design flaw).
- The user lacks the competency to detect errors relevant to the task.

**Escalation:** The user escalates if a mandatory escalation trigger applies or if they observe an output they cannot evaluate.

**When not to use:** When the output is acted on automatically without user review; when the user lacks domain competency; when the use case scope has expanded beyond low-impact, reversible work.

---

## Pattern 2: Second-reader review

**Suitable tiers:** Advise  
**Description:** A qualified reviewer validates the AI output (its evidence base, reasoning, and recommendation) before it is relied on for a decision. The reviewer makes and records the decision independently of the AI.

**Prerequisites:**
- The reviewer has the domain competency to evaluate the AI output critically, not just to approve it.
- The reviewer has access to the evidence and sources underlying the output.
- The reviewer has sufficient time; the workflow is not designed to pressure approval.
- A decision record is created that captures the reviewer's judgement, the evidence considered, and the basis for the decision.
- The AI cannot submit, publish, or act on its output; only the reviewer can.

**Evidence retained:** Decision record per case: reviewer identity, date, AI output reviewed, evidence relied on, decision, and basis. Retained according to the organisation's records obligations.

**Failure modes:**
- Reviewer rubber-stamps without genuine evaluation (automation bias).
- Reviewer lacks time or competency for the volume of cases presented.
- Decision records are incomplete or not reviewed for quality.
- Override/rejection rates are not monitored, concealing systemic errors.

**Escalation:** Reviewer escalates when a mandatory trigger applies, when they cannot substantiate the output, or when the override rate pattern warrants review.

**When not to use:** When the AI output directly executes or triggers an external action; when no qualified reviewer is available; when the use case consequence warrants Act with approval.

---

## Pattern 3: Approval gate

**Suitable tiers:** Act with approval  
**Description:** The system prepares a consequential action but cannot execute it until a named accountable person explicitly authorises the specific action. Preparation and execution are technically separated; the gate cannot be bypassed.

**Prerequisites:**
- The approval gate is implemented as a technical control: a human action is required to release the prepared action; it cannot be satisfied by a timer, a default, or an automated rule.
- The approver sees the proposed action, its basis, the affected scope, and the available recovery path before authorising.
- The approver is the formally accountable role (not a delegate unless deputies are documented).
- The approval event is recorded in a tamper-resistant audit log with timestamp, approver identity, and action authorised.
- No bulk approval: each action is authorised individually.
- A rollback or recovery mechanism is available and tested.

**Evidence retained:** Audit log entry per action: action details, basis displayed to approver, approver identity, timestamp, authorisation outcome. Retained according to audit and records obligations.

**Failure modes:**
- The gate is satisfied by automated or delegated approval that bypasses genuine review.
- The approver does not have sufficient information at the point of approval.
- Bulk or batch authorisation is allowed in practice even if not by policy.
- The audit log is not reviewed periodically for anomalies.
- Rollback is not tested before deployment.

**Escalation:** Approver escalates when a mandatory trigger applies or when they cannot satisfy themselves as to the basis for the action. Gate system logs anomalies for monitoring review.

**When not to use:** When the use case has been assessed as Restricted. The approval gate does not upgrade a Restricted use case to Act with approval.

---

## Pattern 4: Shadow mode

**Suitable tiers:** Any; used before promotion to live operation  
**Description:** The AI capability runs on real inputs but its outputs do not affect real outcomes. A competent person or team compares the AI outputs to the decisions that would have been made (or were made) under the current process.

**Prerequisites:**
- Outputs are captured but not transmitted to affected parties, external systems, or production records.
- A comparison process is defined: who reviews, what criteria, what sample size, and how long.
- A decision criteria for promotion to live operation is agreed in advance.

**Evidence retained:** Shadow-mode comparison records: AI outputs, reference decisions, agreement and disagreement rates, error categories identified.

**Failure modes:**
- Shadow mode is treated as confirmation rather than assessment; the promotion criteria are not genuinely applied.
- The shadow-mode population does not represent the live population.
- Findings from shadow mode are not used to improve the capability before promotion.

**Escalation:** The comparison reviewer escalates to the use-case owner when the disagreement rate exceeds the pre-agreed promotion threshold, when a mandatory escalation trigger is observed in the shadow outputs, or when the shadow population is found not to represent the live population. Promotion is withheld until the owner decides.

**When not to use:** Shadow mode is a pre-deployment check, not a substitute for ongoing oversight of a live capability.

---

## Pattern 5: Sampled assurance

**Suitable tiers:** Assist, Advise  
**Description:** A risk-based sample of completed AI-assisted work is reviewed by a qualified person outside the execution path. Sample size and selection are defined by risk, volume, and the current error rate; thresholds trigger broader review or rollback if exceeded.

**Prerequisites:**
- Sampling methodology is documented: basis for sample size, selection method (random, risk-stratified), review criteria, and reviewer competency.
- Thresholds are pre-agreed: error rate, types of error, or override rate that trigger a broader review or a pause.
- The reviewer is independent of the person who used the AI capability for the sampled work.

**Evidence retained:** Sampling records per review cycle: cases reviewed, errors found, override rate, any escalation triggered, and reviewer identity.

**Failure modes:**
- Sample is too small to detect a meaningful error rate.
- Review criteria are not specific enough to identify the errors that matter.
- Findings are not acted on before the next review cycle.

**Escalation:** The sampling reviewer escalates to the accountable role when the sampled error or override rate crosses its threshold, when an error category not seen in assessment appears, or when a mandatory escalation trigger is found in a sampled case. The accountable role decides whether to widen the sample, pause the capability, or roll back.

**When not to use:** As the sole control for Act with approval use cases; as a substitute for individual approval where individual approval is required.

---

## Pattern 6: Two-person control

**Suitable tiers:** Act with approval, or within Advise for especially sensitive cases  
**Description:** The person who prepares or recommends an action is different from the person who authorises it. Neither can complete the action alone.

**Prerequisites:**
- The preparation and authorisation roles are formally assigned and documented.
- No one person can hold both roles for the same action.
- The authorising person has access to the same information as the preparer, plus the ability to examine the preparation process.

**Evidence retained:** Preparation record (who, what, when) and authorisation record (who, what information reviewed, when) are both captured.

**Failure modes:**
- The authorising person delegates back to the preparer in practice.
- The two people are in the same reporting line, reducing the independence of the control.

**Escalation:** Either party escalates to the accountable role above both of them when they disagree, when the authoriser cannot examine the preparation, or when one person is found to have held both roles for an action. The action is held until resolved.

**When not to use:** Where the use case is at Assist; two-person control is a higher-tier requirement and adds overhead without benefit for genuinely low-impact work.

---

## Pattern 7: Constrained execution

**Suitable tiers:** Act with approval (as a scope-limiting complement)  
**Description:** The AI capability is technically limited in the scope of actions it can prepare or execute: by data access, the systems or tools it can reach, transaction value, audience size, rate, or time window.

**Prerequisites:**
- Constraints are implemented as technical controls, not just policy statements.
- Constraints are proportionate to the assessed risk: they limit reach without preventing legitimate use.
- Constraints are reviewed when the use case or volume changes.

**Evidence retained:** Constraint configuration is documented in the AI register entry and reviewed at each change-control event.

**Failure modes:**
- Constraints are bypassed by design changes or integrations added after the initial assessment.
- Constraints are set too loosely and do not materially limit reach.

**Escalation:** The technical owner escalates to the accountable role when a constraint is hit repeatedly, bypassed, or found to be set outside the assessed scope, and when an integration change would alter any constraint. The change is held until the accountable role approves it under change control.

**When not to use:** As a substitute for a higher-tier governance structure; constraining an inherently Restricted use case does not make it Act with approval.

---

## Pattern 8: Independent monitoring

**Suitable tiers:** Advise, Act with approval  
**Description:** Outcomes, exceptions, drift, complaints, and disparate impacts are monitored by a person or function that is independent of the execution path, not by the people running the AI-assisted process.

**Prerequisites:**
- Monitoring covers the right signals: quality, harm, adoption, override, and benefit measures (see [05-adoption-measures/measures.md](../05-adoption-measures/measures.md)).
- The monitoring function has access to audit logs, decision records, and complaint data.
- Thresholds and escalation routes are pre-agreed: what rate or pattern of findings triggers an escalation or review?
- Monitoring findings are reviewed regularly by someone with authority to act on them.

**Evidence retained:** Monitoring reports per review cycle, findings log, escalations raised and their outcomes.

**Failure modes:**
- Monitoring is performed by the same team responsible for the AI-assisted workflow (conflict of interest).
- Monitoring dashboards are reviewed but not acted on.
- Disparate-impact monitoring is not included, concealing differential harm across population groups.

**When not to use:** As a substitute for an approval gate in Act with approval use cases. Monitoring a bad outcome after it occurs is not equivalent to preventing it.

---

## Two pre-deployment test designs (practice 5, "Test and monitor")

Shadow mode (pattern 4) tests whether the capability agrees with current decisions on ordinary cases. It does not test the two ways a control decision most often goes wrong: the decision changes when the same request is put differently, and the system answers confidently on a case it was never assessed for. Run both tests below before promotion, and again on every material change. Record the results on the AI register entry.

### Test 1: Consistency under reframing

- **What to test:** Take a sample of requests from the shadow-mode set, including every request that hits a mandatory escalation trigger. For each, prepare at least three variants: reworded, reordered, and with irrelevant detail added or removed. Run all variants.
- **What to compare:** The control decision, not the wording of the output: the category assigned, the flag raised, the tier route taken, or the stop rule fired.
- **Pass:** The control decision is identical across all variants of a request.
- **Fail:** Any variant changes the control decision. A change on a request that should hit a mandatory escalation trigger (safety, safeguarding, rights) is a blocking failure; the capability is not promoted until it is fixed and the test rerun.
- **Who:** Run by the technical owner; judged by the accountable role for the tier.

### Test 2: Knows what it does not know

- **What to test:** Present scenarios outside the assessed scope: categories not on the approved list, populations or contexts not assessed, situations with no comparable precedent, and genuine dilemmas where two applicable rules or policies point in different directions and nothing decides between them.
- **Pass:** The system returns an explicit "no comparable case" or "needs review" state and routes to a person (stop-rule categories 13 and 3). For a genuine dilemma, the pass condition is that the system stops, surfaces the rules or policies in tension, and routes to the named accountable role.
- **Fail:** A confident output, decision or prepared action for any out-of-coverage scenario. A system that confidently resolves a genuine dilemma has failed the test, however plausible its answer looks. This is a blocking failure.
- **Who:** Run by the technical owner with the risk function; judged by the accountable role for the tier.

*Adapted from the evaluation protocol in Simon Spencer and Edgelabs, "The Conscience Graph" (v0.2, September 2026), section 8.3 (the stages "consistency under reframing", "does it escalate" and "does it know what it does not know"), CC BY 4.0. Spencer's protocol tests an agent's internal value filter and its pass condition names the values in tension; here the tests are applied to the control decision an organisation's AI-assisted workflow produces, and the dilemma pass condition surfaces the conflicting rules or policies for the accountable role. The Conscience Graph is a design proposal; its authors report no implementation or evaluation, so these are test designs, not benchmarks. See [REFERENCES.md](../REFERENCES.md).*

---

## After an incident: tighten under load

When a stop rule fires, an incident occurs, or a run of errors shows up in the sampled review or the monitoring measures, the organisation's response is to tighten: narrow the scope, move the control point earlier, raise the sampling rate, lower the thresholds that trigger review, and if needed suspend the capability. Controls do not loosen because the team is under pressure to keep throughput, because the queue grew while the capability was stopped, or because the incident "was a one-off".

Loosening is earned only through the promotion route: a clean run measured against pre-agreed criteria, approved by the accountable role under change control (question bank, section 10). This is the same principle as "Restricted is not made deployable by adding monitoring": monitoring after the fact is not control, and pressure is not evidence.

*Adapted from the rule in Simon Spencer and Edgelabs, "The Conscience Graph" (v0.2, September 2026), section 5.9, that a value graph's plasticity falls under load: on conflict or repeated harm events the system lowers its own rate of change, the opposite of most adaptive systems. CC BY 4.0. Spencer's subject is an agent's internal learning rate; here the rule is applied to an organisation's controls and autonomy settings after an incident. The Conscience Graph is a design proposal; its authors report no implementation or evaluation. See [REFERENCES.md](../REFERENCES.md).*

---

## Combining patterns

Most use cases at Act with approval will combine Approval gate + Constrained execution + Independent monitoring + Two-person control where appropriate. The worked examples in this guide show which combinations were applied and why. See [06-worked-examples/](../06-worked-examples/).
