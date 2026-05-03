# {{Skill Name}} Evaluation

Use this template to evaluate whether a skill triggers for the right requests,
avoids nearby unrelated work, follows user instructions, and guides the agent
toward reliable expected behavior.

This file stores both the evaluation shape and the latest reviewed result. It
is not a raw usage log. Update evidence and result sections only after an
explicit evaluation, reviewed usage summary, or promotion review.

## Target

- Skill: `{{skill-name}}`
- Current rank: `Unranked`
- Source version: `{{path, commit, or version}}`
- Evaluator: `{{name or agent}}`
- Date: `{{YYYY-MM-DD}}`

## Evaluation Cases

### Trigger Scenarios

List realistic requests that should use the skill.

| Scenario | User request | Expected behavior | Validation |
| --- | --- | --- | --- |
| Happy path | `{{request}}` | `{{expected behavior}}` | `{{check}}` |
| Edge case | `{{request}}` | `{{expected behavior}}` | `{{check}}` |

### Non-Trigger Scenarios

List nearby requests the skill should not handle.

| Scenario | User request | Expected routing |
| --- | --- | --- |
| Nearby task | `{{request}}` | `{{use another skill, ask a question, or proceed without this skill}}` |

### Instruction-Following Scenarios

List requests where success depends on obeying specific user constraints.

| Scenario | User instruction | Expected behavior | Validation |
| --- | --- | --- | --- |
| Explicit scope | `{{instruction}}` | `{{what the agent must do or avoid}}` | `{{check}}` |
| Output constraint | `{{instruction}}` | `{{required output shape}}` | `{{check}}` |

## Metrics

Use these lightweight metrics to judge each case. Do not expand this section
into a detailed rubric unless a separate rubric workflow asks for it.

| Metric | What to check | Pass signal |
| --- | --- | --- |
| Instruction Following | Did the agent follow explicit user instructions and avoid forbidden actions? | No missed instructions, no scope expansion, no ignored constraints. |
| Trigger Accuracy | Did the skill activate for requests it should handle? | Expected trigger scenarios use the skill. |
| Non-Trigger Avoidance | Did the skill avoid nearby unrelated work? | Non-trigger scenarios route elsewhere or proceed without this skill. |
| Task Completion | Did the final result satisfy the user's actual goal? | The agent reaches the requested outcome, not just a plausible explanation. |
| Workflow Adherence | Did the agent follow the skill's required process? | Required grounding, execution, validation, and reporting steps are present. |
| Context Use | Did the agent use available environment context accurately? | Decisions are grounded in files, tools, or stated assumptions. |
| Validation Quality | Did validation match the task risk? | Meaningful checks are run or skipped checks are explicitly reported. |
| Safety and Privacy | Did the agent avoid unsafe side effects and private data capture? | No raw transcripts, secrets, or unsafe automatic mutation. |

## Regression Cases

Capture cases that must keep working after future edits.

| Case | Input or setup | Expected result |
| --- | --- | --- |
| `{{case name}}` | `{{input or setup}}` | `{{expected result}}` |

## Evidence Notes

Store privacy-safe summaries only. Do not copy raw transcripts, secrets,
personal data, or private user content into this file.

- Evaluation source: `{{evaluation run, reviewed usage summary, or promotion review}}`
- Evidence source: `{{session summary, example, test run, or review}}`
- Durable observation: `{{what was learned}}`
- Follow-up needed: `{{yes/no and short note}}`

## Result

- Status: `Pass | Fail | Needs revision`
- Required fixes: `{{none or short list}}`
- Promotion signal: `{{none, weak, moderate, or strong}}`
- Next evaluation: `{{what to test next}}`
