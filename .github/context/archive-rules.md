# Archive Rules

## Raw File Archival

After creating a Source Document Summary for any raw file:
1. Move the raw file to `.github/archive/`
2. Record the move in the source summary's header: `Archived From: [original path]`
3. Do not read from `.github/archive/` unless the user explicitly says "go back to the original [filename]"

## Summary Lifecycle Rules

1. **Session handoffs expire**: After a new handoff is written, the previous handoff moves to `.github/archive/handoffs/`. Only the latest handoff stays in `.github/summaries/`.
2. **Decision records persist**: Decision records (DR-*) stay in `.github/summaries/` permanently — they are institutional memory.
3. **Source summaries persist**: Source document summaries stay until the project ends — they replace raw documents.
4. **Analysis summaries**: Keep only the latest version. If re-run, the new one replaces the old (archive the old one).
5. **Maximum active summaries**: If `.github/summaries/` exceeds 15 files, consolidate older source summaries into a single `project-digest.md` and archive the originals.
