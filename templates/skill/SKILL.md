---
name: skill-name
description: "Use when Codex needs to [describe the task, workflow, file type, tool, or domain this skill supports]. Include concrete trigger scenarios, important boundaries, and any related tasks this skill should not handle."
---

# {{Skill Title}}

<!--
Replace placeholders before publishing the skill. Keep this file concise and
move detailed references, deterministic scripts, and reusable output assets into
resource folders only when the skill genuinely needs them.
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
- `assets/`: templates, images, fonts, boilerplate, or other files used in the
  final output.
- `agents/openai.yaml`: optional UI metadata after the skill behavior is clear.

Do not add placeholder resource folders or extra documentation files unless the
skill needs them.

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
