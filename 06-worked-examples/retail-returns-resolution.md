# Worked example: retail returns and customer resolution

**Status:** Fictional example for illustrative purposes only.  
**Organisation, people, volumes, and outcomes are invented.** Any resemblance to a real organisation is coincidental.

**Provisional tiers:** Assist (Track A), Advise (Track B) and Act with approval (Track C).

---

## Organisation and context

**Fictional organisation:** Northfield Home & Garden, a mid-size Australian omnichannel retailer operating 42 stores and an e-commerce platform, selling homewares, garden equipment, and power tools. Annual revenue is approximately A$320M. The customer service team handles approximately 8,400 contacts per month across returns, product faults, delivery disputes, and general enquiries.

**Current situation:** Returns and customer resolution contacts are handled by a team of 26 customer service agents across a contact centre and in-store service desks. Average handling time for a phone or chat contact is 11 minutes. A significant proportion of contacts are resolved by applying standard return policy rules that agents look up manually. High-value or complex cases (disputed faults, freight damage claims, commercial customer refunds above A$500, and escalated complaints) are handled by six specialist resolution agents.

**Proposed AI capability:** An AI-assisted contact centre tool that reads the customer's contact reason and relevant order and return history (retrieved from the order management system for the authenticated customer), applies the retailer's return and resolution policy, drafts a suggested resolution for the agent's review, and, for standard resolutions within defined parameters, prepares a resolution record for agent confirmation before it is applied to the order management system.

---

## Inputs and proposed AI role

**Input:** Customer's contact reason (text entered by the agent or transcribed from call), plus structured data retrieved from the order management system: order number, product, purchase date, purchase channel, current status, and prior contact history for the same order.

**Proposed AI role, three tracks:**

**Track A (Assist: policy lookup):** For contacts where the customer's question is answered by a direct policy lookup (e.g. "what is your returns period?", "how do I exchange an item?"), the AI surfaces the relevant policy clause for the agent's use. The agent responds to the customer.

**Track B (Advise: draft resolution):** For contacts where a resolution is likely within the standard policy (return within period, product fault within warranty, delivery delay with trackable order), the AI retrieves relevant order data, applies the policy rule, and drafts a suggested resolution for the agent's review. The agent reviews the draft, may modify it, confirms or overrides, and the agent applies the resolution. The AI does not write to the order management system.

**Track C (Act with approval: standard resolution execution):** For standard resolutions within defined parameters (refund or store credit ≤A$100, exchange of an in-stock item, standard return label generation), the AI prepares the resolution transaction. Execution is blocked until the agent explicitly confirms the prepared action in the case management interface. The agent may modify, override, or escalate before confirming.

**What the AI does not do:**
- Issue a refund, generate a return label, or update the order management system without agent confirmation.
- Handle contacts that fall into the specialist escalation categories (see below).
- Access financial account details beyond what is already visible in the agent's standard order view.
- Commit the company to compensation, goodwill payments, or non-standard resolutions.

---

## Entry gates

**Gate 1, Decide who is accountable:** The contact centre manager owns the use case. For Track C, the contact centre agent role holds a documented delegated authority to approve refunds and store credits up to A$100 and in-stock exchanges; the team leader is the documented deputy; anything above the threshold belongs to the specialist resolution team. Provider responsibilities for the order management integration are documented by ICT operations. Gate passes.

**Gate 2, Understand impacts and plan accordingly:** The affected people are retail customers. A customer can dispute any resolution through the existing contact channels, and a disputed Track C transaction is reversible (stop rule 5). Legal/compliance was consulted on consumer guarantee obligations. Gate passes.

---

## Tier factors

| Factor | Assessment |
|---|---|
| Where the output meets the world | Track A: stays in the agent's own work. Track B: informs the agent's decision about the customer's resolution. Track C: a prepared transaction on the order management system, released only through the agent's confirmation. |
| Accountability and competence | The agent role is accountable for each Track B decision and each Track C confirmation within its delegated authority; the specialist team above the thresholds. |
| Affected people and impacts | Retail customers. Business and trade customers are excluded to the specialist team. |
| Data and authority | Order history, contact history, customer name, delivery address. No health, biometric, or financial account data beyond what is visible in the agent's existing system. |
| Evidence and uncertainty | The draft (Track B) and the prepared transaction (Track C) show the order data and the policy rule applied, so the agent can check them. |
| Consequence and reach | Track A: very low. Track B: low to moderate; a wrong resolution if the agent does not review carefully. Track C: moderate; a refund or exchange has a financial consequence for the business and the customer. One error affects one customer and one order. |
| Reversibility and recovery | Tracks A and B: high; the agent decides before any action. Track C: moderate; the refund or exchange can be reversed, but at cost and with potential customer-experience impact. |
| Legal and regulatory context | Consumer guarantees under the Australian Consumer Law apply. The AI must not be used to deny a consumer guarantee to which the customer is legally entitled. |
| Governance capacity | The order management system already records agent identity and actions; a parameter check, a confirmation step and daily reconciliation are within the operations and finance teams' capacity. |

