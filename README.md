# python-junie-config

This repository is for sharing and archiving configuration files, guidance, and best practices for JetBrains' Junie AI agent. This repo is intended to be cloned or referenced across projects so teams can reuse a consistent set of Junie guidelines and conventions.

## Purpose and Scope

- Centralize Junie configuration and guidance so it's easy to maintain and evolve in one place.
- Encourage consistent behaviors across projects (e.g., logging, the same coding style rules, and repeatable task workflows).
- Serve as a lightweight reference for new contributors who use Junie alongside Python development.

## Contents

- `.junie/` — Home for Junie-specific materials used by this repository.
  - `intermediate_files/` — The place for Junie to store the files it generates that are not relate to the project
  - `logs/` — The place for Junie to store task logs
  - `guidelines.md` — Project guidelines Junie should follow when assisting on tasks (conduct, logging, Python styleguide pointers, and workflow expectations).
- `LICENSE` — License for this repository.
- `README` — The README (this file) for this repository.

> Note: Some teams keep a copy of this repository (or just the `.junie` folder) in their project roots so Junie always sees the same playbook regardless of codebase.

## Usage

- Option A (recommended): Copy the `.junie/` directory from this repository into the root of your target project.
- Option B: Add this repository as a Git submodule or include it with your project templates/scaffolding.
- Option C: Keep this repository separate and reference it during tasks; just ensure Junie has access to the `.junie/guidelines.md` file and related materials.

## Tips 

The core guidance lives in `.junie/guidelines.md`. Here are practical tips for applying it day‑to‑day:

1. Create a task log for every Junie-assisted task
   - Location: `.junie/logs/`
   - File name: `YYYY-MM-DD_HH-mm_<short-task-title>.txt`
   - Content: date, time, and a short list of steps you (and Junie) took. Keep it concise but actionable.
2. Keep ephemeral notes separate
   - If a task needs scratch notes, use `.junie/intermediate_files/<task-name>/` so the main codebase stays clean.
3. Always follow the Python styleguide referenced by the guidelines
   - The guidelines point to a `docs/python-styleguide/` set (e.g., `syntax.md`, `semantics.md`, `code_file_layout.md`, etc.).
   - If a file-specific rule conflicts with a general rule, the file-specific guidance wins.
4. Prefer consistency over novelty
   - When you’re unsure, mirror existing patterns in this repo and in the target project.
5. Don’t commit automation artifacts by default
   - The guidelines ask not to commit anything automatically. Make intentional commits after review.

    
## Updating the guidelines

- Propose edits in `.junie/guidelines.md` and discuss changes with the team before rolling them out to other projects.
- When you change a rule, consider adding a brief rationale and an example to ease adoption.

## Links

- JetBrains AI Assistant (Junie) documentation hub: https://www.jetbrains.com/help/ai/

## License

This repository is distributed under the license found in `LICENSE`.
