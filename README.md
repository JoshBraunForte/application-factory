# Application Factory (SDLC Framework)

Centrally-versioned framework of agent roles, operating model, templates, and standards that
projects consume to run a governed, AI-assisted software development lifecycle.

**Current version:** `0.1.0` (see `manifest.json`).

## Core principle
> AI agents analyze, recommend, challenge, create artifacts, and coordinate work.
> **Humans make major decisions.**

See [`operating-model.md`](operating-model.md) for the full governing workflow, decision-escalation
model, and artifact governance rules.

## Contents
| Path | Purpose |
|------|---------|
| `operating-model.md` | Governing workflow, decision escalation, artifact governance, distribution model |
| `agents/` | Agent role definitions (Project/Product Manager, Enterprise Architect, Software Engineer, QA, Security, Operations, Release Manager, Opportunity Analyst, Debugging & Reliability Engineer) |
| `templates/` | Artifact templates each agent fills in (profile, roadmap, architecture, QA, security, release, etc.) |
| `standards/` | Reusable factory-wide guidance (platforms, coding/security/testing standards, repo conventions) |
| `manifest.json` | Factory version and distribution metadata |

## Distribution model
The factory is the single source of truth. Projects **consume a snapshot** of approved assets into
their own `.factory/` directory using bootstrap/update tooling. Each project records:
- factory version
- update date
- source
- locally modified factory files

Updates are deliberate, not automatic. Deferred scope is never discarded without an explicit human
decision.

## Consuming this in a project
Copy the contents of this repository into the project's `.factory/` directory and record provenance
in the project's `.factory/manifest.json` (`factory_version`, `factory_source`, `installed_at_utc`,
`local_overrides`).

## Reference implementation
The **Loaner Equipment Tracker** sample project was built end-to-end using this factory (profile →
roadmap → architecture → build → QA → security → release), exercising all ten agent roles.
