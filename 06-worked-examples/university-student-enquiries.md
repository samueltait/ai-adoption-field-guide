# Worked example: university student enquiries

**Status:** Fictional example for illustrative purposes only.  
**Organisation, people, volumes, and outcomes are invented.** Any resemblance to a real institution is coincidental.

**Provisional tier:** Assist, self-service variant (the student is the per-output reviewer; the organisation controls the source set and the routing).

---

## Organisation and context

**Fictional organisation:** Hartland University, a regional Australian university with approximately 22,000 enrolled students across undergraduate, postgraduate, and research programs. Student enquiries are handled by a central student services hub and by faculty-based student advisers. The hub handles approximately 3,500 enquiries per month via email, web chat, and a walk-in counter.

**Current situation:** Response time for email and chat enquiries averages 2.4 business days during semester, extending to 5+ days during enrolment and results periods. Most enquiries fall into predictable categories: timetabling, enrolment procedures, fee payment, library access, and policy questions about course requirements. A smaller proportion require adviser involvement: academic progression, disability accommodation, fee appeals, visa status, and personal welfare matters.

**Proposed AI capability:** A student-facing AI chat assistant that drafts answers to common enquiries from the university's approved policy and procedure documentation, identifies the enquiry category, and routes complex cases to an appropriate human adviser. For straightforward enquiries, the student sees an AI-drafted response that the student may accept or escalate. For identified complex cases, the student is routed to a human adviser without an AI draft being provided.

---

## Inputs and proposed AI role

**Input:** Student's enquiry text, submitted through the university's authenticated web chat (the student is logged in; their student ID is available to the system but not passed to the AI model prompt).

**Proposed AI role, two tracks:**

**Track A (Assist, self-service variant):** For enquiries the system categorises as routine (timetabling, library access, fee due dates, campus facilities), the system drafts an answer sourced from approved documentation and presents it to the student. The student may accept the answer, ask a follow-up, or request a human adviser at any time. The system does not take any action on the student's behalf: it does not enrol them, change their details, or submit any form.

**Track B (Route to adviser):** For enquiries the system categorises as sensitive, complex, or outside the approved scope (see the list below), the system does not produce a draft answer. It acknowledges receipt and routes the enquiry to the appropriate adviser queue, with the enquiry text and category flag provided to the adviser.

**What the AI does not do:**
- Make any decision about enrolment, results, academic standing, accommodation, fees, appeals, or visa status.
- Send any communication on behalf of the university that commits to a policy outcome.
- Access or modify the student management system.
- Access the student's full record, results, or personal details beyond what the student has provided in the current chat.

---

## Entry gates

**Gate 1, Decide who is accountable:** The student services director owns the use case. A named documentation owner in student services approves and maintains the source set from which every Track A answer is drawn. The student services team leader deputises and runs sampled assurance. Advisers are accountable for Track B responses. Gate passes.

**Gate 2, Understand impacts and plan accordingly:** The affected people are enrolled students, including international students and students with disability, both with specific rights and entitlements. Students can reach an adviser at any step, and can complain through the university's complaints process. The disability services lead and the privacy officer were consulted before deployment. Gate passes.

---

## Why this is the self-service variant, and how each condition is met

The person who sees each Track A answer is the student it concerns, outside the organisation. The university cannot review each answer before the student sees it, so ordinary Assist does not apply. The self-service variant in the risk tier model is permitted only when all six conditions hold:

| Condition | How it is met |
|---|---|
| 1. Output is informational and creates no commitment | Track A answers state what the approved documentation says. The system takes no action and makes no determination. |
| 2. Every answer is drawn from an approved source set with a named owner | The documentation owner approves and maintains the source set; the system cannot answer from anything else. |
| 3. Matters affecting rights, eligibility, money, safety or access are excluded by routing before generation | The always-Track-B list below is applied before any answer is generated; those enquiries reach an adviser. |
| 4. A human is reachable at every step and AI-generated content is disclosed | The chat shows an "ask an adviser" option on every turn and labels each answer as AI-generated. |
| 5. Sampled assurance runs on live outputs with a suspension threshold | 100 Track A interactions per month are reviewed; above 3% inaccurate, the affected categories are suspended (stop rule 5). |
| 6. Gate 2 satisfied for the affected population | See Entry gates. |

If any condition ceased to hold (for example, the source set lost its owner, or the routing list stopped being applied before generation), Track A would have to be released by a person (Advise) or suspended.

---

## Tier factors

