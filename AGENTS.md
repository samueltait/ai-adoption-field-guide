# Repository rules

**Version:** 2026-09-16
**Author:** Samuel Tait
**Licence:** CC BY 4.0 (see [LICENSE](LICENSE))

These are the rules any contributor, human or AI agent, must follow when
editing this repository. They exist because this is a governance reference:
its credibility rests on what it refuses to do as much as on what it says.

Read [CONTRIBUTING.md](CONTRIBUTING.md) as well. That file describes how to
propose a change. This file describes what the repository will not accept and
the standards a change must meet.

---

## Source of truth

- GitHub `main` is the published source of truth.
- [REFERENCES.md](REFERENCES.md) is the source register. Every substantive
  claim must trace to an entry in it.
- [CHANGELOG.md](CHANGELOG.md) records every released change. Update it as part
  of the same change, not afterwards.
- [LIMITATIONS.md](LIMITATIONS.md) bounds what the guide claims. Do not widen a
  claim without revisiting that file.
- [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) records what is not the
  author's own work.

---

## What must not enter this repository

- Client material, real organisation detail, or anything traceable to a real
  engagement. The worked examples are fictional and must stay fictional.
- Statistics from consulting reports, analyst notes or news articles without a
  primary source.
- Text copied from Australia's Guidance for AI Adoption, the NIST AI RMF, or
  any other referenced work. Link to them; do not reproduce them.
- Code, GitHub Actions, badges, widgets or binary files. The guide is plain
  Markdown so that it can be read and edited anywhere. The only permitted
  exception is repository metadata carrying no executable content:
  `CITATION.cff`, and the issue and pull request templates under `.github/`.
- Any framework, model, phrasing or structure taken from another author
  without attribution in `REFERENCES.md`. If an idea came from somewhere, say
  where it came from and what was changed.

---

## Style

- Australian English.
- Plain Markdown. No HTML.
- No em dashes. Use a colon, a comma, parentheses, or a new sentence.
- Every substantive section must produce something the reader can use: a tier,
  a named role, a stop rule, a measure.
- Cite sources in `REFERENCES.md` with title, publisher, date, URL and access
  date.

---

## Diagrams

The guide is deliberately sparing with diagrams. Before adding one:

- A diagram is justified only when it shows something the adjacent prose or
  table cannot. A diagram that restates a table is removed, not kept.
- A diagram must never assert a rule the text does not assert, and must never
  drop a condition the text states. Where the two disagree, the text governs
  and the diagram is wrong.
- Keep the whole diagram narrow. GitHub scales a Mermaid diagram down to fit
  the column rather than letting it scroll sideways, so at phone width the
  text inside the shapes is the first thing to become unreadable. Total
  rendered width is what governs this, and it is driven by the number of
  parallel branches as much as by the length of any one label: a wide fan of
  short labels can read as poorly as a narrow chain of long ones. Check any
  new or changed diagram at roughly 400px before accepting it.
- Any diagram must be fully redundant with the surrounding text, because a
  reader using a screen reader receives nothing from the rendered image.
- If a diagram needs an introductory sentence conceding that it is subordinate
  to the table beside it, that is evidence it has not earned its place.

---

## Browser work

Use BrowserOS neo for browser tasks. Name and isolate the session, and close it
when the task is complete.
