# R253 Field Repository Contract Seed

## Purpose

Define the minimum durable data model for a growing prep field repository.

## Table: `field_definition`

Required fields:

- `id`
- `field_id`
- `cn_label`
- `category`
- `level`
- `data_type`
- `description`
- `editable`
- `required_default`
- `status`
- `version`
- `created_by`
- `updated_at`

Allowed `status` values:

- `candidate`
- `active`
- `deprecated`
- `rejected`
- `merged`

Examples:

- `unit.big_idea`
- `unit.essential_question`
- `learner.analysis`
- `activity.design_intent`
- `teacher.prompt`
- `assessment.criteria`

## Table: `field_alias`

Required fields:

- `id`
- `field_id`
- `alias`
- `language`
- `source`
- `confidence`
- `status`

Examples:

```text
learner.analysis -> 学情分析
learner.analysis -> 学生情况分析
unit.essential_question -> 基本问题
unit.essential_question -> 驱动问题
```

## Table: `field_value`

Required fields:

- `id`
- `document_id`
- `field_id`
- `value_json`
- `source_span`
- `confidence`
- `review_status`
- `edited_by_teacher`
- `created_at`
- `updated_at`

Allowed `review_status` values:

- `extracted`
- `confirmed`
- `edited`
- `rejected`
- `missing`

## Table: `template_definition`

Required fields:

- `id`
- `template_id`
- `template_name`
- `lesson_type`
- `description`
- `version`
- `status`

Allowed `status` values:

- `draft`
- `active`
- `deprecated`

## Table: `template_field_slot`

Required fields:

- `id`
- `template_id`
- `field_id`
- `slot_group`
- `display_order`
- `required`
- `teacher_editable`
- `generation_rule`
- `validation_rule`

## Field Candidate Publication Rule

The system may suggest new fields, but may not publish them automatically.

Publication requires:

1. no duplicate active field
2. alias merge check completed
3. example source spans attached
4. reviewer approval
5. version increment
6. template impact check

## Minimal Field Extraction Output

Every extraction result should include:

```json
{
  "field_id": "unit.big_idea",
  "cn_label": "大观念",
  "value": "...",
  "source_span": "...",
  "confidence": 0.82,
  "review_status": "extracted"
}
```

## Non-Negotiable Boundary

System field IDs must stay stable. Chinese labels may vary by teacher, school, or region.
