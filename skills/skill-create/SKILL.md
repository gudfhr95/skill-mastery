---
name: skill-create
description: Use when the user wants to design, create, scaffold, review, or improve an AI agent skill, including repo-local skills, Codex skills, skill templates, trigger descriptions, bundled resources, agents/openai.yaml metadata, evaluation starting points, validation plans, and reviewed skill improvement planning. Do not use for ordinary git commits, pull request creation, detailed rubric authoring, full improvement proposal writing, or unrelated repository documentation work.
---

# Skill Create

## Purpose

Design and scaffold AI agent skills as reviewed, evidence-ready artifacts.

Use this skill to turn concrete examples, workflow needs, and improvement
ideas into concise skill instructions. Treat every newly created skill as
Unranked until examples, evaluations, or accepted improvements support
promotion.

## Principles

- Start from concrete user requests and trigger phrases.
- Keep `SKILL.md` lean; move detailed material into resource folders only when
  the skill needs it.
- Use this skill's `templates/skill-template.md` as the canonical starter
  template when creating a new skill file.
- Use this skill's `templates/evaluation-template.md` when a new or revised
  skill needs an evaluation starting point.
- Do not create or modify files unless the user explicitly asks for creation,
  scaffolding, implementation, or an update.
- Store privacy-safe summaries, durable decisions, and reviewed evidence, not
  raw transcripts.
- Prefer improvement proposals or pull requests before changing trusted skill
  instructions.
- Leave detailed rubric design and improvement proposal authoring to separate
  skills or workflows.

## Workflow

1. Ground the request in the environment. In this repository, read `README.md`,
   `docs/INDEX.md`, existing nearby skills, and this skill's
   `templates/skill-template.md` before substantial skill work.
2. Gather the minimum missing intent: skill purpose, target workflow, trigger
   examples, target location, needed resources, and whether file creation is
   explicitly requested.
3. Design the skill boundary: name, description trigger, non-goals, workflow,
   resources, invocation policy, validation checks, evaluation starting point,
   success criteria, and improvement loop.
4. If the user asked only for advice or a plan, stop at a proposal and do not
   edit files.
5. If the user explicitly asked for implementation, create the skill folder,
   copy this skill's `templates/skill-template.md` into the new skill as
   `SKILL.md`, replace template markers, and add `agents/openai.yaml` when
   Codex metadata is useful.
6. When creating an evaluation-ready skill, copy
   `templates/evaluation-template.md` into the target evaluation location when
   one exists. If no evaluation location exists yet, include the filled
   evaluation starting point in the final response instead of inventing a new
   repo structure.
7. Add `scripts/`, `references/`, `assets/`, or additional `templates/` only
   when they directly improve repeatability or output quality.
8. Validate the result with checks that match the change: frontmatter shape,
   naming rules, stale template markers, metadata consistency, resource
   relevance, and any available repo validation command.
9. Report the created or changed files, validation performed, skipped checks,
   and any assumptions that should be reviewed.

## Naming and Metadata

- Use lowercase letters, digits, and hyphens for skill names.
- Prefer short, verb-led names that describe the action, such as
  `skill-create` or `gh-create-pr`.
- Make the folder name exactly match the `name` frontmatter value.
- Write the `description` as the trigger surface: include what the skill does,
  when it should be used, and important boundaries.
- For `agents/openai.yaml`, provide `display_name`, `short_description`,
  `default_prompt`, and an invocation policy that matches the skill's risk.

## Resources

- `templates/skill-template.md`: canonical starter template for new skill
  `SKILL.md` files. In the repository, this lives at
  `skills/skill-create/templates/skill-template.md`.
- `templates/evaluation-template.md`: starter evaluation template for trigger
  scenarios, non-trigger scenarios, instruction-following scenarios,
  lightweight metrics, regressions, privacy-safe evidence notes, pass/fail
  results, and promotion signals.
- `agents/openai.yaml`: Codex invocation metadata for this skill.

Do not add README files, changelogs, installation guides, or placeholder
resource folders inside a skill unless they are directly needed for the skill's
behavior.
