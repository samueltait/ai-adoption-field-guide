# Risk tier model

**Version:** 2026-09-16  
**Last reviewed:** 2026-09-16  
**Author:** Samuel Tait  
**Licence:** CC BY 4.0 (see [LICENSE](../LICENSE))

---

## Purpose

This model helps an organisation decide, before deployment, which form of human control it must exercise over an AI-assisted workflow, and what governance that form of control requires. The tier is a statement about the organisation: what it must be able to do, who must be able to do it, and what must be in place before the workflow operates.

Tiering is based on the proposed use case and the organisation's governance capacity, not on the model brand or the technology stack.

---

## How the tiers are organised

The model is built on Australia's Guidance for AI Adoption (the six essential practices) and the NIST AI Risk Management Framework (Govern, Map, Measure, Manage). It uses them in three different ways.

**The primary axis is practice 6, "Maintain human control".** The tiers are distinguished by which human-control mechanism the organisation can actually exercise over the workflow, unit by unit:

| Mechanism | Where the control point sits | Tier |
|---|---|---|
| Per-output review | A competent person inside the organisation sees each output and can change or discard it before it is used in their own work. | **Assist** |
| Per-decision record | A qualified person makes and records each decision that an output informs. The output is a recommendation; the record is the control. | **Advise** |
| Per-action gate | Each output is a prepared action on an external system or person. A technical gate holds the action until a named accountable person authorises that specific action. | **Act with approval** |
| No exercisable mechanism | None of the above can be maintained for this use case, or the mechanism that could be maintained is not adequate for the impacts identified. | **Restricted** |

The tiers are ordered by how far the AI's output travels before a person controls it. The further it travels, the more the organisation has to build to keep control, so practices 3, 4 and 5 scale up across the tiers.

**Practices 1 and 2 are entry gates.** "Decide who is accountable" and "Understand impacts and plan accordingly" decide whether a tier is reachable at all. If the organisation cannot name a person with the authority and competence to exercise the mechanism, or cannot understand and manage the impacts on the people affected, the use case is Restricted regardless of how attractive the mechanism looks.

**Each tier is defined by its binding governance constraint,** the thing the organisation must be able to do. What the AI does is a consequence of that constraint, not the definition of the tier.

**Tiers are not risk ratings.** Consequence severity, reach and reversibility are inputs to the assessment (see "Tier assessment: what to consider"). They tell you whether the mechanism you can exercise is adequate for what is at stake, and how strong the supporting controls must be. A high-consequence use case does not "earn" a later control point; it is more likely to need the control point moved earlier, or to be Restricted.

**Related work.** The idea of grading AI decision authority in tiers builds on Paweł Huryn's decision-type hierarchy (see [Related work](#related-work) below). This guide's contribution is the Australian regulatory grounding, the mapping to the six practices and the NIST functions, the decision-rights question bank, the oversight patterns, the stop-rule categories and the worked examples.

---

## Entry gates

Both gates must pass before a tier can be assigned. A gate that fails sends the use case to Restricted; the failed gate becomes the re-entry condition.

### Gate 1: Decide who is accountable

- Can the organisation name a role (not only a person) with the authority to exercise the human-control mechanism this use case needs, and with deputies where the workflow cannot wait?
- Does that role have the competence to check, decide or authorise what the AI produces, and the time to do it at the expected volume?
- Are provider and platform responsibilities for the AI capability known to that role?
- Is the use case covered by the organisation's AI governance arrangements, and is the accountable role trained for it?

If the answer to the first two questions is no, the mechanism cannot be exercised and the use case is Restricted.

### Gate 2: Understand impacts and plan accordingly

- Who is affected by the outputs, inside and outside the organisation, and have they been identified and engaged?
- Can an affected person raise a concern, have an error corrected, and seek redress, through a route that exists before deployment?
- Will systemic issues (patterns of error, complaint or disparate outcome) be noticed by someone with authority to act?

If affected people cannot be identified, or no feedback and redress route can be established, the use case is Restricted.

---

## Tier overview

| Tier | Human-control mechanism | Binding constraint | What this means for the AI's role |
|---|---|---|---|
| **Assist** | Per-output review | A competent, accountable person must see every output and be able to change or discard it before it is used in their own work. | Drafting, summarising, reformatting and option generation for that person's use. |
| **Advise** | Per-decision record | A qualified reviewer must make and record each decision the output informs, with the evidence visible, the time to disagree, and a redress route for the person affected. | Recommendations, classifications and assessments that a person decides on. |
| **Act with approval** | Per-action gate | A formally delegated role must be able to see and authorise each prepared action before release, through a technical gate that cannot be bypassed, with rollback tested and the use case on the AI register. | Prepared actions on external systems or people, released one at a time on authorisation. |
| **Restricted** | None exercisable | The organisation cannot exercise any of the three mechanisms for this use case, or the mechanism it can exercise is not adequate for the impacts identified at Gate 2. | No operational use until a documented reassessment closes the gap. |

