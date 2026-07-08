# R253 Adoption Blueprint

## Product Principle

```text
Fields are assets.
Templates are views.
Skills are reusable operating packages.
```

## Layered Architecture

```text
materials layer
  -> field extraction layer
  -> field repository layer
  -> template orchestration layer
  -> teacher editing layer
  -> Agent Skill layer
```

## P0 Scope

P0 should not start with a broad AI workflow canvas.

P0 should build a stable, reviewable loop:

1. upload or import source material
2. extract known fields
3. show extracted values with source spans
4. teacher confirms, edits, rejects, or marks missing
5. generate one selected template view from confirmed fields
6. save field values and teacher edits
7. keep version record for field definitions and template slots

## P0 Field Families

Start with these field categories:

- meta fields
- course basics
- unit design
- learner analysis
- objective system
- key and difficult points
- teaching activities
- classroom language
- assessment and feedback

## P0 Template Views

Start with three template views:

- public lesson transcript
- daily teaching plan
- fast prep

Each template should be:

```text
field slots + display order + generation rules + constraints + output style
```

## P1 Scope

Add learning and governance:

- candidate field pool
- alias merge suggestions
- new field approval
- field deprecation
- school/region template library
- teacher personal template library
- Skill versioning and rollback

## P2 Scope

Add richer Agent Skill operations:

- skill package builder
- eval fixtures
- example cases
- reviewer dashboard
- field/template/skill dependency graph
- exportable Skill manifest

## Recommended Stage Order

1. `R254_PREP_FIELD_REPOSITORY_SCHEMA_AND_TEMPLATE_SLOT_CONTRACT`
2. `R255_PREP_FIELD_EXTRACTION_REVIEW_LOOP_CONTRACT`
3. `R256_TEMPLATE_ORCHESTRATION_AND_TEACHER_EDITING_SURFACE_CONTRACT`
4. `R257_AGENT_SKILL_PACKAGE_AND_VERSION_CONTRACT`

## First Engineering Decision

Do not implement open-ended field learning first.

Start with a controlled field repository and a teacher confirmation page. Let new fields be discovered as candidates, but require review before publishing.
