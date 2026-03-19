# Project Structure

## Directory Tree

```
project-root/
├── .github/
│   ├── copilot-instructions.md        ← Core instructions (read automatically by Copilot)
│   ├── prompts/                       ← Reusable prompt files
│   │   ├── handoff.prompt.md          ← End session, write state to disk
│   │   ├── status.prompt.md           ← Check project state
│   │   └── process-doc.prompt.md      ← Process a document into structured summary
│   ├── templates/
│   │   └── templates.md               ← Summary, handoff, decision, task, output contract templates
│   ├── context/                       ← Reusable domain knowledge (loaded on demand)
│   │   ├── client-briefs/             ← Per-client context files
│   │   ├── [your-domain].md           ← Your domain-specific context files
│   │   ├── [your-domain].md           ← (e.g., tech-stack.md, style-guide.md)
│   │   ├── processing-protocol.md     ← Document processing steps
│   │   ├── archive-rules.md           ← Summary lifecycle and file archival
│   │   ├── subagent-rules.md          ← When to use subagents vs. main agent
│   │   └── project-structure.md       ← This file
│   ├── summaries/                     ← ALL active session state lives here
│   │   ├── 00-project-brief.md        ← Initial project setup
│   │   ├── source-[filename].md       ← Per-document summaries
│   │   ├── analysis-[topic].md        ← Research outputs
│   │   ├── decision-[num]-[topic].md  ← Decision records
│   │   └── handoff-[date]-[topic].md  ← Latest session handoff ONLY
│   └── archive/                       ← Processed raw files (DO NOT read unless told)
│       └── handoffs/                  ← Superseded session handoffs
├── output/
│   ├── schemas/                       ← Data models, agent definitions
│   ├── prompts/                       ← System prompts for agents
│   ├── deliverables/                  ← Client-facing final outputs
│   └── presentations/                 ← Decks, workshop materials
```

## New Project Scaffold

```bash
mkdir -p .github/summaries .github/archive/handoffs .github/context/client-briefs .github/templates .github/prompts
mkdir -p output/schemas output/prompts output/deliverables output/presentations
```
