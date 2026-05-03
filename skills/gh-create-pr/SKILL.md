---
name: gh-create-pr
description: Use when the user explicitly asks to create or open a GitHub pull request for the current repository branch after commits already exist. Do not use for staging, committing, pushing unpublished branches, PR review comments, CI debugging, or general GitHub triage.
---

# GitHub Create PR

## Purpose

Create one GitHub pull request from the current repository branch.

Pull requests publish branch state to GitHub, so use this workflow only when the
user asks to create or open a PR. This skill assumes the branch already contains
the intended commits and does not stage, commit, or push changes.

## Workflow

1. Inspect local context with `git status -sb`, `git branch --show-current`,
   `git remote -v`, `gh --version`, and `gh auth status`.
2. Use `origin` when it exists. If multiple GitHub remotes exist and there is no
   clear default, ask which remote to use.
3. Resolve the base branch from the user request. If the user did not specify a
   base, use the GitHub default branch.
4. Stop before creating a PR when:
   - the current branch is missing, detached, or the same as the base branch
   - the branch has no commits ahead of the base branch
   - GitHub CLI is missing or not authenticated
   - the branch has not already been published to the selected remote
5. If uncommitted changes exist, state that they are excluded from the PR and ask
   before continuing.
6. Check whether an open PR already exists for the current branch and avoid
   creating a duplicate.
7. Generate a concise title and body from the user's requested title/body when
   provided. Otherwise derive them from `git log` and `git diff --stat`.
8. Create a draft PR by default:
   `gh pr create --draft --base <base> --head <branch> --title <title> --body-file <tmp>`.
   Omit `--draft` only when the user explicitly asks for a ready-for-review PR.
9. Report the PR URL, base branch, head branch, draft or ready state, title, and
   validation performed.

## Resources

- `agents/openai.yaml`: configures Codex invocation metadata for this skill.

Do not add scripts, references, or assets unless PR creation needs a repeatable
helper.

## Success Criteria

- The skill only creates a PR for the current branch after commits already exist.
- The base and head branches are explicit before PR creation.
- Duplicate PRs are not created for branches that already have an open PR.
- Draft PRs are the default unless the user explicitly asks for ready review.
- Uncommitted local changes are not silently included or implied to be included.
- The final response includes the PR URL, branch target, PR state, and validation.

## Improvement

- Keep the workflow conservative around publishing and repository state.
- Do not stage, commit, push, force-push, or rewrite history from this skill.
- Capture privacy-safe lessons from real use, not raw transcripts.
