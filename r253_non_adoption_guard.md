# R253 Non-Adoption Guard

## Do Not Adopt Directly

Do not copy or install external projects into the main chain for this stage.

Do not adopt:

- Claw-ED runtime
- saniales scripts or agents
- classmin CrewAI runtime
- Divanshi Streamlit app
- generic CMS/admin systems as the actual Xiaobei backend
- generic workflow builders as the actual 小教 runtime

## Why

The target is not a new external module. The target is a Xiaobei-native contract layer.

Direct adoption would create risks:

- field IDs would not match our lesson contracts
- template semantics would drift
- licensing and dependency boundaries would become messy
- teacher review gates could be bypassed
- main chain would inherit unrelated runtime assumptions

## Allowed Use

Allowed:

- contract borrowing
- naming reference
- product-flow reference
- schema shape inspiration
- isolated future prototypes

Not allowed:

- code copy
- dependency install
- runtime connection
- database migration
- provider calls
- hidden background automation

## Review Question For GPT

If GPT recommends adopting an external project, it must answer:

1. Which exact contract does it satisfy?
2. Which current Xiaobei route or data model does it touch?
3. What is the rollback path?
4. What license or dependency risk exists?
5. How does teacher review remain mandatory?

If those cannot be answered, the recommendation should be rejected.