| Factor | Assessment |
|---|---|
| Where the output meets the world | Track A: directly with the student it concerns (self-service). Track B: with an adviser, who sees the routed enquiry and category flag and can re-route it. |
| Accountability and competence | Track A: the documentation owner is accountable for the source set; the student services unit for the answers drawn from it. Track B: the adviser. |
| Affected people and impacts | Enrolled students, including international students and students with disability. |
| Data and authority | Enquiry text may reveal personal health, financial, or welfare information. Student ID is available but not passed to the AI model. No sensitive data is used to generate the AI response. |
| Evidence and uncertainty | Every Track A answer cites the approved document it is drawn from, so the student can check it. |
| Consequence and reach | Routine enquiries: low. An incorrect timetabling answer or a misquoted fee due date causes inconvenience. Complex matters: high. Incorrect information about academic progression, visa status, disability accommodation, or fee appeals can harm the student's enrolment, financial position, or welfare. These must not be answered by the AI. |
| Reversibility and recovery | Routine: reversible; the student can verify, re-ask, or escalate. Complex: potentially irreversible if acted on by the student without adviser review, which is why they are excluded by routing. |
| Legal and regulatory context | Disability accommodation involves the student's rights under the Disability Discrimination Act 1992. International students' obligations arise under the Education Services for Overseas Students Act 2000. |
| Governance capacity | The hub already maintains approved documentation and handles complaints; adding the source-set owner role and monthly sampling is within its capacity. |

---

## Provisional tiers

**Track A: Assist, self-service variant.** Routine factual enquiries, answered from the approved source set, with the student in control of whether to accept the answer or escalate.

**Track B: Route to adviser.** Complex, sensitive, or out-of-scope matters receive no AI draft answer. The routing function itself is Assist (the adviser sees the routed enquiry and the category flag before acting and can re-route it); the adviser interaction that follows is governed by the university's existing adviser practices, not this guide.

---

## Matters that must always route to an adviser (never answered by the AI)

The following are always Track B, regardless of how the enquiry is phrased:

- Admission, re-admission, or enrolment status.
- Academic progression decisions: satisfactory academic progress, academic standing, exclusion, leave of absence, withdrawal.
- Fees, fee liability, refunds, or scholarship eligibility.
- Disability accommodation: requests, renewals, disputes.
- Safeguarding or personal welfare concerns: any indication of distress, safety risk, mental health crisis, or harm to the student or another person.
- Visa status and international student obligations.
- Complaints about staff, assessors, or the university's processes.
- Appeals against any university decision.
- Requests for the university to take an action on the student's behalf.

**Rationale for each:**

*Enrolment and progression:* These are formal determinations with financial and legal consequences. An AI draft answer risks providing incorrect information about a student's specific situation, which the student may rely on to their detriment.

*Fees and scholarships:* Fee liability is a contractual and regulatory matter. Incorrect information could lead a student to miss a payment, forfeit a scholarship, or make a financial decision based on an incorrect understanding.

*Disability accommodation:* Accommodation decisions involve the student's legal rights and the university's obligations. They require a qualified adviser and an individualised assessment.

*Safeguarding and welfare:* Any indication that a student is in distress, at risk, or experiencing harm must reach a human immediately. An AI chat assistant must not attempt to manage a welfare matter.

*Visa and international obligations:* International students' visa obligations are complex and highly individual. Incorrect advice could affect a student's visa status.

---

## Decision owners

| Role | Responsibility |
|---|---|
| Student services director | Service owner; accountable for the overall quality and equity of the student enquiry service. |
| Documentation owner (student services) | Approves and maintains the source set from which Track A answers are drawn; removes or corrects sources on error. |
| Student services team leader | Day-to-day oversight; runs sampled assurance; monitors escalation rates; reviews adoption measures. |
| Student adviser (specialist) | Handles all Track B enquiries; is the accountable person for adviser responses. |
| ICT/digital team | Technical operation, documentation management system, access controls. |
| Privacy officer | Consulted before deployment; reviews any privacy event. |
| Disability services lead | Consulted before deployment; confirms Track B routing for disability matters is correct. |

---

## Oversight patterns

**Workspace assistant, self-service form (Track A):** The student reviews every AI-drafted response before acting on it, can see the source it was drawn from, and can escalate to an adviser at any point. The system takes no action without the student's explicit acceptance and further action by the student.

**Sampled assurance (mandatory for the self-service variant):** A risk-based sample of 100 Track A interactions per month is reviewed by the team leader for accuracy against the approved documentation. Inaccurate responses are removed from the approved response set. An error rate above 3% suspends the affected response categories (stop rule 5).

