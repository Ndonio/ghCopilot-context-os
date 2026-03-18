# Context OS — Copilot Instructions

## Session Start

Read the latest handoff in docs/summaries/ if one exists. Load only the files that handoff references — not all summaries. If no handoff exists, ask: what is the project, what type of work, what is the target deliverable.

Before starting work, state: what you understand the project state to be, what you plan to do this session, and any open questions.

## Identity

<!-- Customize this section for your workflow. Examples:
     - "You work with [Name], a software engineer building [product]."
     - "You work with [Name], a consultant preparing client deliverables."
     Keep it to 2-3 lines. -->

You work with [Your Name], [your role and context]. Adapt your communication style and outputs to match this domain.

## Rules

1. Do not mix unrelated project contexts in one session.
2. Write state to disk, not conversation. After completing meaningful work, write a summary to docs/summaries/ using templates from templates/templates.md. Include: decisions with rationale, exact numbers, file paths, open items.
3. Before the conversation gets long or a session ends, write to disk: every number, every decision with rationale, every open question, every file path, exact next action.
4. When switching work types (research → writing → review), write a handoff to docs/summaries/handoff-[date]-[topic].md and suggest starting a new chat.
5. Do not silently resolve open questions. Mark them OPEN or ASSUMED.
6. Do not bulk-read documents. Process one at a time: read, summarize to disk, release from context before reading next. For the detailed protocol, read docs/context/processing-protocol.md.
7. Subagent returns must be structured, not free-form prose. Use output contracts from templates/templates.md.

## Where Things Live

- templates/templates.md — summary, handoff, decision, analysis, task, output contract templates (read on demand)
- docs/summaries/ — active session state (latest handoff + project brief + decision records + source summaries)
- docs/context/ — reusable domain knowledge, loaded only when relevant to the current task
  - processing-protocol.md — full document processing steps
  - archive-rules.md — summary lifecycle and file archival rules
  - subagent-rules.md — when to delegate work to subagents
  <!-- Add your own domain context files here. Examples:
       - tech-stack.md — architecture decisions
       - style-guide.md — coding or writing conventions -->
- docs/archive/ — processed raw files. Do not read unless explicitly told.
- output/deliverables/ — final outputs
- .github/prompts/ — reusable prompt files for common workflows (handoff, status, process-doc)

## Error Recovery

If context degrades or the conversation becomes too long: write current state to docs/summaries/recovery-[date].md, tell the user what may have been lost, suggest a fresh chat session.

## Before Delivering Output

Verify: exact numbers preserved, open questions marked OPEN, output matches what was requested (not assumed), claims backed by specific data, output consistent with stored decisions in docs/context/, summary written to disk for this session's work.
