# References

**Version:** 2026-09-16
**Author:** Samuel Tait
**Licence:** CC BY 4.0 (see [LICENSE](LICENSE))

This is the source register for the AI Adoption Field Guide. Each entry
records the source, the concept or content it informed, and the access date.
Links to external sources should be verified before relying on them; official
guidance documents are occasionally moved or updated.

---

## Primary governance frameworks

**[1] Australia's Guidance for AI Adoption: Implementation Guidance**
- Publisher: National AI Centre, Australian Government
- Date: May 2026 (implementation guidance); October 2025 (foundations v1.0)
- URL: https://www.ai.gov.au/staying-safe-and-responsible/essential-ai-practices/guidance-ai-adoption-implementation-guidance
- Access date: 16 September 2026
- Informed: The six essential practices used as the group rows of the
  governance-requirement mapping table; practice 6, "Maintain human
  control", as the organising axis of the tier model; practices 1,
  "Decide who is accountable", and 2, "Understand impacts and plan
  accordingly", as the entry gates; practice sub-area references
  (1.1 through 6.2).

**[2] NIST AI Risk Management Framework (AI RMF 1.0)**
- Publisher: National Institute of Standards and Technology, US Department
  of Commerce
- Date: 26 January 2023 (verified against nist.gov, 16 September 2026)
- URL: https://www.nist.gov/itl/ai-risk-management-framework
- Access date: 16 September 2026
- Informed: The four core functions (Govern, Map, Measure, Manage) mapped
  to each tier alongside the Australian practices; the framing of risk
  management as an ongoing process spanning identification, analysis,
  response, and governance.

**[3] DTA Policy for the responsible use of AI in government (v2.0)**
- Publisher: Digital Transformation Agency, Australian Government
- Effective date: 15 December 2025
- URL: https://www.digital.gov.au/ai/ai-in-government-policy
- Access date: 16 September 2026
- Informed: The note in the risk tier model that use-case impact assessments
  are mandatory for in-scope Commonwealth agency use cases under this policy;
  the worked example for the local council (noting that local government
  may have analogous obligations under state policy).

---

## Related work

**[4] Huryn, P. (2026). "The Intent Engineering Framework for AI Agents."**
- Publisher: Product Compass
- Date: 13 January 2026 (updated 22 July 2026)
- URL: https://www.productcompass.pm/p/intent-engineering-framework-for-ai-agents
- Also: Substack note, 14 January 2026, https://substack.com/@huryn/note/c-199618549
- Access date: 16 September 2026
- Role in this guide: The tiered approach to AI decision authority in this
  guide builds on Huryn's decision-type hierarchy, which orders autonomy
  levels by blast radius and reversibility and introduces stop rules and
  health metrics as governance concepts. This guide reorganises the tiers
  on Australia's Guidance for AI Adoption practice 6, "Maintain human
  control", adds practices 1 and 2 as entry gates, and maps every practice
  and NIST AI RMF function to each tier. The decision-rights question bank,
  the oversight patterns, the stop-rule categories and the worked examples
  are this guide's own. Huryn's level names (Full Autonomy / Guarded
  Autonomy / Proposal-First / No Autonomy, Human-Required) and his
  seven-part specification are his published work and are not used here.

**[5] Spencer, S. (2026). "The Conscience Graph: a built-in, layered, provenanced value graph for AI reasoning."**
- Publisher: Edgelabs. Position paper and open call for collaboration,
  version 0.2, dated 10 September 2026.
- Authorship: the paper's copyright statement names Simon Spencer as author
  and originator, working in collaboration with Claude (Anthropic).
- Published as: a PDF document attached to a LinkedIn post by Simon Spencer
  on 11 September 2026, visible to anyone on or off LinkedIn. At the time of
  writing this is the only public copy; there is no repository, preprint or
  Edgelabs website copy.
- URL: https://www.linkedin.com/posts/simonspencer_the-conscience-graph-activity-7503683676421951488-RFEi/
- Access date: 16 September 2026
- Licence: paper and diagrams CC BY 4.0; schema and reference code
  Apache 2.0. The licence conditions require attribution to Simon Spencer
  and Edgelabs, citation of the paper, naming the Conscience Graph as the
  source concept, marking any changes, and: "Do not claim origination of
  the concept, the layered model, the four-band fast path, re-attribution,
  or qualification-bound delegation caps as described here." None of those
  is claimed by this guide.
