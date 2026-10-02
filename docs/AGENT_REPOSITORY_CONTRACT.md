# Agent Repository Contract — GTM Cheat Codes

**Status:** COMPONENT / AGENT KNOWLEDGE MODULE
**Domain:** GTM skills, workflows, schemas and approval-aware operating patterns.
**Boundary:** This module owns reusable GTM workflow knowledge and contracts. It does not own CRM source-of-truth data, payment processing, outbound credentials or portfolio deployment.

## Typed agent interface
Every skill should expose typed inputs, typed outputs and explicit side effects/approval requirements.

Recommended internal boundary:
- `domain/`: GTM workflow rules and decision logic.
- `agent/`: skill invocation contracts and adapters.
- `shared/`: schemas, validation, evidence/result envelopes.
- `tests/`: skill unit, fixture/integration and workflow tests.

Existing `skills/`, `automations/`, `registry/` and `templates/` remain authoritative during migration; do not duplicate them merely to satisfy directory naming.

## Auditability
Every workflow must identify its source context, requested action, approval state, resulting action and evidence reference.

## Safety
Human approval remains required for external messages, system-of-record writes and publishing unless a separate explicit policy grants authority.

## Verification
Validate schemas, fixtures and representative workflows before release.
