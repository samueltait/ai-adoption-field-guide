# Worked example: local council service request triage

**Status:** Fictional example for illustrative purposes only.  
**Organisation, people, volumes, and outcomes are invented.** Any resemblance to a real organisation is coincidental.

**Provisional tier:** Advise (per-decision record).

---

## Organisation and context

**Fictional organisation:** Riverbend City Council, a mid-size local government authority serving a mixed urban and peri-urban area of approximately 180,000 residents. The council receives service requests through a web form, a phone line, and a counter walk-in service across several categories: waste, roads and footpaths, parks and open space, animal management, development queries, and general enquiries.

**Current situation:** The customer service team receives approximately 1,400 inbound service requests per week. First-contact routing is manual; a team of eight officers review each request and assign it to the relevant service unit. Average routing time is 18 minutes per request. A backlog of approximately 400 unrouted requests accumulates on peak days (post-long weekend, post-storm events). Some service requests are misrouted on first contact, requiring re-routing and adding an average of 2.3 days to resolution.

**Proposed AI capability:** A natural-language triage system that reads the text of an inbound service request, identifies the service category, suggests a routing destination, and flags requests that require urgent attention or human review before routing.

---

## Inputs and proposed AI role

**Input:** The text submitted by the resident in the service request form (free text, up to 1,000 characters). No structured fields are required; residents describe their issue in their own words.

**Proposed AI role:** The system reads the request text, assigns a suggested category and routing destination from an approved list, and produces a draft routing recommendation for the customer service officer's review. For requests flagged as urgent or out-of-scope, it surfaces a reason for human review rather than a routing suggestion.

**What the AI does not do:**
- Send any communication to the resident.
- Commit the council to any action, timeline, or service level.
- Access or modify records in the council's service management system.
- Make a final routing decision. The officer decides, and the decision is recorded in the service management system.

---

## Entry gates

**Gate 1, Decide who is accountable:** The customer service officer role holds the routing decision; the customer service team leader is the deputy and the first escalation point; the service delivery manager owns the use case. Officers are trained to check suggestions rather than accept them. Provider terms for the triage system are held by the ICT/digital team. Gate passes.

**Gate 2, Understand impacts and plan accordingly:** The affected people are residents, including people under stress, people with limited English and people who cannot use the web form well. Residents can raise a concern through the council's existing complaints process, and misrouting is visible in re-routing records. Gate passes, with accessibility conditions carried into the stop rules.

---

## Tier factors

| Factor | Assessment |
|---|---|
| Where the output meets the world | The suggestion informs an officer's decision about a resident's request. It does not stay in the officer's own work: it determines which service unit responds to a member of the public. The control point is therefore the officer's recorded decision, not simply their review of the text. |
| Accountability and competence | Each officer is accountable for the routing decision they record; the team leader deputises. Officers already make this decision manually and have the domain knowledge to check the suggestion. |
| Affected people and impacts | Residents of the council area. No special vulnerability is assumed for the general population, but accessibility considerations apply (see stop rules). |
| Data and authority | Request text may contain personal information about the resident or a third party. No health, financial, or identity document data is required. |
| Evidence and uncertainty | The AI output is visible and checkable by the officer. For requests the system cannot match to an approved category, it surfaces a "needs review" flag rather than a guess. |
| Consequence and reach | Routing an ordinary request to the wrong unit causes delay, not harm. Misrouting an urgent safety-related request (downed power line, road hazard, animal attack) could delay an emergency response. One error affects one resident. |
| Reversibility and recovery | Misrouting is detectable and correctable; the officer decides before submission and re-routing is possible afterwards. |
| Legal and regulatory context | Service request routing is not a statutory determination. The council has obligations under its accessibility and equal service delivery policies. State policy on AI in local government may apply and should be checked. |
| Governance capacity | The team already records routing decisions and reviews complaints; adding override monitoring and a sampled review is within its capacity. |

---

## Provisional tier

**Advise (per-decision record).**

**Rationale:** The output informs a decision about someone other than the user, so per-output review alone is not the control. The officer must make and record the routing decision, with the suggestion and any override captured, and residents must have a redress route. All of that is already exercisable. Per-action gating is not needed because the AI prepares no action: it never writes to the service management system or contacts the resident. The urgent and sensitive flags must work reliably for Advise to hold; if they cannot, the affected categories are Restricted (see below).

---

## Decision owners

| Role | Responsibility |
|---|---|
| Customer service officer | Makes and records each routing decision; may accept, change or reject the AI suggestion. This is the accountability act for each decision. |
| Customer service team leader | Deputy for the officer role; monitors override rates and unusual patterns; first escalation point for out-of-scope requests. |
| Service delivery manager | Owns the use case; accountable for the quality and equity of the routing function; reviews adoption and quality measures. |
| ICT/digital team | Accountable for the system's technical operation, data handling, and any integration with the council's service management system. |
| Privacy officer | Consulted before deployment on data handling; reviews any privacy event. |

---

## Oversight patterns

**Second-reader review:** The officer reviews the AI suggestion and the request text, then records the routing decision in the service management system. The record captures the suggestion, the decision and, where they differ, the reason. See [03-oversight-patterns/oversight-patterns.md](../03-oversight-patterns/oversight-patterns.md).

**Sampled assurance:** A risk-based sample of 50 completed routings per week is reviewed by the team leader to assess the quality of both AI suggestions and officer decisions. Error rate above 5% in the sampled set triggers a broader review.