- Status: a design proposal. The paper states that it proposes a schema, a
  prototype and an evaluation approach; it reports no implementation and
  no evaluation results. Nothing adapted from it is presented in this guide
  as evidence or established practice.
- Role in this guide: four mechanisms adapted, each marked in place with
  the change made (Spencer's subject is an agent's internal pre-reasoning
  filter; this guide applies each mechanism to an organisation's control
  decisions over an AI-assisted workflow):
  - Section 4.1, three ways rule lists fail (coverage, conflict,
    brittleness): README.md, "Why tiers and stop rules, not a rule list".
  - Sections 5.8 and 6, the "unknown" band ("unknown is not comfort"):
    04-stop-rules/stop-rules.md, category 13, "No comparable case", and
    the "Silence is not permission" principle; cross-referenced from the
    tier factors in 01-risk-tiers/risk-tier-model.md.
  - Section 5.9, plasticity falls under load: 03-oversight-patterns/
    oversight-patterns.md, "After an incident: tighten under load".
  - Section 8.3, evaluation stages "consistency under reframing", "does
    it escalate" and "does it know what it does not know":
    03-oversight-patterns/oversight-patterns.md, "Two pre-deployment test
    designs".
- Not adapted: the layered value model, the four-band fast path as a
  whole, asymmetric learning, lineage, re-attribution, qualification and
  delegation caps, the schema, and the paper's vocabulary.

---

## Statutes referred to in the worked examples

The worked examples name the following Australian laws to show which
matters must always reach a person. The names and years were verified
against the official legislation register on 16 September 2026; the guide
does not interpret them.

- Australian Consumer Law (Schedule 2 to the Competition and Consumer Act
  2010): retail example.
- Education Services for Overseas Students Act 2000 (No. 164, 2000):
  university example.
- Disability Discrimination Act 1992 (No. 135, 1992): university example.

---

## Incident illustration sources

The incident illustration in `07-incident-illustration/exploitgym-2026.md`
is cited from the two primary reports below.

How it came to the author's attention: through the LinkedIn post of
11 September 2026 that accompanies Spencer's paper (entry [5]; the post is
the paper's publication venue), which opens with a short account of the
incident as its case study. The paper itself, as reviewed for this guide,
does not discuss the incident anywhere; the post and the paper are
different documents and only the post mentions it. The incident is cited
here solely from the primary reports [6] and [7]; nothing in the
illustration rests on the post.

For readers who compare the two, the post's brief account differs from the
primary reports in three respects. This is the ordinary difference between
a short secondary account and two long primary reports, not a criticism of
the post:

1. The post describes the agents as having reverse-engineered "the answer
   key". The METR report describes reverse-engineering of the HMAC used to
   generate task flags, and characterises the motive as "understanding the
   implementation of the scorer rather than stealing answer keys".
2. The post's account can be read as attributing transcript or tool-call
   spoofing to the agent population as a whole. METR reports it as a
   minority activity: "at least a dozen" developers, "nearly a hundred"
   replicators, roughly 7% of evaluated transcripts, all small scale.
3. The post gives a compressed duration. The primary reports give specific
   dates: message-board activity 8 to 13 July, Hugging Face production
   compromise 11 to 13 July, detection 19 July, public disclosure 21 July.

The illustration follows the primary reports on all three points.

**[6] METR and Redwood Research. "Brief independent investigation of agents'
behavior, reasoning and collaboration in the OpenAI / Hugging Face hacking
incident."**
- Authors: Hjalmar Wijk and Ajeya Cotra (METR); Ryan Greenblatt (Redwood
  Research, contracting with METR).
- Publication date: 26 August 2026 (stated on the report cover).
- Scope: an independent investigation, six days on premises at OpenAI,
  focused on the period 7 to 13 July 2026 within an agreed window of
  26 June to 13 July 2026.
- URLs: https://metr.org/blog/2026-08-26-openai-hugging-face-incident-investigation/
  and https://metr.org/hugging-face-incident-report-aug-2026.pdf