---

## Provisional tiers

**Track A: Assist (per-output review).** Policy lookup to aid the agent.  
**Track B: Advise (per-decision record).** Draft resolution for agent review and decision, recorded in the case management system.  
**Track C: Act with approval (per-action gate).** Standard resolution prepared by AI, executed only after the agent confirms the specific transaction within the delegated parameters.

**Entry evidence for Track C (required by the model before an Act with approval use case may operate):**
- Delegated authority instrument for the agent role (≤A$100 refunds and credits; in-stock exchanges), with the team leader as deputy.
- Provider and integration responsibilities documented by ICT operations, including failure handling (stop rule 6).
- AI register entry recording the use case, the parameter check, the confirmation gate and the approver role.
- Approval gate and rollback (transaction reversal) tested in pre-production.
- Daily reconciliation by operations/finance, independent of the contact centre.
- Documented pause procedure: the contact centre manager can suspend Track C without ICT involvement.
- Audit log in the order management system: agent identity, timestamp, action confirmed.

---

## Cases that must always go to the specialist team (not AI-assisted)

The following contacts must be handled by a specialist resolution agent, regardless of how they present:

- Refund or store credit requests above A$500.
- Commercial customer claims (business accounts, trade customers).
- Product liability claims: any claim that a product caused injury or property damage.
- Fraud allegations: any suspicion of fraudulent return or contact.
- Escalated complaints: contacts where the customer has previously escalated or has requested to speak with a manager.
- Consumer guarantee disputes: where the customer disputes the company's response and invokes consumer guarantee rights explicitly.
- Insurance-related claims.
- Contacts where the customer indicates legal action.

**Rationale:** These cases involve financial consequence above the agent's authority, legal rights and obligations under consumer law, or reputational risk that requires specialist judgment and cannot be safely delegated to an AI-assisted standard workflow.

---

## Decision owners

| Role | Responsibility |
|---|---|
| Contact centre manager | Service owner; accountable for the overall performance and quality of the contact centre; reviews adoption and quality measures; can suspend any track. |
| Team leader (contact centre) | Day-to-day oversight; deputy for the agent role's delegated authority; monitors override rates and escalation patterns; first escalation for anomalies. |
| Agent (contact centre) | Reviews and confirms or overrides every AI draft (Track B) and every prepared action (Track C). Confirmation is the accountability act, within the delegated authority. |
| Specialist resolution team | Handles all cases above the defined thresholds and all escalated contacts. |
| Operations/finance | Reviews Track C transaction volumes and financial accuracy; daily reconciliation, independent of the contact centre. |
| ICT operations | Integration with the order management system; documents provider responsibilities; resolves integration faults. |
| Legal/compliance | Consulted before deployment on consumer guarantee obligations; reviews any consumer law escalation. |

---

## Oversight patterns

**Track A: Workspace assistant.** The agent sees the policy clause and uses it to respond. No further oversight required for routine lookups.

**Track B: Second-reader review.** The agent reviews the draft resolution, the order data it drew on, and the policy rule applied. The agent confirms or overrides before any action is taken. Override reason is recorded in the case management system.

**Track C: Approval gate, with Constrained execution and Independent monitoring.**
- *Approval gate:* the prepared transaction is displayed to the agent before execution. The agent confirms (or overrides) each transaction individually. Bulk confirmation is not permitted. The order management system records the agent identity, timestamp, and action confirmed.
- *Constrained execution:* the AI can only prepare transactions within the parameters (≤A$100 refund or credit; in-stock exchange; standard return label). Anything outside them is never presented for confirmation (stop rule 2).
- *Independent monitoring:* a daily reconciliation by the operations/finance team reviews all Track C transactions for anomalies, outside the contact centre's reporting line.

---

## Stop rules

