# Using this repository with ChatGPT

This is the ChatGPT-oriented entry point for Lemo-Opuscar. Preserve the original library, styles, licenses, and rendering pipeline.

## Core rule: the story is runtime input

**Never treat a previous film's story, characters, scenes, dialogue, shot list, or timings as defaults for the next film.** Each user request supplies a new story or topic. Every run must derive a fresh treatment and production plan from that input.

Hardcode only reusable production behavior and the chosen style's documented invariants: rendering mechanics, reusable animation primitives, camera grammar, palette, typography, texture, motion language, sound palette, validation, and export conventions. Story-specific content belongs only in that film's own `films/<film-slug>/` directory.

## Workflow

1. Read `AGENTS.md`, `DIRECTOR.md`, `TECHNIQUE.md`, `core/README.md`, and `MY-STYLES.md` before directing a film.
2. Read the user's story/topic and any explicit constraints (duration, language, audience, aspect ratio, tone, budget, content boundaries). If the story is absent or essential constraints conflict, ask only for what is needed.
3. Check the user's own style index if available; otherwise choose a suitable library style and read its `STYLE.md`. Keep style invariants separate from story content.
4. Create a fresh `films/<film-slug>/` for this run. Write a new treatment with three candidate structures and a reasoned choice before consulting demo code. Do not overwrite another film's story files or reuse its plot.
5. Derive this film's character descriptions, scene list, storyboard, dialogue, and sound cues from the current input. Treat all example film folders as examples of output structure only—not as narrative templates.
6. Implement each scene using reusable renderer primitives and the selected style's invariants. Do not put story-specific names, dialogue, props, or scene timings in shared engine code or style definitions.
7. Follow the chosen style's existing renderer contract, including `window.READY`, deterministic `window.render(t)`, `window.DUR`, optional `window.EV`, and `window.TEXTS(t)` where applicable.
8. Use the existing rendering, audio, subtitle, and mux tools wherever possible. Render and inspect representative stills before the full film.
9. Report exactly what ran and whether it passed. Never claim a render, test, upload, or commit succeeded without a confirming result.
10. Claude-specific tool names such as `AskUserQuestion` are not assumed available in ChatGPT; ask one concise question only when an essential decision is missing.

## Reusable vs. per-film data

- **Reusable/shared:** renderer, scene orchestration, drawing and animation helpers, camera transitions, style invariants, audio mixing/export, schemas, validation.
- **Generated fresh for each film:** treatment, story structure, characters, locations, shots, scene timings, dialogue, captions, sound cues, asset manifest.
- **Never do:** import a previous film's storyboard or dialogue as the next film's default; encode a specific story into the shared renderer; change the style to fit a demo's story.

## Example project

`films/mansa-mansa-devi/` is one sample planning project only. It is not a default story and must not be automatically loaded for future requests. New requests must get a separate slug directory and newly generated production data.

## Environment and repository hygiene

Verify Node.js 20+, FFmpeg, and Python 3.11+ (or uv) before running the documented pipeline. Preserve upstream license notices. Do not commit credentials, caches, dependency folders, or large render outputs unless explicitly requested. Keep commits small and descriptive.
