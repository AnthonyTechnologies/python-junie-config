# Guidelines

## Conduct

You are an expert in Python. You write secure, maintainable, and performant code.

## General

1. Create a log of this task.
2. Do not commit anything.
3. Ensure to follow the other guidelines and style guides in files mentioned in this guideline file.
4. If intermediary files are created, put them in .junie/intermediate_files/[name of task].
5. If the task requires tracking a lot of information, keep notes for yourself in the intermediary files.

## Security

- Never store or echo secrets, tokens, or credentials. Use placeholders like ${ENV_VAR} in examples.

## Logs

- File location: `.junie\logs`.
- Filename format: ``YYYY-MM-DD_HH-mm-ss_Timezone__<task-title-sanitized>.txt``.
  - Example: ``2025-11-20_14-24-00_UTC__Assess-guidelines-for-Junie-AI.txt``
- Timezone: ``UTC`` for timestamps within the file and filename unless the task explicitly requires a local timezone. Include the local time in parentheses on first line if relevant.
- Required header fields (first lines of the log):
  - ``Task Title``
  - ``Task ID`` (if available; else ``N/A``)
  - ``Started`` and ``Ended`` (ISO 8601, UTC)
  - ``Agent`` (name/version), ``Environment`` (OS, Python version)
  - ``Inputs`` (files/branches considered; redact secrets)
  - ``Output Artifacts`` (created files/paths)
- Steps section: append-only bullet list with timestamps for each action/decision.
- Redaction: never include secrets, access tokens, private keys, credentials, or raw PII. Write ``[REDACTED]`` and note category.
- Read-only mode: if file creation is prohibited, create an in-memory or response-embedded “virtual log” section and include a note: ``Log creation skipped due to read-only constraints``. If later allowed, backfill the log to `.junie\logs` with the same filename format and an ``ImportedFrom`` pointer.
- If required directories don’t exist, create them if permitted; otherwise, log the limitation and propose a remediation step.
- On tool errors, record the error message, attempted command (sanitized), and next action.


### Example Log
```
Task Title: Assess guidelines for the Junie AI Coding Agent
Task ID: N/A
Agent: Junie gpt-5-2025-08-07
Environment: Windows 11; Python 3.12
Started: 2025-11-20T14:24:00Z
Ended: 2025-11-20T14:40:00Z
Inputs: .junie\guidelines.md; docs\python-styleguide\style_guide.toml
Output Artifacts: [none]

Steps:
- 14:24: Fetched and read .junie\guidelines.md (22 lines), noted logging and style guide pointers.
- 14:30: Identified gaps (logging specifics, conflict resolution, enforcement, security).
- 14:35: Drafted concrete policy language and checklist.
- 14:40: Delivered recommendations and example log skeleton.

Notes:
- Read-only session; no files created. Redactions: N/A.
```

## Intermediate Files

- Directory: `.junie\intermediate_files\<task-title-sanitized>\<file>`
- Contents may include scratch notes and extracted snippets. Do not store secrets or license-restricted data.
- Include a ``README.txt`` summarizing file purposes when the folder has more than 3 files.

## Python Development

The [`Python Style Guide`](../docs/python-styleguide) describes in detail the guidelines of how you should write python
code for this project. [`style_guide.toml`](../docs/python-styleguide/style_guide.toml) is the entry point you should
use to understand the style guide.

When conflicts arise, the project tool configurations take precedence over the style guide.
