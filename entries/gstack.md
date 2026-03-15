# GStack

## Overview
- **Source**: https://github.com/garrytan/gstack
- **Found on**: X / GitHub
- **Found via**: Garry Tan (Y Combinator President & CEO)
- **Date added**: 2026-03-15
- **Status**: `new`

## What it does
GStack is a collection of 8 specialized workflow skills for Claude Code that transform it from a generic AI assistant into a team of domain-specific experts. Each skill emulates a different professional role — founder strategist, engineering manager, paranoid code reviewer, release engineer, QA tester, and more. You shift between "gears" depending on the task: `/plan-ceo-review` for first-principles product thinking, `/review` for production-grade bug hunting, `/ship` for atomic releases, `/browse` for visual QA with a real browser, and `/retro` for team retrospectives with per-contributor metrics.

## Why I saved this
It gives Claude Code different "hats" — each skill is a specialised expert mode instead of one generic assistant. Instead of prompting Claude to "act like a code reviewer," you get a purpose-built review skill that knows exactly what to look for. It's a framework for people who build apps and want to ship — it turns Claude Code into a team of specialists rather than one generalist.

## Key features
- `/plan-ceo-review` — Founder mode: rethinks problems from first principles, looks for the "10-star product" hidden in feature requests
- `/plan-eng-review` — Tech lead mode: architecture, data flow, state machines, edge cases, failure modes, test matrices
- `/review` — Paranoid staff engineer: catches race conditions, trust boundary issues, N+1 queries, orphaned resources
- `/ship` — Release engineer: sync, test, changelog, PR creation as one atomic operation
- `/browse` — QA with real browser: Playwright-powered Chromium, screenshots, form filling, console inspection
- `/qa` — Systematic QA: diff-aware (auto on feature branches), full exploration, smoke tests, regression testing
- `/setup-browser-cookies` — Imports cookies from Chrome/Arc/Brave/Edge into headless sessions
- `/retro` — Engineering manager: commit history analysis, shipping velocity, per-contributor feedback

## Use cases for me
- Level up Claude Code workflows with specialized "expert modes" instead of generic prompting
- Use `/review` before shipping to catch production bugs that basic testing misses
- Use `/browse` and `/qa` for visual testing of web projects
- Use `/plan-ceo-review` for product thinking on new project ideas
- Use `/ship` to standardize the release process across projects

## Technical details
- **Language/Stack**: TypeScript/JavaScript, Bun runtime
- **Requirements**: Claude Code, Git, Bun v1.0+, Playwright (for /browse)
- **Complexity**: `medium`
- **License**: MIT (inferred)

## How to get started
```bash
# Global install (recommended)
git clone https://github.com/garrytan/gstack.git ~/.claude/skills/gstack
cd ~/.claude/skills/gstack && ./setup

# This installs skill files + symlinks for slash commands
# /browse compiles a native binary (~58MB)
```

After install, skills are available as slash commands in Claude Code: `/plan-ceo-review`, `/review`, `/ship`, `/browse`, `/qa`, `/retro`, etc.

## Tags
`claude-code` `ai-agents` `developer-tools` `code-review` `qa-testing` `workflow` `productivity`

## Notes
- Works with parallel Claude Code sessions (Conductor) — each gets isolated workspaces and browser instances
- Browser sessions auto-shutdown after 30 min idle
- `/qa` is diff-aware: reads `git diff main` to auto-identify affected pages
- Has Greptile integration for automated code review
- Can auto-upgrade via `/gstack-upgrade` or `auto_upgrade: true` in `~/.gstack/config.yaml`
- Built by Garry Tan — this is how the YC CEO actually ships software with Claude Code
