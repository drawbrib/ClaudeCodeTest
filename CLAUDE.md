# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository

GitHub: https://github.com/drawbrib/ClaudeCodeTest

## Git Workflow

After every meaningful change, commit with a clean message and push:

```bash
git add <files>
git commit -m "Subject line

Optional body explaining what and why."
git push
```

Use imperative subject lines ("Add", "Fix", "Update"). Each logical change gets its own commit — don't batch unrelated work.

## Stack

All projects are **single-file HTML apps** — no build step, no package manager, no framework. Each file contains HTML, CSS, and JavaScript inline. Open directly in a browser.

## Projects

- **tictactoe.html** — Two-player and vs-CPU Tic Tac Toe. CPU uses minimax. Dark theme.
- **mlb_predictor.html** — Yankees vs Giants run/HR predictor. Fetches live data from the free MLB Stats API (`statsapi.mlb.com/api/v1`) at page load. Falls back to hardcoded 2024 stats if the API is unavailable. Prediction formula: `team_R/G × (pitcher_ERA / lgERA) × park_factor`. Park factors are hardcoded (the API doesn't expose them).

## Design Conventions

- Dark theme: background `#1a1a2e`, card `#16213e`, accent `#e94560`, secondary `#a8dadc`
- No external dependencies — everything self-contained in the HTML file
- Graceful degradation: API failures show a warning and fall back to cached stats rather than breaking
