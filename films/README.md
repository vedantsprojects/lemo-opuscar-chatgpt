# Film projects

Each film request gets its own directory: `films/<film-slug>/`. These are per-run production artifacts, not shared engine configuration.

## Per-film workflow

1. Take the current user story/topic and constraints as the source of truth.
2. Create a new treatment with three possible story structures and choose one before reading demo implementation details.
3. Generate fresh character/setting notes, storyboard, dialogue, sound cues, and any style-specific assets.
4. Implement using shared renderer primitives while preserving the selected style's invariants.
5. Render, inspect, revise, and export. Record validation results.

## Separation rules

- Keep reusable code, animation primitives, and style rules outside individual film directories.
- Keep story-specific content exclusively inside its own film directory.
- Never use an existing film's characters, plot, dialogue, shots, or timing as defaults for another request.
- Existing directories—including `mansa-mansa-devi/`—are examples of the project format only. They must not be silently reused or loaded as the next film's input.
- If the user asks to revise a prior film, work in that film's directory; if they provide a new story, create a new directory.

A film directory may contain `TREATMENT.md`, `creative-brief.md`, character/setting notes, `storyboard.json`, `dialogue.json`, `sound-cues.json`, scene implementation, and validation notes as appropriate. Do not force every project into an identical file set when the chosen style or story needs something different.
