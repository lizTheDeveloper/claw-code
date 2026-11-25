# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Detected stack
- Languages: Rust.
- Frameworks: none detected from the supported starter markers.

## Verification
- Run Rust verification from `rust/`: `cargo fmt`, `cargo clippy --workspace --all-targets -- -D warnings`, `cargo test --workspace`
- `src/` and `tests/` are both present; update both surfaces together when behavior changes.

## Repository shape
- `rust/` contains the Rust workspace and active CLI/runtime implementation.
- `src/` contains source files that should stay consistent with generated guidance and tests.
- `tests/` contains validation surfaces that should be reviewed alongside code changes.

## Working agreement
- Prefer small, reviewable changes and keep generated bootstrap files aligned with actual repo workflows.
- Keep shared defaults in `.claude.json`; reserve `.claude/settings.local.json` for machine-local overrides.
- Do not overwrite existing `CLAUDE.md` content automatically; update it intentionally when repo workflows change.

## If you are Opus: always use a sub-agent
If you are an Opus model, never investigate, debug, or fix things yourself in the main session. For every task — a bug, a change, an investigation, a deploy — write a clear brief and hand it to a sub-agent (or message one already working on it). The main session only coordinates: it dispatches, relays results, and asks for decisions. Working inline burns the budget. The only exception is a single trivial action whose cost is smaller than writing the brief. Keep to at most 3 sub-agents at once.