**Shadow mode (pre-deployment):** See "Promotion and review decision" below.

---

## Stop rules

| # | Trigger | Detection | Immediate action | Escalation owner | Evidence to preserve | Recovery authority | Notification duty |
|---|---|---|---|---|---|---|---|
| 1 | The enquiry text contains language indicating distress, self-harm, or a safety concern. | Automated keyword detection. | Immediately route to the student welfare team; do not produce an AI response. Display a welfare support message to the student with emergency contact details. | Student welfare team. | Full enquiry text, timestamp. | Student welfare officer determines follow-up. | Student welfare lead and student services director notified. |
| 2 | The enquiry text references a matter that is always Track B (see list above) but the categorisation system proposes a Track A response. | Automated category check before response is generated; or adviser review of the routing log. | Suppress the Track A response; route to adviser. | Team leader. | Enquiry text, proposed category, override event. | Team leader re-reviews the category mapping and updates if necessary. | Team leader notifies ICT/digital of misclassification. |
| 3 | The approved documentation source for a Track A response is unavailable, out of date, or in conflict with another approved source. | Documentation management system check at response generation. | Do not produce a Track A response; route to adviser. | Documentation owner; team leader. | Enquiry text, documentation error, timestamp. | Documentation owner confirms correct documentation and restores Track A capability. | None unless a pattern indicates a documentation management failure. |
| 4 | A student reports that an AI-drafted response was incorrect and they acted on it to their detriment. | Student complaint through the university's complaints process. | Record the complaint; escalate to the student services director. Suspend the relevant response category pending review. | Student services director. | Full interaction record, AI response, documentation source used, student outcome. | Director reviews; documentation owner corrects or removes the source. | Student acknowledged per complaints policy; registrar notified if the student's record is affected. |
| 5 | Track A accuracy rate in the monthly sample falls below 97% (more than 3% inaccurate responses). | Monthly sampled assurance review. | Team leader suspends the affected response categories pending review. | Team leader; student services director. | Sampled records, error log. | Director approves reinstatement after documentation is corrected. | Director and ICT/digital informed. |
| 6 | No comparable case (category 13): the enquiry does not match any Track A category or any always-Track-B category, or matches an approved source and a conflicting approved source with nothing to decide between them. | Automated category-match check returning "no match", or source-conflict check returning "unresolved". | No Track A answer; acknowledge receipt and route to the adviser queue flagged "no comparable case". | Student services team leader. | Enquiry text, check result, adviser's handling. | Student services director, under change control: add a category or source, confirm the enquiry type as adviser-only, or reassess the tier. | Director told of every activation; a recurring pattern is treated as a scope gap and reviewed with ICT/digital. |

---

## Adoption and benefit measures

| Measure | Baseline | Target | Source | Cadence |
|---|---|---|---|---|
| Email/chat response time | 2.4 business days | ≤4 hours for Track A | Workflow timestamps | Monthly |
| Track A resolution rate (student accepts AI response) | N/A (new) | Monitor; do not set target before 90-day review | Interaction logs | Monthly |
| Escalation rate from Track A to adviser | N/A (new) | Monitor; high escalation indicates scope or quality issue | Escalation logs | Monthly |
| Misclassification rate (Track B sent to Track A) | N/A | Zero misclassifications into Track A for always-human categories | Routing review | Monthly |
| Track A accuracy rate (sampled) | N/A | ≥97% per month | Sampled assurance records | Monthly |
| Student satisfaction, response quality | Pre-deployment survey | Post-deployment survey at 90 days | Survey | 90 days, then annually |
| Adviser capacity released | Baseline volume of routine enquiries handled by advisers | Measurable reduction enabling adviser redeployment to complex cases | Workflow records | Quarterly |
| Safeguarding escalation response time | Baseline from welfare team records | No increase | Welfare team records | Monthly |

---

## Promotion and review decision

**Shadow mode:** Before live deployment, AI responses are generated but not shown to students. Advisers review AI-generated responses for a sample of 500 enquiries against the responses they would have given. Agreement rate, accuracy, and misclassification events are reviewed. If agreement rate ≥95%, zero misclassification into always-human categories, and no safeguarding misclassification, promote to live Track A operation.

**First post-deployment review:** 90 days from go-live. Team leader and student services director review adoption measures, accuracy, escalation rates, complaints, and whether all six self-service conditions still hold. Decision: continue, adjust scope, or reassess the tier.

**Annual review:** Full reassessment including a review of the approved documentation set, disability and international student obligations, and any changes to university policy that affect the response categories.
