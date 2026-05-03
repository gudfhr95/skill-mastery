---
name: git-commit
description: Use when the user explicitly asks to create a git commit from current repository changes. Do not use for general git status, diff review, push, or PR creation.
---

# Git Commit

## Purpose

Create one reviewed git commit from the intended repository changes.

Commits change repository history, so use this workflow only when the user asks
for a commit.

## Workflow

1. Inspect `git status --short` and the relevant diff.
2. Identify which changes belong to the requested commit.
3. Run appropriate validation for the changed files when practical.
4. Stage only the intended files.
5. Commit with a concise message that explains the user-facing change.
6. Report the commit hash and any validation that was or was not run.

## Resources

- `agents/openai.yaml`: configures Codex invocation policy for this skill.

Do not add scripts, references, or assets unless the commit workflow needs a
repeatable helper.

## Success Criteria

- Only intended files are staged.
- Unrelated user changes are left untouched.
- Validation is run when practical, or the skipped validation is reported.
- The commit message is concise and describes the committed change.
- The final response includes the commit hash and any remaining uncommitted
  changes.

## Improvement

- Keep the workflow conservative around staging and history changes.
- Do not rewrite history, amend, reset, or force-push unless the user explicitly
  asks.
- Capture privacy-safe lessons from real use, not raw transcripts.
