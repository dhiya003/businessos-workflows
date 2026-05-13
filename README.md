# BusinessOS Workflow Governance

## Purpose

This repository contains governed workflow exports for the BusinessOS operational platform.

The repository provides:
- workflow version governance
- rollback safety
- operational lineage
- workflow release discipline
- stable vs experimental separation

---

# Workflow Lifecycle States

## shared

Stable production-approved workflows.

Requirements:
- validated end-to-end
- database verified
- dashboard verified
- rollback tested
- operationally stable

These workflows are considered production-safe.

Examples:
- shared-webhook-intake-v1
- shared-workflow-error-handler-v1

---

## experimental

Workflows under active development or testing.

These workflows:
- may fail
- may contain incomplete logic
- are not considered production-safe

Experimental workflows must NEVER directly replace stable workflows.

Examples:
- experimental-webhook-intake-v2
- experimental-ai-routing-v1

---

## archived

Deprecated or historical workflow versions retained for:
- rollback
- operational history
- recovery
- lineage tracking

Archived workflows should remain immutable.

Examples:
- shared-webhook-intake-v1-old
- experimental-routing-v0

---

# Workflow Naming Standard

Format:

<domain>-<module>-<purpose>-v<version>

Examples:
- shared-webhook-intake-v1
- shared-workflow-error-handler-v1
- experimental-ai-routing-v2

---

# Workflow Promotion Policy

Experimental workflows may only be promoted to shared after:

- successful workflow execution testing
- successful database validation
- successful dashboard validation
- successful rollback validation
- operational review completion

Promotion must create a NEW workflow version.

Example:
- shared-webhook-intake-v1
→
- shared-webhook-intake-v2

Never overwrite stable workflow history.

---

# Rollback Policy

Previous stable workflow versions must always remain recoverable.

Never delete previous stable workflow exports.

Stable workflow exports must remain versioned and immutable.

---

# Repository Structure

businessos-workflows/
│
├── shared/
├── experimental/
└── archived/

---

# Operational Governance Principles

- workflows are infrastructure assets
- workflow history must remain traceable
- stable workflows must remain reproducible
- operational rollback must always be possible
- experimental workflows must remain isolated from production

---

# Current Stable Workflows

- shared-webhook-intake-v1
- shared-workflow-error-handler-v1
- shared-lead-intake-reliability-v1