**Self-service variant of Assist.** Where the output goes directly to the person it concerns (a public-facing chat assistant, a self-service portal), per-output review by the organisation is not exercisable per interaction. This is not ordinary Assist. It is permitted only under the conditions in "Assist, self-service variant" below; if any condition cannot be met, the output must be released by a person (Advise or Act with approval) or the use case is Restricted.

---

## Governance requirement mapping

Every one of the six practices applies at every tier. The table shows the form each practice takes at each tier, not whether it is switched on. The Restricted column shows what must be evidenced for the use case to re-enter assessment. The two entry-gate practices must be satisfied before any tier is reachable.

| Practice and sub-area | Assist | Advise | Act with approval | Restricted (re-entry) |
|---|---|---|---|---|
| **Decide who is accountable** (entry gate) | | | | |
| 1.1 Accountable people | Named user accountable for each use | Named qualified reviewer role; decision owner named | Formally delegated approver role with documented deputies | No role with authority and competence can be named; re-entry requires one |
| 1.2 Supply chain accountabilities | Provider terms known to the service owner | Provider responsibilities for the recommendation path documented | Provider responsibilities for the action path documented, including failure handling | Provider responsibilities documented before re-entry |
| 1.3 AI literacy and training | User trained to check outputs | Reviewer competence evidenced | Approver and operators trained; refreshed on change | Training plan is part of re-entry |
| 1.4 AI governance framework | Covered by existing workplace policy | Use case assessed under the organisation's AI governance arrangements | Formal policy, delegated-authority instrument and audit access | Framework records the restriction and its re-entry conditions |
| **Understand impacts and plan accordingly** (entry gate) | | | | |
| 2.1 Identify and engage stakeholders | Own team | Affected people identified and consulted | Affected people identified, consulted and told how the gate works | Affected people cannot be identified or engaged; re-entry requires both |
| 2.2 Establish feedback and redress processes | User can correct or discard; existing complaints route | Affected person can challenge the decision through a named route | Affected person can challenge the action; reversal route named | Redress route established before re-entry |
| 2.3 Monitor for systemic issues | Sampled assurance where outputs leave the team | Override and complaint patterns reviewed | Independent monitoring of outcomes and disparities | Residual manual process monitored for the same harm |
| **Measure and manage risks: implement AI-specific risk management** | | | | |
| 3.1 Fit-for-purpose risk management framework | Existing operational risk process | AI-specific assessment added | AI-specific assessment with a named risk owner | Assessment records why risk cannot be managed within tolerance |
| 3.2 Assess AI system risks | Assessment against the factor list below | Full assessment, documented | Full assessment, reviewed by the risk function | The assessment is the re-entry document |
| 3.3 Implement controls | Data boundary; review before use | Reviewer competence; decision record; evidence visibility | Gate; separation of preparation and execution; rollback; constrained execution | No available control contains the risk |
| 3.4 Monitor and report incidents | Existing incident route | AI-specific incident category | AI-specific incident category with stop-rule log | Incidents in the manual process inform re-entry |
| **Share essential information** | | | | |
| 4.1 Maintain an AI register | Recorded at team level | Register entry | Register entry including gate design and approver role | Register records the restriction |
| 4.2 Transparency and explainability | User can see what the AI drew on | Evidence and sources visible to the reviewer | Basis, scope and recovery path visible to the approver | Inability to explain outputs is itself a reason to restrict |
| 4.3 Supply chain transparency | Provider named | Provider and model version recorded | Components contributing to each prepared action known to the approver | Documented before re-entry |
| 4.4 AI-generated content transparency | Internal use; disclosed if forwarded | Disclosed to anyone relying on the recommendation | Disclosed to the affected person | Not applicable until re-entry |
| **Test and monitor** | | | | |
| 5.1 Pre-deployment testing | Basic validation in context | Shadow-mode comparison against current decisions | Gate and rollback tested; shadow mode | Testing cannot demonstrate control |
| 5.2 Monitor system performance | Sampled review | Error and override rates tracked | Live monitoring independent of the execution path | Not applicable until re-entry |
| 5.3 Additional testing proportionate to risk | On change | On change or drift | Before go-live and on every material change | Part of re-entry |
| 5.4 Data and cybersecurity measures | Approved data boundary | Plus access controls on evidence | Plus injection and abuse controls on the action path | Part of re-entry |
| **Maintain human control** (primary axis) | | | | |
| 6.1 Maintain human oversight and control | Per-output review | Per-decision record | Per-action gate | No exercisable mechanism |
| 6.2 Decommission when appropriate | User can stop using it | Named role can suspend | Documented pause and decommission plan, tested | Decommissioned or never deployed |
| **NIST AI RMF** | | | | |
| Govern | Existing policy and roles | AI-specific roles and decision records | Formal delegated authority, audit and register | Governance records the restriction |
| Map | Use case and data boundary described | Affected people and decision context mapped | Action path, external effects and recovery mapped | Mapping shows control cannot be established |
| Measure | Basic validation and sampling | Error, override and complaint measures | Gate, rollback and outcome measures | Measurement cannot demonstrate control |
| Manage | Review before use | Decision record and redress | Gate, rollback, constrained execution, independent monitoring | No response keeps risk within tolerance |

