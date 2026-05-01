# skill-mastery

A harness for creating, evaluating, and leveling up AI agent skills.

## What is skill-mastery?

`skill-mastery` is an early-stage open-source project for treating AI agent skills as living artifacts.

A skill should not be a static prompt file that is written once and forgotten. It should improve as agents use it, as users correct it, and as evaluations reveal where it succeeds or fails.

The goal of `skill-mastery` is to help teams create skills, organize them in a catalog, learn from real usage, and promote the skills that become more useful, more reliable, and better tested over time.

## Why it matters

AI agent skills often fail silently. They can become outdated, overfit to one workflow, miss important edge cases, or rely on instructions that only make sense to their original author.

Most skill improvement still happens manually: someone notices a failure, edits an instruction, and hopes the change does not break another workflow.

`skill-mastery` aims to make that improvement loop explicit:

- capture what happened when a skill was used
- summarize feedback without storing raw private transcripts
- evaluate behavior with examples and rubrics
- generate structured improvement proposals
- promote skills only when they have evidence of reliability

## How it works

`skill-mastery` is designed around a simple loop:

1. Create skills from reusable templates.
2. Register skills in a catalog.
3. Capture privacy-safe summaries from real sessions.
4. Evaluate skills with examples, rubrics, and regression checks.
5. Generate improvement proposals or draft PRs.
6. Promote skills when they prove reliable.

By default, skills should not mutate themselves automatically. The first milestone is proposal-first improvement: collect evidence, suggest changes, and let a human review the update before it becomes part of the skill.

## Skill Mastery Ranks

Skills level up through evidence, not raw usage count.

The rank system is inspired by competitive ladder progression. A skill climbs when it becomes more useful, more reliable, and better tested.

| Rank | Meaning |
| --- | --- |
| Unranked | Newly created or imported; not evaluated yet. |
| Iron | Has basic structure but weak evidence, examples, or evaluation coverage. |
| Bronze | Usable for simple cases with clear instructions and basic examples. |
| Silver | Used in real sessions; early feedback has been captured. |
| Gold | Handles common cases reliably and passes core evaluations. |
| Platinum | Has a low correction rate and documented edge cases. |
| Emerald | Performs well across varied workflows and has accepted improvements. |
| Diamond | Stable, well-tested, and safe to reuse broadly. |
| Master | Trusted for high-value workflows with strong regression protection. |
| Grandmaster | Consistently reliable across agents, users, and contexts. |
| Challenger | Exemplary skill; promoted as a reference implementation. |
| Archived | Deprecated, superseded, or intentionally retired. |

Good promotion signals include:

- successful real sessions
- fewer user corrections
- passing evaluations
- accepted improvement proposals
- stable behavior across different contexts

## Improvement Loop

The improvement loop turns real usage into reviewed changes:

1. A skill is used in a session.
2. The session produces a privacy-safe summary.
3. The summary is linked to the skill version that was used.
4. Repeated issues, missing instructions, and successful patterns are extracted.
5. An improvement proposal is generated.
6. Evaluations and review gates decide whether the skill should change or rank up.

This creates a recursive improvement loop without letting noisy sessions directly rewrite trusted instructions.

## Safety Principles

`skill-mastery` is designed around conservative skill evolution:

- Store privacy-safe summaries, not raw session transcripts.
- Prefer proposals and draft PRs before modifying skill instructions.
- Require human review before promotion.
- Keep changes rollback-friendly.
- Evaluate before trusting a new version.
- Avoid ranking skills based only on popularity.

## Roadmap

This project is currently in the design and prototype stage.

Planned work:

- Define the base skill template.
- Define catalog metadata for skills, versions, ranks, owners, and risk levels.
- Define a privacy-safe session summary format.
- Define the improvement proposal format.
- Define evaluation gates and promotion rules.
- Support integrations with agent environments.
- Generate draft PRs for reviewed skill improvements.

## Status

`skill-mastery` is early-stage. The repository is currently being shaped around the core concepts, schemas, and improvement workflow before implementation is expanded.

Expect changes to the data model, rank criteria, and integration approach as the project evolves.

## Contributing

Contributions and design discussions are welcome, especially around:

- skill template design
- catalog schema
- evaluation strategy
- rank and promotion criteria
- privacy-safe session summaries
- improvement proposal workflows
- integrations with AI agent environments

The core question is simple: how do we help agent skills get better every time they are used?
