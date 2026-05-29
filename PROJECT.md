# Project: shin13.github.io

建立日期：2026-05-30
最後更新：2026-05-30
專案資料夾：`/Users/shin/Projects/shin13.github.io`

## Agent start here

Any agent working in this repository should read, in order:

1. `PROJECT.md` — project overview and source-of-truth hierarchy.
2. `MEMORY.md` — stable repo preferences and decisions.
3. `STATE.md` — current status, completed work, next steps, blockers.
4. `WORKFLOW.md` — workspace rules and verification steps.
5. Relevant content files under `content/`.

## Project summary

This is Shin’s personal home on the internet, built with Hugo + PaperMod. The site emphasizes a calm, minimal personal-home structure rather than a job-search portfolio. Main navigation centers on Home, Now, Notes, Projects, About, and Search.

## Goal

Keep the site current, readable, and calm. The homepage and Now page should feel spacious and reflective. Notes should remain source-backed and concise. Technical changes should be verified with a Hugo build before commit/push.

## Core message / framing

This site is a personal home, not just a résumé. It should communicate current focus, ongoing questions, notes, and projects with minimal clutter.

## Current main deliverables

- `content/now/index.md`: current Now page.
- `content/notes/what-counts-as-human-ai-collaboration.md`: new research/essay note.
- `content/notes/_index.md`: Notes section intro.

## Source of truth hierarchy

1. Latest explicit user instruction.
2. `PROJECT.md`.
3. `STATE.md`.
4. `MEMORY.md`.
5. Content files.

## Working principles for agents

- Prefer minimal, direct edits.
- Verify site changes with `hugo --minify --cleanDestinationDir`.
- Preserve the calm personal-home style.
- Update `STATE.md` whenever substantial progress or status changes.
