# Changelog

## v4.0.0 (2026-02-13) — Research-Backed Redesign

A complete rewrite of CLAUDE.md based on 9 peer-reviewed papers on how LLMs actually process system prompts. The core insight: fewer, better-placed rules outperform comprehensive documentation.

### Changed
- **CLAUDE.md**: 327 lines → 47 lines. 15+ rules → 7 rules. Zero explanatory prose.
- **Language**: "CRITICAL / NEVER / MUST" → plain imperatives. Claude 4.6 overtriggers on emphatic language.
- **Session startup**: "Read all summaries" → "Read only what the handoff references." Surgical context loading.
- **README.md**: Complete rewrite with research citations, v3→v4 migration guide, design decision table.

### Added
- **`docs/context/` directory**: Reference files loaded on demand instead of embedded in CLAUDE.md.
  - `processing-protocol.md` — document processing steps
  - `archive-rules.md` — summary lifecycle and file archival rules
  - `project-structure.md` — full directory tree + scaffold commands
  - `subagent-rules.md` — when to use subagents vs. main agent
- **Template 6: Task Definition** — action/verify/done format for discrete work units.
- **"Files to Load Next Session"** field in handoff template — progressive disclosure index layer.
- **Work-type → context mapping** in CLAUDE.md "Where Things Live" section.
- **`CLAUDE-v3.md`** — previous version preserved for reference and migration.

### Removed from CLAUDE.md (moved to docs/context/)
- Document Processing Protocol → `docs/context/processing-protocol.md`
- Archive Protocol → `docs/context/archive-rules.md`
- File Organization Standard → `docs/context/project-structure.md`
- Subagent Deployment Rules → `docs/context/subagent-rules.md`
- "Structured Summarization: Why It Matters" section (coherent filler, cut entirely)
- "Cost of NOT Splitting" section (persuasive prose, cut entirely)
- Context Budget Check arithmetic (Claude doesn't reliably self-monitor tokens)
- Quick Reference table (user commands, not agent instructions)
- MCP Server Awareness (situational, not always-load)

### Research Basis
- [Working Memory Limits](https://arxiv.org/abs/2409.10715) — 5-10 rule cap
- [Context Rot](https://research.trychroma.com/context-rot) — coherent filler interference
- [Hidden in the Haystack](https://arxiv.org/abs/2505.18148) — rule sizing (1-3 lines)
- [Lost in the Middle](https://aclanthology.org/2024.tacl-1.9/) — U-shaped attention, end-position boost
- [Claude 4 Best Practices](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-4-best-practices) — overtriggering
- [Anthropic Context Engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) — just-in-time loading

---

## v1.1.0 (2026-02-11) — Community Improvements

### Fixed
- **Step 1 vs Rule 1 contradiction**: Session startup no longer bulk-reads all summary files. Now reads only `00-project-brief.md` + latest handoff, loading others on-demand.

### Added
- **Lightweight templates**: 3-field versions of Source Summary, Session Handoff, and Decision Record for projects under 5 sessions. Start light, upgrade when needed.
- **Worked example**: `examples/software-dev-project/` — a realistic 2-session Go project showing filled-in project brief, source summary, and session handoff.
- **Slash commands**: `/handoff`, `/process-doc`, `/status` — automate the most common protocols instead of following manual instructions.
- **Software Development workflow**: New phase-based workflow template (Template A) for dev projects alongside the existing consulting and agent development workflows.

### Changed
- **De-biased language**: Replaced consulting-specific terms throughout. "Client" → "Project Owner", "Engagement" → "Project". Project Brief template now works for any domain.
- **Template lettering**: Workflow templates re-ordered — Software Dev (A), Enterprise Sales (B), Agent Development (C), Hybrid (D).
- **`.gitignore`**: `.claude/commands/` now tracked so slash commands ship with the repo.

## v1.0.0 (2026-02-09) — Initial Release

- Core CLAUDE.md operating system (~3.5K tokens)
  - 4-step session startup protocol
  - 6 context management rules
  - Session discipline and handoff protocol
  - Document processing protocol
  - Archive protocol with summary lifecycle rules
  - Subagent deployment rules
  - Quality gates checklist
  - Error recovery procedures
- Structured templates (`templates/claude-templates.md`)
  - 5 core templates: Source Summary, Analysis Summary, Decision Record, Session Handoff, Project Brief
  - 3 subagent output contracts: Document Analysis, Research/Analysis, Review/QA
  - 3 phase-based workflow templates: Enterprise Sales, Agent Development, Hybrid
