# GPT Review Prompt For R253

Please review this package as a product/architecture decision, not as source-code reuse.

## Context

We are designing a teacher prep system. The proposed direction is:

```text
prep field repository + template orchestration + Agent Skill generation
```

The goal is to stop treating lesson prep as fixed templates, and instead manage reusable structured teaching knowledge.

## Please Judge

1. Is the decision correct that none of the four teacher-prep reference systems fully implements this architecture?
2. Are the partial references assigned correctly?
   - Claw-ED: bundle/tool/skill surface
   - saniales: workflow and artifact handoff
   - classmin: activity alias/strategy registry and review/final chain
   - Divanshi: minimum intake form
3. Is the generic pattern stack reasonable?
   - JSON schema/form builder
   - content model governance
   - AI workflow/skill publication
4. Should Xiaobei build this as its own contract layer instead of adopting an external project?
5. Is the proposed next artifact correct?

```text
R254_PREP_FIELD_REPOSITORY_SCHEMA_AND_TEMPLATE_SLOT_CONTRACT
```

## Please Return

Use this structure:

```text
Decision:
Approve / Revise / Reject

Strongest reasons:
- ...

Risks:
- ...

Missing contracts:
- ...

Recommended next artifact:
- ...

Do-not-do list:
- ...
```

## Important Boundary

Do not recommend copying external code unless you can specify:

- exact source file
- license implication
- exact Xiaobei contract it satisfies
- exact rollback path
- how teacher review remains mandatory
