# Changelog

All notable changes to this guide are recorded here.

The version identifier is the date of the release in ISO 8601 format
(YYYY-MM-DD). The guide uses date-based versioning rather than semantic
versioning because it is a governance reference document, not software.

---

## 2026-09-16 (revision 2): Licence, repository standards, diagrams

**Licence**

- `LICENSE` now contains the unmodified CC BY 4.0 legal code. The previous
  file paraphrased the licence and appended third-party terms to it, so
  automated licence detection could not match it and the repository was
  reported as `NOASSERTION`.
- `THIRD_PARTY_NOTICES.md` added. The referenced and adapted work previously
  appended to `LICENSE` is recorded there instead.

**Repository standards**

- `AGENTS.md` added: source of truth, confidentiality limits, style rules,
  and the test a diagram must pass to be included.
- `CODE_OF_CONDUCT.md` added. Original text written for this repository. It
  is not the Contributor Covenant and should not be cited as it.
- `CITATION.cff` added, so the guide can be cited directly from GitHub.
- `.github/` added with two issue templates and a pull request template.
  These carry no executable content. `CONTRIBUTING.md` now states this
  metadata exception explicitly and records that no workflows, dependency
  automation or build step will be accepted.

**Diagrams**

- `01-risk-tiers/risk-tier-model.md`: the tier selection diagram was
  replaced. The previous version asked which control mechanism the
  organisation could exercise and, at each failure, moved to a tier with a
  weaker control. That contradicts this guide's own rule that where an
  organisation cannot provide what a mechanism requires the answer is
  Restricted, not a lower standard. The replacement takes where the output
  meets the world as the classifier, consistent with the tier factors, and
  routes any gate or adequacy failure to Restricted.
- `01-risk-tiers/risk-tier-model.md`: the entry gate diagram was removed. It
  used a full screen of vertical space to restate a relationship the adjacent
  sentence already states.
- `04-stop-rules/stop-rules.md`: the stop rule diagram was removed and its
  introduction rewritten. The diagram presented the seven fields as a firing
  sequence, implied that the recovery authority is necessarily a later step
  than the escalation owner, and implied that evidence preservation and
  notification wait on escalation. The seven fields are a specification, not
  a sequence.

**References**

- `REFERENCES.md` entry [10] added: Afroogh, Varshney and D'Cruz (2025),
  arXiv:2505.18422, cited to mark the boundary between task-level allocation
  and use-case-level tiering. Nothing from it is adapted. Identifier, title
  and author names verified against export.arxiv.org on 16 September 2026.
- `GLOSSARY.md` and `02-decision-rights/question-bank.md`: the term "decision
  rights" is now distinguished from the narrower sense used in
  task-allocation frameworks.

---

## 2026-09-16: Initial release

**Included at initial release:**

- `README.md`: purpose, audience, navigation, related work, licence.
- `QUICKSTART.md`: five-step deployment checklist and minimum governance
  checklist.
- `CONTRIBUTING.md`: how to report errors and propose changes.
- `01-risk-tiers/risk-tier-model.md`: four-tier model (Assist / Advise /
  Act with approval / Restricted) organised on Australia's Guidance for
  AI Adoption practice 6, "Maintain human control", with practices 1 and 2
  as entry gates; mapping of all six practices and the NIST AI RMF
  functions to each tier; tier definitions; a self-service variant of
  Assist; tier factors; mandatory escalation triggers.
- `02-decision-rights/question-bank.md`: ten-section question bank leading
  to a provisional tier and named decision owners.
- `03-oversight-patterns/oversight-patterns.md`: eight reusable oversight
  patterns with prerequisites, failure modes, and escalation routes.
- `04-stop-rules/stop-rules.md`: thirteen stop-rule categories, including
  category 13, "No comparable case", and a structured template for
  defining rules for a specific use case.
- `05-adoption-measures/measures.md`: adoption, human-control, outcome,
  risk and equity, and sustainment measures with baseline discipline.
- `06-worked-examples/local-council-service-requests.md`: Advise tier;
  routing triage at a fictional local government authority.
- `06-worked-examples/university-student-enquiries.md`: Assist tier,
  self-service variant, with route-to-adviser paths; policy enquiries at
  a fictional university.
- `06-worked-examples/retail-returns-resolution.md`: multi-tier example
  (Assist / Advise / Act with approval); returns and customer resolution
  at a fictional Australian retailer.
- `07-incident-illustration/exploitgym-2026.md`: a real, documented
  incident (the OpenAI ExploitGym / Hugging Face incident, July 2026) read
  through the guide's lens. Kept separate from the fictional worked
  examples. An illustration only, not the basis of the model; states its
  research-context limits up front. Cited from two primary reports
  (REFERENCES.md [6] METR/Redwood and [7] OpenAI).
- `GLOSSARY.md`: key terms used in this guide.
- `LIMITATIONS.md`: scope, caveats, and what this guide does not do.
- `REFERENCES.md`: source register.
- `LICENSE`: CC BY 4.0.
- `CHANGELOG.md`: this file.

**Adapted material at initial release:** four mechanisms adapted, with
changes marked in place, from Simon Spencer and Edgelabs, "The Conscience
Graph" (v0.2, September 2026, CC BY 4.0), the source concept: the three
ways rule lists fail (README.md); the "unknown" band, adapted as stop-rule
category 13, "No comparable case" (stop-rules.md, cross-referenced from
risk-tier-model.md); plasticity falls under load, adapted as "After an
incident: tighten under load" (oversight-patterns.md); and two evaluation
stages, adapted as "Two pre-deployment test designs" (oversight-patterns.md).
Each is applied to an organisation's control decisions rather than to an
agent's internal filter. The paper is a design proposal with no reported
implementation or evaluation. See REFERENCES.md [5].

**Next scheduled review:** no later than 2027-09-16.

---

## Review and staleness policy

This guide is reviewed:

- When Australia's Guidance for AI Adoption or the NIST AI RMF materially
  changes.
- When a cited source changes.
- When a material error is reported.
- At least annually.

After 18 months without a recorded review, a prominent staleness notice
will be added to README.md.
