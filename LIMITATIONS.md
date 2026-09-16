# Limitations and disclaimer

**Version:** 2026-09-16
**Author:** Samuel Tait
**Licence:** CC BY 4.0 (see [LICENSE](LICENSE))

---

## What this guide is

This guide is a practical governance reference for assigning proportionate
human control to AI-assisted workflows. It provides a risk tier model, a
decision-rights question bank, oversight patterns, stop-rule categories,
and adoption and benefits-realisation measures.

It is written by an individual practitioner, published under CC BY 4.0, and
intended as a starting point for governance design, not a finished
compliance answer.

---

## What this guide is not

**Not legal advice.** Nothing in this guide constitutes legal advice. If
your use case involves legal obligations, regulated activities, personal
data, or potential liability, you must obtain specialist legal advice before
relying on any element of this guide.

**Not a certification or audit standard.** Assigning a tier using this guide
does not certify compliance with any law, regulation, or technical standard.
It does not substitute for a formal conformity assessment, an impact
assessment required by law or policy, or an independent audit.

**Not a substitute for sector-specific guidance.** Many industries and
public-sector contexts have requirements that go beyond anything in this
guide: health, finance, safety-critical infrastructure, government services,
education, employment, and others. This guide does not address those
requirements and cannot substitute for sector-specific regulatory guidance.

**Not a complete governance framework for any organisation.** This guide
covers one part of AI governance: risk tiering, decision rights, oversight,
stop rules, and measurement. It does not address procurement, contracting,
training, workforce planning, change management, organisational strategy,
or the full range of requirements in Australia's Guidance for AI Adoption
or NIST AI RMF.

---

## Primary context

This guide is designed primarily for Australian contexts. The risk tier
model is organised on Australia's Guidance for AI Adoption (National AI Centre,
2025-2026) and the DTA Policy for the Responsible Use of AI in Government
(effective December 2025). Most of the governance principles are broadly
applicable, but readers in other jurisdictions should verify applicability
against their local frameworks.

---

## Fictional examples

The three worked examples in this guide (Riverbend City Council, Hartland
University, and Northfield Home & Garden) are entirely fictional.
Organisations, people, volumes, and outcomes are invented. They are designed
to show how the tier model, question bank, patterns, stop rules, and measures
apply in different contexts. They are not intended as recommendations for any
real organisation, and no resemblance to any real person, organisation, or
situation is intended or should be inferred.

Numerical figures in the examples (e.g. volumes, handling times, rates) are
illustrative. They are not benchmarks, industry averages, or predictions.

The three worked examples in `06-worked-examples/` are the fictional ones.
The incident illustration in `07-incident-illustration/` is different: it is
a real, documented event (the OpenAI ExploitGym / Hugging Face incident of
July 2026), cited from two primary reports. It is included to show the
guide's ideas at work on a real failure. Its own limits are stated in that
file and matter: it describes a research evaluation in which safeguards were
deliberately reduced, driven primarily by an internal-only research model,
with no impact on customer data, product functionality or availability. It
is not a description of any deployed product and must not be read as one.

---

## Tier is a starting point

The tier assigned to a use case using this guide is a provisional starting
point for governance design. It is not a permanent determination, a
compliance guarantee, or a substitute for ongoing review. It must be
reassessed when the use case, data, model, scale, or governance capacity
changes materially.

Applying a more conservative tier is always available when the assessment is
uncertain.

---

## Completeness and currency

This guide was drafted at a point in time. Guidance from the National AI
Centre, NIST, and other referenced bodies changes over time. Users should
check primary sources directly and not rely solely on this guide for the
current state of any framework. See [REFERENCES.md](REFERENCES.md) for the
source register, including access dates.

---

## Attribution and third-party rights

Original guide text is licensed under CC BY 4.0. Referenced frameworks
retain their own rights and are not covered by this licence. See
[LICENSE](LICENSE).
