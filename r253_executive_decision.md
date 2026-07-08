# R253 Executive Decision

## Core Judgment

The proposed direction is valid and should become a bottom-layer capability of the prep system:

```text
materials -> field extraction -> field repository -> template orchestration -> teacher editing -> Agent Skill publication
```

This should not be treated as a better prompt or a new fixed lesson template. The durable product object is the field repository. Templates are views over field assets. Agent Skills are versioned operating packages built from stable field sets, template structures, generation policies, validation rules, examples, and change records.

## Answer To The User Question

Do the four downloaded systems already do this?

No. None of them fully implements:

- reviewed field definitions
- field aliases
- source-span backed extracted field values
- candidate field discovery
- human review before publishing new fields
- template slots bound to reusable fields
- Agent Skill versions generated from approved field/template contracts

What they provide are partial references:

- Claw-ED shows a broad lesson bundle/tool/skill surface.
- saniales shows a clean course-to-lesson artifact workflow.
- classmin shows the strongest local hint for field-like teaching activity assets.
- Divanshi shows the minimum form-input baseline.

## Answer To The GitHub Question

Current open-source education/lesson-planning projects mostly stop at generator, workflow, or artifact-chain level. The more mature architectural pieces are found in generic open-source systems:

- schema-driven forms: `react-jsonschema-form`, `formio/formio.js`
- content model and field governance: `strapi/strapi`, `directus/directus`, `payloadcms/payload`
- AI workflow and Agent packaging: `langgenius/dify`, `FlowiseAI/Flowise`, `langflow-ai/langflow`
- reusable agent skill packaging: `FrancyJGLisboa/agent-skill-creator`, `VoltAgent/awesome-agent-skills`

## Recommended Position

Build Xiaobei's own education-specific field repository.

Borrow patterns, not code:

```text
classmin activity registry
  + JSON Schema/Form.io style field editor
  + Strapi/Directus style content model governance
  + Dify/Langflow style workflow/skill publication
  = Xiaobei-native prep field repository and Skill layer
```

## Safe Adoption Level

Use this package as a contract seed only:

- `contract_only`: field repository metadata, review states, template slot rules
- `naming_reference`: activity alias, skill, workflow, bundle, review/final
- `future_design`: visual field editor, workflow canvas, skill marketplace

No direct runtime adoption is recommended.
