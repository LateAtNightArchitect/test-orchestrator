# CLAUDE.md

Guidance for Claude Code when working in this repository.

## What this project is

test-orchestrator is a framework for systems infrastructure testing. It
coordinates a pipeline of subprojects that together plan, provision, run,
record, and evaluate infrastructure tests.

## Repository structure

This top-level repo is the orchestrator itself (glue code, shared config,
docs). The subdirectories below are each meant to be their own standalone
Git repository, checked out as siblings inside this directory:

- `test-planner`
- `test-env-builder`
- `test-runner`
- `test-recorder`
- `test-evaluator`

These are listed in `.gitignore` and are **not** part of this repo's Git
history. Do not `git add` files inside them from this repo, and do not
expect `git status`/`git log` here to reflect their state — treat them as
external projects that happen to live on disk nearby. If a subproject
needs its own Git history, it should be initialized independently inside
its own directory.

## Working in this repo

- Changes to orchestration logic, shared docs, or top-level config belong
  in this repo.
- Changes inside a subproject directory belong to that subproject's own
  repo — if one doesn't exist yet, flag that to the user rather than
  assuming it should be tracked here.
