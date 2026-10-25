# Using this repository with ChatGPT

This is the ChatGPT-oriented entry point for Lemo-Opuscar. Preserve the original library, styles, licenses, and rendering pipeline.

## Workflow

1. Read `AGENTS.md`, `DIRECTOR.md`, `TECHNIQUE.md`, `core/README.md`, and `MY-STYLES.md` before directing a film.
2. Check the user's own style index if available; otherwise select a library style that fits the brief and read its `STYLE.md`.
3. Write a new treatment before reading demo code. Use demos only to learn techniques, not to copy their story, shot sequence, props, or timeline.
4. Put user-owned film work under `films/<film-slug>/`, outside `styles/`.
5. Follow the chosen style's invariants and existing renderer contract, including `window.READY`, deterministic `window.render(t)`, `window.DUR`, optional `window.EV`, and `window.TEXTS(t)` where applicable.
6. Use the existing rendering, audio, subtitle, and mux tools wherever possible. Render and inspect representative stills before the full film.
7. Report exactly what ran and whether it passed. Never claim a render, test, upload, or commit succeeded without a confirming result.
8. Claude-specific tool names such as `AskUserQuestion` are not assumed available in ChatGPT; ask one concise question only when an essential decision is missing.

## Film scaffold

The Mata Mansa Devi film planning files live in `films/mansa-mansa-devi/`. They describe a 60-second, 1920×1080, 24 fps English-language anime-inspired short using code-based rendering, not a paid AI video-generation service. Planning files do not mean the film is implemented or rendered.

## Environment and repository hygiene

Verify Node.js 20+, FFmpeg, and Python 3.11+ (or uv) before running the documented pipeline. Preserve upstream license notices. Do not commit credentials, caches, dependency folders, or large render outputs unless explicitly requested. Keep commits small and descriptive.
