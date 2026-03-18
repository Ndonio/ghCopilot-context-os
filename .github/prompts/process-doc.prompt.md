---
description: "Process an input document into a structured summary"
---

Process the provided document following the protocol in `docs/context/processing-protocol.md`.

Use Template 1 (Source Document Summary) from `templates/templates.md` to create a structured summary.

Write the summary to `docs/summaries/source-{filename}.md`.

Extract and preserve:
- Every exact number, date, percentage, amount
- All requirements with conditions and constraints
- Decisions referenced with rationale
- Relationships to other known project documents
- Open questions and ambiguities
- Key verbatim quotes (2-5 max)

After writing the summary, confirm what was captured and flag anything marked UNCLEAR or ASSUMED.
