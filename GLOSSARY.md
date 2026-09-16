# Glossary

**Version:** 2026-09-16
**Author:** Samuel Tait
**Licence:** CC BY 4.0 (see [LICENSE](LICENSE))

Key terms used in this guide. Where a term has a specific meaning in an
external framework (Australian Guidance for AI Adoption, NIST AI RMF), this
glossary describes how the term is used here; it does not reproduce or
replace the source definition.

---

**Accountable person**
A named role (not just a named individual) that has the authority and
competency to make, record, and be answerable for a decision or action that
an AI-assisted workflow contributes to. Accountability cannot be delegated
to the AI system.

**Act with approval (tier)**
The third tier of this guide's risk model: the per-action gate. Each output
is a prepared action on an external system or person, and a formally
accountable role must authorise each action through a technical gate before
it is released. Preparation and execution are separated by design.

**Advise (tier)**
The second tier of this guide's risk model: the per-decision record. The
output informs a decision about a person or matter outside the user's own
work, and a qualified reviewer must make and record that decision, with the
evidence visible and a redress route for the person affected.

**Adoption measure**
A measure that tracks whether eligible users are using the AI-assisted
capability appropriately and sustainably, distinct from measures that track
whether the expected benefits have been realised.

**AI adoption**
Moving a use case from business case through governed implementation,
sustained use, and demonstrated benefits realisation. Not limited to
deploying a model or running a pilot.

**AI register**
A record maintained by an organisation that documents its AI systems and
use cases, including their purpose, scope, accountability, risk tier, and
governance status. Relevant to AI6 practice 4.1 (maintain an AI register).

**Approval gate**
A technical or process mechanism that prevents an AI-prepared action from
being executed until an accountable person has explicitly reviewed and
authorised it. An approval gate cannot be bypassed by bulk approval,
notification-only confirmation, or AI-to-AI authorisation.

**Assist (tier)**
The first tier of this guide's risk model: per-output review. A competent
person inside the organisation sees every output and can change or discard
it before it is used in their own work. See also "Self-service variant".

**Benefits realisation**
Evidence that the intended operational or user outcomes of an AI-assisted
use case have occurred, measured net of harms, control failures, and
adoption costs. Distinguished from usage metrics or efficiency projections.

**Decision rights**
The allocation of authority to make, approve, override, escalate, and retire
decisions in an AI-assisted workflow: who is accountable, who approves, who
operates, who monitors, and who can stop the capability.

Some task-allocation frameworks use the same phrase in a narrower sense, for
final authority alone, as one of three elements allocated separately alongside
initiative (who starts the work) and control (who oversees execution). See
Afroogh, Varshney and D'Cruz (2025) in REFERENCES.md [10]. This guide uses the
broad sense throughout. Where an assessment draws on both, record which sense
is meant.

**Entry gate**
One of the two conditions, drawn from Australia's Guidance for AI Adoption
practices 1 ("Decide who is accountable") and 2 ("Understand impacts and
plan accordingly"), that must pass before any tier can be assigned: a named
role with the authority and competence to exercise the control mechanism,
and identified affected people with a feedback and redress route. A failed
gate sends the use case to Restricted.

**Governance capacity**
An organisation's practical ability to satisfy the required governance
practices for a given tier: the roles, processes, tools, time, and
competency that the oversight and accountability structures require.

**Human approval**
An act by an accountable person who reviews sufficient evidence and
explicitly authorises an action before it changes an external state. Passive
notification, bulk sign-off, or AI-generated authorisation is not human
approval.

**Mandatory escalation trigger**
A condition that requires a case to be routed to a named human accountable
person regardless of the tier provisionally assigned to the use case.
Fifteen categories are defined in the risk tier model; they override any
automated or lower-level handling.

**No comparable case**
The stop state for a situation with no comparable precedent in the assessed
scope: no matching category, an unassessed population or context, or two
applicable rules that conflict with nothing to decide between them. The
absence of a matching stop rule is never read as permission; the case
routes to a person and into the review loop. Stop-rule category 13, adapted
from the "unknown" band in Spencer and Edgelabs, "The Conscience Graph"
(2026); see REFERENCES.md.

**Oversight pattern**
A reusable arrangement of review, monitoring, authority, and escalation
that is appropriate for a given tier and use case. Eight patterns are
described in this guide. Patterns may be combined; they are not
interchangeable.

**Provisional tier**
The tier assigned to a proposed use case at the time of assessment. A
provisional tier is a starting point for governance design, not a permanent
or compliance-equivalent determination. It must be reassessed when the
use case, data, model, scale, or governance capacity changes materially.

**Restricted (tier)**
The fourth tier of this guide's risk model: no exercisable control. The
organisation cannot exercise per-output review, a per-decision record or a
per-action gate for this use case, or an entry gate has failed, or the
mechanism it can exercise is not adequate for the impacts. Restricted is a
governance restriction, not a legal determination.

**Risk tier**
The form of human control the organisation must exercise over an
AI-assisted workflow (per-output review, per-decision record, per-action
gate, or none available), determined by where the output meets the world,
whether the accountability and impact gates pass, and whether that control
is adequate for the consequences.

**Self-service variant**
A form of Assist in which the person who sees each output is the person it
concerns, outside the organisation. Permitted only when the output is
informational, drawn from an approved source set with a named owner,
excludes matters affecting rights by routing before generation, offers a
human at every step, is disclosed as AI-generated, and is covered by
sampled assurance.

**Shadow mode**
An oversight pattern in which the AI system runs and produces outputs but
does not affect real outcomes. Shadow mode results are compared to the
current process before the capability is promoted to live operation.

**Stop rule**
A pre-agreed, observable condition that pauses or ends AI-assisted work and
transfers control to a named person. A stop rule must specify the trigger,
detection method, immediate containment action, escalation owner, evidence
to preserve, recovery authority, and notification duty.

**Sustainment measure**
A measure that tracks whether the governance and operational conditions that
enabled safe AI use remain in place over time: control-test pass rate,
model and prompt stability, drift detection, and benefit persistence.

**Tier factor**
One of the inputs assessed when assigning a provisional tier: where the
output meets the world, accountability and competence, affected people and
impacts, data and authority, evidence and uncertainty, consequence and
reach, reversibility and recovery, legal and regulatory context, and
governance capacity. No single factor sets the tier.

**Use case**
A specific AI-assisted workflow or capability assessed as a unit for
tiering, governance, and measurement purposes. A use case is defined by
what the AI does, what it does not do, who is affected, and how the output
connects to decisions or actions.
