# LogMedic

> Portable agent for identifying projects where recognizable application logs are missing.

## What it does

LogMedic inspects project files for recognizable logging artifacts and reports when no useful log evidence is visible. It helps surface observability gaps before they become debugging problems.

### Diagnostic fingerprint

**Log artifact discovery → observability signal → explanation → improvement plan**

## Why this agent is distinct

LogMedic is intentionally about the evidence needed to reason from runtime behavior. It does not attempt to infer application health from thin repository metadata. Its current rule answers a practical baseline question:

> **Does the project expose recognizable application logs?**

## Workflow

```text
Repository
   ↓
File scanner
   ↓
Log artifact detection
   ↓
Finding + evidence
   ↓
Observability recommendation
```

## Verification

This repository includes:
- OpenGAP passport metadata
- a dedicated log-focused fixture
- deterministic diagnostic rules
- four framework portability adapters
- local adapter tests

OpenGAP validation passed, and all four generated framework exports have been successfully exercised.

## Structure

```text
Identity:        agent.yaml / SOUL.md
Behavior:        AGENTS.md / DUTIES.md
Explainability:  EXPLAINABILITY.md
Runtime:         agent.py
Diagnostics:     tools/
Portability:     adapters/
Verification:    tests/
```

## Design principle

**Observability starts with evidence.** LogMedic does not manufacture runtime data. When logs are not recognizable from the inspected project, the agent reports that limitation directly.

## Medic family

LogMedic belongs to a family of small, composable agents. Each member has a focused diagnostic fingerprint rather than pretending that one generic reviewer is an expert at everything.