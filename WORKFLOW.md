# WORKFLOW.md

## Purpose

This repository is Shin’s Hugo website workspace. It should stay easy to resume, easy to verify, and easy to hand off.

## Folder conventions

- Content lives under `content/`.
- Notes live under `content/notes/`.
- The site is built and verified with Hugo.

## Required root docs

Keep these files at the repository root:

- `AGENTS.md`
- `PROJECT.md`
- `MEMORY.md`
- `STATE.md`
- `WORKFLOW.md`

## Agent start procedure

1. Read `AGENTS.md`.
2. Read `PROJECT.md`.
3. Read `MEMORY.md`.
4. Read `STATE.md`.
5. Read the relevant content files.

## Update procedure

- Update `STATE.md` when work is completed or status changes.
- Update `MEMORY.md` only for stable preferences or decisions.
- Update `PROJECT.md` when the overall framing or deliverables change.
- Verify content edits with `hugo --minify --cleanDestinationDir`.
- Commit changes when the requested work is complete.

## Closeout procedure

For a session closeout:
1. Make sure the root docs are current.
2. Confirm the completed work and next steps in `STATE.md`.
3. Leave the repository in a clean, understandable state.