---

## Tier definitions

### Tier 1: Assist (per-output review)

**Human-control mechanism:** A competent person inside the organisation sees each output and can change or discard it before it is used in their own work. The person's review is the accountability act.

**Binding constraint:** The organisation must be able to guarantee that no output is used, forwarded or acted on without that person having seen it, and that the person has the competence to check it.

**Entry gates:** Gate 1: the user is named and trained. Gate 2: the output stays within the user's own work; where it can leave the team, a correction and complaints route exists.

**Consequence for the AI's role:** Drafting, summarising, reformatting, generating options for the user's review. The user then acts on their own judgement.

**Required governance (minimum):**
- A named user is accountable for each use.
- The user understands the task domain and that AI output requires checking.
- Data used is within the organisation's approved boundary for the workflow.
- Basic validation has confirmed plausible outputs in this context.
- Errors can be found and corrected by the user without consequential delay or harm.
- Where outputs can leave the team, a sampled review runs and AI-generated content is disclosed.

**Not permitted at Assist:**
- Output used without the user's review.
- Output that informs a decision about a person outside the user's own work (that is Advise).
- Output forwarded directly to an external person or system without review (that is the self-service variant, Advise or Act with approval).
- Output that determines eligibility, moves money, creates a legal commitment or alters rights or access to services.
- Reliance by a user who lacks the competence to check the output.

**Entry evidence:** The user can describe what the AI does, what it does not do, and how they verify and use the output; the data boundary and validation check are recorded.

**Escalation condition:** Any mandatory escalation trigger; the output begins to inform decisions about other people; the use case expands beyond its assessed scope; a pattern of errors emerges that the user cannot reliably detect.

---

### Tier 2: Advise (per-decision record)

**Human-control mechanism:** A qualified person makes and records each decision that the output informs. The output is advisory; the recorded decision is the control.

**Binding constraint:** The organisation must be able to provide a reviewer with the competence, evidence, time and authority to decide differently from the AI, and a redress route for the person the decision affects.

**Entry gates:** Gate 1: the reviewer role and the decision owner are named. Gate 2: affected people are identified and can challenge the decision.

**Consequence for the AI's role:** Recommendations, assessments, classifications, summaries and structured options with supporting evidence, for a person to decide on. The AI does not initiate external action.

**Required governance (minimum):**
- A qualified reviewer is identified, available, and able to evaluate the output critically rather than approve it.
- Affected people are identified and a feedback or redress route exists.
- A risk assessment of the AI system is complete; controls are proportionate.
- AI-generated content is disclosed to anyone relying on the recommendation.
- Evidence and sources underlying the output are visible to the reviewer before the decision.
- A decision record captures the reviewer's judgement, the evidence relied on and the basis for the decision.
- Error rates, override rates and complaint patterns are monitored.
- The reviewer has time, information and authority to disagree or escalate.

**Not permitted at Advise:**
- Execution of any action by the system on the basis of its output.
- Bulk approval without individual review of each case.
- Deployment where the reviewer lacks the competence or time for the volume presented.
- Decisions whose consequence, if the reviewer errs, is not adequate for a record-based control (see Restricted).

**Entry evidence:** Risk assessment complete; reviewer role appointed and trained; performance-monitoring baseline recorded; feedback and redress route operating.

**Escalation condition:** Any mandatory escalation trigger; override or error rate crosses its threshold; the reviewer role is vacant; the use case changes scope or population; the output starts to prepare actions rather than inform decisions.

---

### Tier 3: Act with approval (per-action gate)

**Human-control mechanism:** Each output is a prepared action on an external system or person. A technical gate holds the action until a formally accountable person authorises that specific action. Preparation and execution are separated by design.

