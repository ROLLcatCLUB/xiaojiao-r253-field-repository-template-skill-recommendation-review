# R253 GitHub Pattern Landscape

## Current Search Judgment

As of 2026-07-08, open-source education/lesson-prep projects on GitHub appear to focus on:

- AI lesson generation
- lesson bundle generation
- course/lesson artifact workflow
- slides/PPT script generation
- classroom simulation

They do not commonly expose a full "field repository + template slot orchestration + Agent Skill generation" architecture.

## Education / Lesson Planning Candidates

### Claw-ED

URL: <https://github.com/SirhanMacx/Claw-ED>

Use as:

- lesson bundle reference
- tool/skill reference
- approval gate reference

Do not use as:

- field repository implementation
- direct runtime dependency

### saniales/ai-lesson-planner

URL: <https://github.com/saniales/ai-lesson-planner>

Use as:

- workflow split reference
- artifact folder reference
- course metadata boundary reference

Do not use as:

- field warehouse
- code source for the main chain

### sususng/classmin

URL: <https://github.com/sususng/classmin>

Use as:

- activity alias/strategy registry reference
- review/final workflow reference
- classroom timeline reference

Do not use as:

- main runtime
- general field governance source

### DivanshiJain2005/AI-lesson-planner

URL: <https://github.com/DivanshiJain2005/AI-lesson-planner>

Use as:

- minimum input form reference

Do not use as:

- architecture reference

## Generic Open-Source Pattern Sources

### Schema-driven form rendering

- `rjsf-team/react-jsonschema-form`: <https://github.com/rjsf-team/react-jsonschema-form>
- `formio/formio.js`: <https://github.com/formio/formio.js>

Pattern to borrow:

```text
field/schema definition -> generated editable UI -> validation
```

Why relevant:

The teacher editing layer should not be hard-coded per template. It should render from field metadata and template slots.

### Content model and field governance

- `strapi/strapi`: <https://github.com/strapi/strapi>
- `directus/directus`: <https://github.com/directus/directus>
- `payloadcms/payload`: <https://github.com/payloadcms/payload>

Pattern to borrow:

```text
content type / field model -> visual admin -> permissions -> draft/publish or review states -> generated APIs
```

Why relevant:

Xiaobei's field repository needs stable field IDs, labels, data types, required flags, versioning, candidate states, and governance before fields can be used in official templates or Skills.

### AI workflow and Agent orchestration

- `langgenius/dify`: <https://github.com/langgenius/dify>
- `FlowiseAI/Flowise`: <https://github.com/FlowiseAI/Flowise>
- `langflow-ai/langflow`: <https://github.com/langflow-ai/langflow>
- `n8n-io/n8n`: <https://github.com/n8n-io/n8n>

Pattern to borrow:

```text
node/workflow canvas -> testable flow -> API/tool publication -> observable versioned execution
```

Why relevant:

Agent Skills should not be loose prompts. They should be packages with fields, strategy, validators, examples, and versions.

### Reusable Agent Skill packaging

- `FrancyJGLisboa/agent-skill-creator`: <https://github.com/FrancyJGLisboa/agent-skill-creator>
- `VoltAgent/awesome-agent-skills`: <https://github.com/VoltAgent/awesome-agent-skills>

Pattern to borrow:

```text
workflow knowledge -> reusable Skill package -> validations/evals -> installable agent capability
```

Why relevant:

The final layer can turn stable prep capabilities into repeatable "小教 Skills", but only after field and template contracts are stable.

## Pattern Combination

Recommended synthesis:

```text
classmin activity registry
  + JSON Schema/Form.io style editable fields
  + Strapi/Directus style field governance
  + Dify/Langflow style workflow publication
  + skill package validation
  = Xiaobei-native prep capability substrate
```