**Shadow mode (pre-deployment):** See "Promotion and review decision" below.

---

## Stop rules

| # | Trigger | Detection | Immediate action | Escalation owner | Evidence to preserve | Recovery authority | Notification duty |
|---|---|---|---|---|---|---|---|
| 1 | The request text contains indicators of an emergency or immediate safety risk (explicit safety keywords, mention of injury, or a hazard posing risk of harm). | Automated keyword detection in the triage system. | Surface to officer immediately as "URGENT: safety review required". Do not assign a routine routing suggestion. | Team leader / emergency response protocol. | Full request text, timestamp, detected keywords. | Team leader confirms routing to the relevant emergency or safety team. | Team leader notifies service delivery manager of any emergency request received. |
| 2 | The request text appears to reference a child at risk or a domestic violence situation. | Automated detection of relevant categories. | Flag as "SENSITIVE: human review required". Do not assign a routine routing. | Team leader; council's safeguarding or social services contact. | Full request text, timestamp. | Team leader determines routing after review; may involve external referral. | Social services or safeguarding lead notified per council policy. |
| 3 | No category on the approved list matches the request text; or the text is under 20 characters; or language detection returns a language other than English. | Automated category-match, length and language checks before a suggestion is produced. | Surface to officer as "NEEDS REVIEW: no matching category" with no routing suggestion. | Officer; escalated to team leader if still unresolvable. | Request text, check results. | Officer routes manually after review. | None routine; team leader notified if a pattern of unmatched or non-English requests emerges (accessibility signal). |
| 4 | The officer override rate for the week exceeds 20% of reviewed suggestions. | Team leader's weekly sampled assurance review. | Team leader reviews the sample for systematic cause. | Service delivery manager. | Override records for the affected period, categorised by reason. | Service delivery manager determines whether the system should be paused pending investigation. | Service delivery manager informs ICT/digital. |
| 5 | A resident complains that their request was misrouted and a service delay caused harm. | Complaint received through the council's complaints process. | Record the complaint; review the request routing record. | Customer service team leader; complaints function. | Full routing record, AI suggestion, officer decision, timestamps. | Complaints function resolves; service delivery manager reviews for systemic cause. | Resident acknowledged per complaints policy. |
| 6 | No comparable case (category 13): the request combines factors not seen in shadow mode or the sampled review (for example, a request that matches two categories with different service units and no rule decides between them), or the officer flags "I have not seen this before". | Automated two-category conflict check returning "unresolved"; officer flag in the triage interface. | No routing suggestion; surface "NO COMPARABLE CASE" and hold for the officer's manual decision. | Team leader. | Request text, categories in conflict, officer's decision. | Service delivery manager, under change control: add a category or rule, confirm the case type as manual, or reassess the tier. | Service delivery manager told of every activation; risk function told if the same pattern recurs. |

---

## Why automated service denial is Restricted

Several request types could in principle be handled by an AI system without officer involvement: routine acknowledgements, FAQ responses, or form validation. However, any automated response that *determines* what service a resident will receive, or declines to route a request without human review, is not Advise. It is Restricted for this use case.

**Automated service denial is Restricted because:**
- No human-control mechanism is exercisable. A resident who receives no routing, or a denial, from an automated system has had a service-access decision made about them with no person making or recording it and no gate holding it.
- Gate 2 fails for the people most affected. The council's accessibility obligation means residents who cannot navigate a web form, who are under stress, or whose English is limited must not be turned away because their request does not parse cleanly.
- Routing determines whether a resident's concern receives a council response. That is a service-access decision, not a formatting task.

Any proposed use case that involves the system making a final routing decision without an officer, automatically declining to route a request, or sending an automated message to the resident that commits the council to a response (or the absence of one) must be reassessed before any operational use.

---

## Adoption and benefit measures

| Measure | Baseline | Target | Source | Cadence |
|---|---|---|---|---|
| Routing time per request | 18 min (manual) | ≤10 min (AI-assisted) | Workflow timestamps | Monthly |
| Misrouting rate | Measured from re-routing records pre-deployment | ≤50% of baseline | Re-routing records | Monthly |
| Override rate | N/A (new) | Monitor; flag if >20% | Decision records | Weekly (team leader) |
| Unrouted backlog at end of peak days | ~400 requests | ≤100 | Service management system | Monthly |
| Complaints about misrouting or service delay | Baseline from prior period | No increase | Complaints log | Quarterly |
| Non-English and unmatched requests reaching an officer | Baseline from prior period | No decrease (a fall would suggest requests are being lost) | Stop rule 3 log | Monthly |
| Officer experience | Pre-deployment survey | Post-deployment survey at 90 days | Survey | At 90 days |

---

## Promotion and review decision

The capability should enter shadow mode before live operation: AI-generated routing suggestions are produced but not shown to officers; the ICT team compares AI suggestions to officer decisions over two weeks and reviews agreement rate, error categories, and urgent-flag accuracy. If the agreement rate is ≥85% and no emergency misclassification occurs in shadow mode, the capability is promoted to live Advise operation.

**First post-deployment review:** 90 days from go-live. Service delivery manager reviews adoption measures, override rate, complaint data, and any stop-rule activations. Decision: continue, adjust, or reassess the tier.

**Annual review:** The capability is reassessed annually and whenever a material change occurs to the routing categories, the system, the data, or the volume.