**Binding constraint:** The organisation must be able to operate a gate that cannot be bypassed, staffed by a role with documented delegated authority and deputies, with rollback tested, the use case on the AI register, and monitoring independent of the execution path.

**Entry gates:** Gate 1: the approver role, its delegated authority and its deputies are documented. Gate 2: affected people can challenge an action and have it reversed.

**Consequence for the AI's role:** Preparing communications, transactions, record updates and case routings, released one at a time on authorisation.

**Required governance (minimum):**
- All Advise requirements, plus:
- A formal accountability structure with documented delegated authority (a role, not a person) and named deputies.
- Provider and platform responsibilities for the action path documented, including failure handling.
- An AI register entry that records the use case, the gate design and the approver role, available to reviewers and auditors.
- The approver knows which components contributed to the prepared action.
- Testing proportionate to risk before deployment: the gate functions as designed; rollback or recovery is tested.
- Live monitoring that runs independently of the execution path.
- A documented pause and decommission plan that a named role can execute.
- The approver sees the action, its basis, the affected scope and the recovery path before authorising.
- No silent, delegated-to-AI or bulk approval; each action is authorised individually.
- A tamper-resistant audit log retained under the organisation's records obligations.

**Not permitted at Act with approval:**
- Approval by anyone other than the accountable role or a documented deputy.
- Execution without a recorded approval event.
- Actions that cannot be explained or substantiated at the point of approval.
- Actions assessed as Restricted, whatever the approval capacity.

**Entry evidence:** All requirements documented and tested; the gate functions correctly in pre-production; AI register entry complete; approver role appointment documented; decommission plan available; rollback tested.

**Escalation condition:** Any mandatory escalation trigger; approver and deputies unavailable; the gate fails or is bypassed; the action scope, data or model changes materially; an audit finding is unresolved; rollback cannot be executed.

---

### Tier 4: Restricted (no exercisable control)

**Human-control mechanism:** None. The organisation cannot exercise per-output review, a per-decision record or a per-action gate for this use case, or the mechanism it can exercise is not adequate for the impacts identified at Gate 2.

**Binding constraint:** The use case must not operate until a documented reassessment shows how the blocking gap has been closed.

**This is a governance restriction, not a claim about legality.** A use case may be Restricted even if no law prohibits it.

**A use case is Restricted when any of the following holds:**
- Gate 1 fails: no role with the authority and competence to exercise the required mechanism can be named.
- Gate 2 fails: affected people cannot be identified or engaged, or no redress route can be established.
- The action is too fast, too voluminous, too complex or too consequential for any of the three mechanisms to be maintained.
- The consequence of a failure of the mechanism is severe or irreversible enough that no available approval or review arrangement is adequate.
- Risk cannot be managed within the organisation's tolerance with the controls available to it.
- The use case has produced, or could produce, discriminatory outcomes, rights violations or safety risks the organisation is not prepared to accept.

**Consequence for the AI's role:** No operational use. Redesign the use case, narrow its scope, move the control point earlier, use a non-AI process, or obtain specialist or legal authority before reassessment.

**Required governance (minimum):**
- The restriction and its reason are recorded in the AI register.
- The failed gate or blocking factor is named as the re-entry condition.
- Any residual manual process is monitored for the same harm.

**Not permitted at Restricted:**
- Operational use in any form, including pilots on real people or records.
- Re-entry by adding monitoring alone. Monitoring a bad outcome is not the same as preventing it.

**Entry evidence (for re-entry to assessment):** A documented reassessment showing how the failed gate or blocking factor has been closed, signed by the accountable role, with the proposed mechanism and its supporting controls described.

**Escalation condition:** Any attempt to operate the use case, or a materially similar one, without reassessment; discovery that a Restricted capability has been running; a proposal to re-enter without the evidence above.

---

## Assist, self-service variant

Where the person who receives the output is the person it concerns, and is outside the organisation (a student, a customer, a resident), the organisation cannot review each output before that person sees it. The affected person exercises per-output review; the organisation exercises control over the source set and the routing. This is permitted as a variant of Assist only when all of the following hold:

1. The output is informational and creates no commitment, determination or change of state.
2. Every answer is drawn from a source set that a named accountable role approves and maintains.
3. Matters that affect rights, eligibility, money, safety or access to services are excluded by routing before any output is generated, and reach a person.
4. The affected person can reach a human at every step and is told the content is AI-generated.
5. Sampled assurance runs on live outputs, with a threshold that suspends the affected response categories.
6. Gate 2 is satisfied for the affected population, including a complaints route.

If any condition cannot be met, a person must release each output (Advise, with the reviewer as the control point) or the use case is Restricted. The university worked example applies this variant.