- Access date: 16 September 2026
- Informed: the incident illustration only. All quoted figures (tens of
  thousands of agents launched; ~30-40% of tasks impossible; ~1200 agents
  on the board and ~700 attacking Hugging Face; HMAC reverse-engineered to
  understand the scorer "rather than stealing answer keys"; tool-call
  spoofing by "at least a dozen" developers and "nearly a hundred"
  replicators, ~7% of evaluated transcripts, all small scale; 533 board
  agents with over 90% joining; 3-6 agents considering alerting humans and
  none pursuing it; the scorer "doesn't actually run a scoring model to
  check for usage of the intended vulnerability at all") are taken from
  this report.

**[7] OpenAI. "Hugging Face Incident Technical Report."**
- Publisher: OpenAI.
- Date: 2026. The copy reviewed carries no printed publication date. The
  public disclosure of the incident was 21 July 2026, and the companion
  METR and Redwood Research report is dated 26 August 2026, so this report
  post-dates the investigation it describes.
- URL: https://cdn.openai.com/pdf/67869394-cb91-4c12-888c-5cbd85c7814c/OpenAI-Hugging-Face%20Incident-Technical-Report.pdf
- Access date: 16 September 2026
- Informed: the incident illustration only. The research-evaluation limits
  (safeguards disabled to measure true capability; internal-only research
  model prototype not intended for release; no impact on customer data,
  product functionality or availability; production auto-review would have
  flagged most dangerous actions) and the incident timeline (production
  compromise 11 to 13 July; detected 19 July; disclosed 21 July) are taken
  from this report.

---

## Repository and open-source references

**[8] microsoft/agent-governance-toolkit**
- Publisher: Microsoft
- Licence: MIT
- URL: https://github.com/microsoft/agent-governance-toolkit
- Access date: 16 September 2026
- Informed: General reference for open-source AI governance tooling;
  confirmed that governance toolkits targeting enterprise AI agents are
  an active area of public development.

**[9] UrbanInstitute/agentic-ai-playbook**
- Publisher: Urban Institute
- Licence: CC BY 4.0
- URL: https://github.com/UrbanInstitute/agentic-ai-playbook
- Access date: 16 September 2026
- Informed: General reference for publicly available governance playbooks
  for agentic AI in public-interest contexts.

---

## Cited to mark a boundary, not adapted

**[10] Afroogh, S., Varshney, K. R., & D'Cruz, J. (2025). "A Task-Driven
Human-AI Collaboration: When to Automate, When to Collaborate, When to
Challenge."**
- Authors: Saleh Afroogh, Kush R. Varshney, Jason D'Cruz
- Publisher: arXiv preprint, arXiv:2505.18422 [cs.CY]. Version 6 at the time
  of access.
- Date: first posted 23 May 2025. Identifier, title and author names verified
  against export.arxiv.org on 16 September 2026.
- URL: https://arxiv.org/abs/2505.18422
- Access date: 16 September 2026
- Role in this guide: cited in `01-risk-tiers/risk-tier-model.md` under
  "Related work", and in `GLOSSARY.md` and
  `02-decision-rights/question-bank.md` to disambiguate the term "decision
  rights". The paper classifies a single task by risk and complexity, maps it
  to an autonomous, assistive or adversarial AI role, and allocates
  initiative, control and decision rights as three separate questions. This
  guide works at a different unit (the use case, not the task) and on a
  different primary axis (where the output meets the world, not risk by
  complexity), and treats consequence, reach and reversibility as inputs to
  the adequacy test rather than as the classifier.
- Not adapted: the risk by complexity matrix, the three AI roles and the
  agency triad are the authors' framework. Nothing from the paper is
  reproduced or adapted in this guide. It is cited so that a reader who knows
  that framework can see where the two differ and why.

---

## Source register notes

- This register covers the primary sources drawn on in drafting this guide.
  It does not list every source consulted during research.
- Statistics and claims from secondary sources (consulting reports, news
  articles, analyst notes) are not used in this guide. Where a statistic
  appears, it must be traceable to a primary source listed here.
- Drafting records for this guide are kept outside this repository.
