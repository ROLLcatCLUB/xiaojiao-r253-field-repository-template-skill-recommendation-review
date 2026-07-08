# R253 Agent Skill Contract Seed

## Principle

An Agent Skill is not just a prompt.

It should be:

```text
field set + template structure + generation strategy + validation rules + examples + version history
```

## Skill Manifest Shape

Minimum manifest:

```json
{
  "skill_id": "prep.public_lesson_transcript.v1",
  "skill_name": "公开课逐字稿生成",
  "version": "1.0.0",
  "field_set": [
    "course.subject",
    "course.grade",
    "unit.big_idea",
    "unit.essential_question",
    "learner.analysis",
    "activity.sequence",
    "teacher.prompt",
    "assessment.criteria"
  ],
  "template_id": "template.public_lesson_transcript.v1",
  "generation_strategy": "generate missing connective teaching language only after source-backed fields are confirmed",
  "validation_rules": [
    "required fields must be confirmed or teacher-filled",
    "generated activity sequence must preserve source-backed activity order when present",
    "teacher language must be editable before export",
    "source gaps must be visible"
  ],
  "examples": [],
  "status": "draft"
}
```

## Initial Skills

Recommended first five:

- `prep.field_extraction.v1`
- `prep.template_orchestration.v1`
- `prep.public_lesson_transcript.v1`
- `prep.daily_teaching_plan.v1`
- `prep.fast_prep.v1`

P1:

- `prep.field_upgrade_suggestion.v1`
- `prep.alias_merge_review.v1`
- `prep.teacher_style_adaptation.v1`

## Skill Review Gate

A Skill can become active only when:

- field dependencies exist and are active
- template exists and is active
- minimum examples pass
- validation rules are explicit
- teacher edit surface exists for generated output
- rollback target exists

## Runtime Boundary

Skills should call approved field/template contracts. They should not invent new system fields at runtime.

If the model discovers a new repeated structure, it should create:

```text
candidate field suggestion
```

not:

```text
active field mutation
```

## Relationship To 小教

This is the safest way to "接进来":

```text
external idea -> Xiaobei contract -> 小教 Skill -> review gate -> teacher-facing generation
```

Do not connect external projects directly as 小教 runtime modules.
