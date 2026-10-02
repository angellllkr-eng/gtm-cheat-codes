# X31 Architecture Contract

**Responsibility:** GTM skills and workflow module

**Repository status:** CANONICAL CAPABILITY

## Domain boundary
Owns reusable GTM skills, workflow patterns, schemas, templates, and governance guidance. It does not own external CRM or messaging system state.

## Typed agent/operator contract
Skills expose explicit inputs, required context, approval requirements, external actions, and expected outputs. External writes require human approval and least-privilege credentials.

## Layer separation
Domain: GTM workflow logic. Interface: skill/workflow contracts and schemas. Shared: registry/templates/utilities. Tests: schema validation, workflow fixtures, and integration tests where external adapters exist.

## Auditability
Every workflow that can change a system of record must preserve source references, approval state, and an execution outcome.

## Repository rule
This contract standardizes the repository boundary without creating a duplicate implementation. Existing capability is reconciled in place when this repository is canonical; legacy/source-freeze repositories remain provenance sources until reusable material is migrated and verified in its canonical destination.

## X31 invariant
**Domain → Agent/Operator Interface → Shared → Tests → Audit/Evidence**

No secret material belongs in Git. No production claim is valid without runtime evidence from the canonical deployment authority.
