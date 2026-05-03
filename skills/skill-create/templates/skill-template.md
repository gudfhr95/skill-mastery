---
name: skill-name
description: "Use when an agent needs to [describe the task, workflow, file type, tool, or domain this skill supports]. Include concrete trigger scenarios, important boundaries, and nearby tasks this skill should not handle."
# disable-model-invocation: true
---

# {{Skill Title}}

<!--
Replace placeholders before publishing the skill. Keep this file concise and
move detailed references, deterministic scripts, reusable templates, and output
assets into resource folders only when the skill genuinely needs them.
-->

## Purpose

State what this skill helps an agent do and why the workflow deserves a
dedicated skill.

## Workflow

1. Gather the minimum context, files, inputs, or user decisions needed for the
   task.
2. Select the procedure, tool, reference, or asset that fits the current request.
3. Perform the work using the target environment's existing patterns.
4. Validate the result with checks that match the task's risk.
5. Report the outcome, evidence, and any remaining limitations.

## Resources

Add resource folders only when they directly improve repeatability:

- `scripts/`: deterministic helpers for fragile or repeated operations.
- `references/`: detailed domain, API, schema, or workflow material that should
  be loaded only when needed.
- `templates/`: reusable text, code, or file skeletons used to create outputs.
- `assets/`: images, fonts, binary templates, or other files used in final
  outputs.
- `agents/openai.yaml`: optional Codex metadata after the skill behavior is
  clear.

Do not add placeholder resource folders or extra documentation files unless the
skill needs them.

## Invocation Policy

For side-effectful skills that should only run after explicit user invocation:

- Add `disable-model-invocation: true` to `SKILL.md` frontmatter for Claude
  Code.
- Add `policy.allow_implicit_invocation: false` to `agents/openai.yaml` for
  Codex.

Omit these settings for skills that are safe to trigger automatically.

## Success Criteria

- The skill triggers for the right user requests and avoids nearby unrelated
  work.
- The workflow produces outputs that match the user's goal and the environment's
  conventions.
- The validation steps catch the most likely failure modes.
- Realistic examples or evaluations can show when the skill passes or needs
  revision.

## Improvement

- Capture privacy-safe summaries, durable decisions, and reviewed evidence from
  real use.
- Do not store raw transcripts in the skill.
- Prefer improvement proposals or pull requests before changing trusted skill
  instructions.
- Promote the skill only when examples, evaluations, or accepted improvements
  support the change.