| # | Trigger | Detection | Immediate action | Escalation owner | Evidence to preserve | Recovery authority | Notification duty |
|---|---|---|---|---|---|---|---|
| 1 | The customer contact or order history indicates a product liability claim (injury or property damage). | Agent flags "product liability" in the case system, or AI categorises as liability claim. | Do not produce a draft resolution; route immediately to the specialist team. | Specialist team lead. | Full contact record, order history, customer-stated injury details. | Specialist team lead confirms routing and initiates the liability process. | Legal/compliance notified per the product liability protocol. |
| 2 | The AI-prepared Track C refund amount exceeds A$100 or the exchange product is not in stock at the confirmed location. | Automated parameter check before presenting the prepared action to the agent. | Do not present the action for agent confirmation; surface "Exceeds standard parameters: escalate to specialist". | Team leader. | Prepared action details, parameter check result. | Team leader confirms escalation to specialist. | None routine. |
| 3 | The customer uses language indicating they are pursuing legal action or have lodged a formal complaint. | Automated keyword detection in the contact text; agent may also flag. | Do not produce a draft resolution; route to specialist team. | Specialist team lead. | Full contact record, flagged language. | Specialist team lead handles the contact. | Legal/compliance notified. |
| 4 | The agent override rate for Track B drafts in the current week exceeds 30%. | Team leader's weekly monitoring review. | Team leader reviews a sample of overrides to identify the cause. | Contact centre manager. | Override records, override reasons for the affected period. | Contact centre manager determines whether Track B should be paused pending a policy-data review. | Contact centre manager informs operations. |
| 5 | A Track C transaction is disputed by a customer as incorrectly applied (wrong amount, wrong product, wrong account). | Customer complaint or inbound contact about a prior resolution. | Record the dispute; flag the transaction for specialist review; do not apply further AI-assisted resolutions to this customer's account pending review. | Specialist team lead. | Original transaction record, agent confirmation log, dispute details. | Specialist team resolves the dispute; operations/finance reviews the transaction log. | Customer acknowledged; operations notified for reconciliation. |
| 6 | The order management system API returns an error during a Track C prepared action. | Automated error detection in the integration layer. | Do not execute the prepared action; display error to agent; route to manual handling. | ICT operations. | Error log, prepared action details, timestamp. | ICT operations resolves the integration fault; contact centre manager approves resumption. | Contact centre manager informed of any extended outage. |
| 7 | No comparable case (category 13): the contact and order history do not match any standard resolution rule, or two policy rules apply with different outcomes and nothing decides between them (for example, a faulty item bought in a bundle promotion that is partly returned). | Automated rule-match check returning "no match" or "unresolved"; agent flag "not seen this before". | No draft (Track B) and no prepared action (Track C); route to the specialist team flagged "no comparable case". | Specialist team lead. | Contact record, order data, rules in conflict, specialist's resolution. | Contact centre manager, under change control: add or clarify a policy rule, confirm the case type as specialist-only, or reassess the tier. | Contact centre manager told of every activation; legal/compliance told if the conflict involves consumer guarantee rights. |

---

## Why consumer-guarantee denial is Restricted

An AI-assisted workflow must not be used to deny a consumer guarantee under the Australian Consumer Law. Consumer guarantees are statutory rights; denial requires a substantive assessment of whether the guarantee applies, which involves the product, the fault, the use, and sometimes the customer's circumstances. An AI system applying a pattern-matching policy rule to a consumer guarantee dispute could:

- Deny a valid statutory right based on an incorrect categorisation of the fault.
- Expose the organisation to a consumer law compliance failure.
- Cause financial harm to the customer.

On the tier model's terms, none of the three control mechanisms is adequate here: a frontline agent's confirmation is not a competent assessment of a statutory right, and the consequence of a wrong denial falls on the customer. Any proposed use of AI to generate, confirm, or route a consumer-guarantee denial is Restricted for this use case; if it is ever reassessed, the control point would have to sit with the specialist team as a per-decision record (Advise), not with an agent's gate.

---

## Adoption and benefit measures

| Measure | Baseline | Target | Source | Cadence |
|---|---|---|---|---|
| Average handling time | 11 min | ≤8 min for AI-assisted contacts | Telephony/case management timestamps | Monthly |
| First-contact resolution rate | Baseline from case management records | ≥5pp improvement at 90 days | Case management records | Monthly |
| Agent override rate (Track B) | N/A | Monitor; flag if >30% | Case management records | Weekly (team leader) |
| Track C transaction accuracy | Baseline from reconciliation records | Zero AI-prepared transaction errors above A$10 at reconciliation | Operations/finance reconciliation | Monthly |
| Specialist escalation rate | Baseline from current routing data | No increase; flag if decrease (may indicate under-escalation) | Case management records | Monthly |
| Consumer law complaints | Baseline from complaints records | No increase | Complaints log | Quarterly |
| Product liability flags handled per protocol | 100% (expected) | 100% | Specialist team records | Monthly |
| Agent satisfaction, tool usability | Pre-deployment survey | Post-deployment survey at 90 days | Survey | 90 days, then annually |

---

## Promotion and review decision

**Shadow mode (Track C only):** Before Track C goes live, the AI prepares transactions but agents apply them manually. For two weeks, the operations/finance team compares AI-prepared transactions to manually applied transactions for the same contacts. If the agreement rate is ≥97% and no liability or consumer-law cases are prepared for standard Track C resolution, promote to live Track C operation.

**First post-deployment review:** 90 days from go-live. Contact centre manager and operations/finance review adoption measures, transaction accuracy, override rates, and any consumer-law or liability events. Decision: continue, adjust parameters, or reassess the tier.

**Annual review:** Full reassessment including a review of the consumer law compliance record, any changes to product categories or return policy, and any changes in volume or customer population.