---

## Tier assessment: what to consider

These factors are inputs to the assessment. The first three decide which mechanism is exercisable and whether the gates pass. The remainder decide whether that mechanism is adequate and how strong the supporting controls must be. None of them, on its own, sets the tier.

**Where the output meets the world (practice 6)**
- Does the output stay in the user's own work, inform a decision about someone else, or prepare an action on an external system or person?
- Who is the person who sees each output before it has effect, and are they inside the organisation?

**Accountability and competence (Gate 1)**
- Which role is accountable for the review, decision or authorisation the output feeds?
- Does that role have the competence to check the output and the time to do so at volume?
- Are deputies available in the time window the workflow requires?

**Affected people and impacts (Gate 2)**
- Who is affected, including people not present in the process?
- Are any affected people children or otherwise vulnerable?
- Can affected people raise a concern, have an error corrected and seek redress?

**Data and authority**
- Is the data within the approved purpose and authority?
- Are health, financial, biometric, children's, criminal-record or immigration data present?

**Evidence and uncertainty**
- How reliable is the output for this task, and is its basis visible and checkable?
- What happens on conflicting, missing or out-of-distribution input?
- Is there a comparable precedent for this situation? Where there is none, the absence of a matching stop rule is not permission to proceed: the case routes to a person. See stop-rule category 13, "No comparable case", in [04-stop-rules/stop-rules.md](../04-stop-rules/stop-rules.md).

**Consequence and reach**
- How severe is the worst plausible harm from an undetected error, and who bears it?
- Does the output affect rights, eligibility, money, safety, reputation or access to services?
- How many people or records can be affected before an error is noticed?

**Reversibility and recovery**
- Can an incorrect output be caught before it causes harm, and by whom?
- If it reaches a person or system, how quickly and at what cost can it be corrected?

**Legal and regulatory context**
- Do sector-specific obligations impose higher standards?
- Does the use case fall under a mandatory impact assessment, such as the DTA Policy for the responsible use of AI in government (effective December 2025) for in-scope Commonwealth agencies?

**Governance capacity**
- Can the organisation actually provide the roles, processes, tools and time that the mechanism requires? If not, the answer is Restricted, not a lower standard.

---

## Mandatory escalation triggers

The following conditions require escalation to a named accountable person, whatever tier has been assigned. A use case that regularly hits these triggers should be reassessed.

1. Credible risk to life or physical safety.
2. A legal commitment or material financial movement.
3. A determination or denial that affects rights, eligibility, employment, insurance coverage, education progression, or access to essential or public services.
4. Suspected fraud or criminal allegation.
5. Use involving children or other vulnerable people.
6. Sensitive personal data outside the approved purpose.
7. A security incident, prompt injection or data leakage.
8. Discriminatory or systematically disparate outcomes across a relevant population group.
9. Inability to explain or substantiate a consequential output when asked.
10. Material drift in model behaviour, output quality or population beyond established monitoring thresholds.
11. A control failure: a gate bypassed, a stop rule not triggered when it should have been, or a monitoring gap.
12. A novel use outside the assessed scope.
13. A conflict between applicable policy and the requested action.
14. No competent, available accountable human can be reached within the required timeframe.
15. A complaint or appeal about the AI-assisted output or process.

---

## Related work

The tiered approach in this guide builds on **Paweł Huryn, "The Intent Engineering Framework for AI Agents,"** *Product Compass*, 13 January 2026. Huryn's framework sets out a hierarchy of decision types and autonomy levels for AI agents, ordered by blast radius and reversibility, and introduces stop rules and health metrics as governance concepts. The idea of grading AI decision authority in tiers comes from that work.

What this guide adds is the Australian regulatory grounding (Australia's Guidance for AI Adoption and its six essential practices), the use of practice 6 as the organising axis and practices 1 and 2 as entry gates, the mapping of every practice and NIST AI RMF function to each tier, the decision-rights question bank, the oversight patterns, the stop-rule categories and the worked examples. Huryn's level names and his seven-part specification are not used here.

**Australia's Guidance for AI Adoption** (National AI Centre, October 2025; implementation guidance May 2026): https://www.ai.gov.au/staying-safe-and-responsible/essential-ai-practices/guidance-ai-adoption-implementation-guidance

**NIST AI Risk Management Framework (AI RMF 1.0):** https://www.nist.gov/itl/ai-risk-management-framework

See [REFERENCES.md](../REFERENCES.md) for the full source register.

---

*This model does not constitute legal advice, certification, or a substitute for sector-specific regulatory obligations. See [LIMITATIONS.md](../LIMITATIONS.md).*
