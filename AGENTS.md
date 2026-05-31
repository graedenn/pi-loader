# AGENTS.md

## Project
pi coding agent extension that replaces the default spinner with braille-dot animations. 54+ patterns configurable via `/loader` commands.

## Architecture
- `index.ts` — extension factory, preview component, config persistence
- `patterns.ts` — all pattern definitions (raw frame data)
- `braille-chars.txt` — reference for encoding braille frames
- `config.json` — persisted user config (pattern, color, speed)

Patterns are raw string arrays of 1-2 braille characters. All patterns use `type: "raw"` — no grid/generator functions.

## Workflows
- Extension goes in `~/.pi/agent/extensions/pi-loader/`
- `/reload` in pi to reload after edits
- `/loader preview` to browse and select patterns

## Conventions
- Add new patterns as `type: "raw"` entries in `patterns.ts` only
- Do not add grid/generator functions
- Color values: theme token name, `#hex`, or ANSI 0-255
- Preview keybindings: `←→` pattern, `↑↓` speed, `[]` color, `Enter` select
- Frame interval formula: `max(80, min(300, 1600 / frames.length)) / speed`

## Skills
- `thermo-nuclear-code-quality-review` — for deep code quality audits
