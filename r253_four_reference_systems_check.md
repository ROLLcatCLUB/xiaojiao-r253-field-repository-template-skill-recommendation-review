# R253 Four Reference Systems Check

## Evaluation Criteria

A system counts as matching the proposed architecture only if it has most of these:

- field definitions with stable IDs
- Chinese/user-facing labels separated from system IDs
- field categories and levels
- field aliases
- extracted field values with source spans and confidence
- review status for extracted values and candidate fields
- template definitions made of field slots
- teacher editing loop feeding back into fields/templates
- Skill packages built from field sets, template structures, strategies, validators, examples, and versions

## Claw-ED

Repository: <https://github.com/SirhanMacx/Claw-ED>

Observed strengths:

- complete lesson bundle direction
- teacher profile and local-first teaching voice
- many agent tools
- custom YAML prompt tools with `name`, `description`, `parameters`, and `prompt_template`
- prompt version and quality tracking ideas
- teacher approval/autonomy gates

Match level: partial.

Why it does not fully match:

- tool parameters are not a reusable prep field warehouse
- no `field_definition` / `field_alias` / `field_value` layer
- no candidate field discovery and human field-publishing workflow
- templates remain prompt/tool/artifact oriented rather than field-slot oriented

Recommended use:

- Reference the tool/skill package shape.
- Reference bundle and teacher approval ideas.
- Do not copy code or make it a runtime dependency.

## saniales/ai-lesson-planner

Repository: <https://github.com/saniales/ai-lesson-planner>

Observed strengths:

- course planner -> discussion/highlights -> lesson planner -> slides maker
- `.lesson-config.json` and course metadata boundary
- lesson folder and artifact scaffolding
- explicit rule that templates are structure baselines, not fixed section counts

Match level: partial.

Why it does not fully match:

- `.lesson-config.json` is course metadata, not a growing field repository
- no field alias or source-span extraction layer
- no field review/publish workflow
- no Skill version contract based on approved fields

Recommended use:

- Reference workflow decomposition and artifact handoff.
- Reference the idea that templates should not force fixed counts.
- Keep GPL surface as design-only unless legal review says otherwise.

## sususng/classmin

Repository: <https://github.com/sususng/classmin>

Observed strengths:

- Chinese classroom/lesson-prep orientation
- drafts -> reviews -> final workflow
- teaching activity definitions with aliases and strategies
- teaching stage to activity mapping
- classroom timeline output
- peer/academic/content review agents

Match level: strongest partial match among the four.

Why it does not fully match:

- activity definitions are field-like, but scoped to classroom actions
- no general prep field repository covering unit, objectives, learner analysis, assessment, resources, classroom language, etc.
- no reviewed candidate-field lifecycle
- no template slot table that binds views to reusable field IDs

Recommended use:

- Reference `activity type + alias + strategy` as the seed for Xiaobei's activity/teacher-language field family.
- Reference review/final workflow.
- Do not connect classmin runtime into the main chain.

## DivanshiJain2005/AI-lesson-planner

Repository: <https://github.com/DivanshiJain2005/AI-lesson-planner>

Observed strengths:

- simple input form
- useful minimum fields: title, subject, grade, duration, supporting materials
- clear demo of "few fields -> lesson plan output"

Match level: low.

Why it does not fully match:

- fixed form fields only
- no field repository
- no template orchestration
- no teacher review loop
- no field learning or Skill publication

Recommended use:

- Reference as the minimum intake baseline only.
- Do not use as architecture reference beyond input simplicity.

## Summary

None of the four systems fully does the proposed architecture. The most useful pieces are:

```text
Claw-ED: skill/tool/package surface
saniales: workflow decomposition
classmin: activity alias/strategy registry and review/final chain
Divanshi: minimum form intake
```
