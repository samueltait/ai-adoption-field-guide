# Changelog

All notable changes to this guide are recorded here.

The version identifier is the date of the release in ISO 8601 format
(YYYY-MM-DD). The guide uses date-based versioning rather than semantic
versioning because it is a governance reference document, not software.

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
