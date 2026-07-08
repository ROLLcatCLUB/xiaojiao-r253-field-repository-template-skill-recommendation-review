# R253 Field Repository + Template Orchestration + Agent Skill Recommendation

Stage ID: `1013R_R253_FIELD_REPOSITORY_TEMPLATE_SKILL_PATTERN_RECOMMENDATION`

This review package extracts the current recommendation for turning lesson preparation from fixed templates into a growing bottom-layer capability:

```text
prep field repository
template orchestration
Agent Skill generation
```

## Decision

The four teacher-prep reference systems do not fully implement this architecture. They provide useful partial patterns:

- Claw-ED: lesson bundle chain, teacher profile, tools/skills, custom YAML tool schema.
- saniales/ai-lesson-planner: course-to-lesson workflow and artifact scaffolding.
- classmin: teaching activity registry with aliases/strategies and review/final workflow.
- DivanshiJain2005/AI-lesson-planner: minimum input form and lightweight generation demo.

The complete direction should be Xiaobei-native: build our own field repository, use external systems only as pattern references, and borrow mature generic open-source ideas for schema-driven forms, content model governance, and AI workflow/skill packaging.

## What This Package Is For

Give GPT a small auditable package to review:

- Whether the recommended architecture is product-correct.
- Whether the proposed adoption order is safe.
- Whether any external project should be studied further.
- Whether the first implementation contract should be field repository, template slots, or Agent Skill packaging.

## Files

- `r253_executive_decision.md`
- `r253_four_reference_systems_check.md`
- `r253_github_pattern_landscape.md`
- `r253_adoption_blueprint.md`
- `r253_field_repository_contract_seed.md`
- `r253_agent_skill_contract_seed.md`
- `r253_non_adoption_guard.md`
- `GPT_REVIEW_PROMPT_R253.md`
- `r253_review_manifest.json`
- `validate_1013R_R253_field_repository_template_skill_pattern_recommendation_result.json`

## Boundary

R253 is docs-only and review-only.

It does not:

- install external projects
- copy external code
- change runtime routes
- change database schema
- modify the current lesson-generation chain
- replace R250/R251
- occupy the earlier R251 recommendation for `R252_TEACHER_EXECUTION_MAP_AND_CLASSROOM_TIMELINE_CONTRACT`

## Recommended Next Artifact

If GPT agrees with this direction, the next artifact should be:

```text
R254_PREP_FIELD_REPOSITORY_SCHEMA_AND_TEMPLATE_SLOT_CONTRACT
```

That should define `field_definition`, `field_alias`, `field_value`, `template_definition`, `template_field_slot`, review states, and the first three template views: public lesson transcript, daily teaching plan, and fast prep.
