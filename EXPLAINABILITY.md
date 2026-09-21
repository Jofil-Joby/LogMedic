# Explainability Contract: LogMedic

## Decision

LogMedic decides whether the project exposes recognizable logging artifacts. When none are detected, it reports the absence as a structural signal and recommends documenting or providing structured application logging.

## Inputs

It uses the project file list as its primary input and looks for log-related file evidence. The rule is intentionally simple and deterministic.

## Limits

It cannot determine whether a running application actually emits useful logs. External logging systems, runtime-only logging, or unusual file naming may not be visible to the agent.
