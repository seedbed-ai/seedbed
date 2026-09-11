# Seedbed

**Seedbed is an early-stage platform for long-lived autonomous and adaptive systems.** It is designed to keep semantic identity and interaction boundaries from being unnecessarily owned by whichever environment, learning or decision framework, or execution infrastructure happens to be in use today.

> **Pre-release:** Seedbed is in very early development. No customer-executable public release is available yet. Expect defects, incomplete capabilities, breaking changes, and material design evolution before the first supported pre-release.

## Why Seedbed

Long-lived autonomous systems tend to accumulate coupling across boundaries that should be able to change independently. Entity identity becomes tied to a process or framework. Interaction semantics become tied to one simulator, device, or API. Runtime lifecycle becomes entangled with application meaning. Replacing one legitimate implementation choice can then force unrelated redesign elsewhere.

Seedbed is being built to reduce that **change amplification**.

The intended result is a stable semantic and interaction boundary around long-lived application entities so that supported environments, learning or decision frameworks, and execution realizations can evolve with less unnecessary cross-cutting change.

Seedbed must remove more coupling than it introduces. It is not intended to sit in every system merely because the system uses AI.

## What Seedbed is

At the Product level, Seedbed is intended to provide general machinery for:

- coherent semantic identity for long-lived autonomous or adaptive application entities;
- explicit information and interaction boundaries;
- relationships and routing between those boundaries;
- independent customer-owned workload implementations and mutable workload state;
- operational realization that can evolve without automatically redefining application meaning; and
- a clean separation between application semantics, learning or decision frameworks, environments, and execution infrastructure.

The internal domain vocabulary currently includes concepts such as **Bed**, **Entity**, **Machine**, **Simulation**, **Interface**, **Connection**, and **Interaction**. Those concepts are useful for understanding the direction of the system, but the public executable API and schemas are not yet frozen.

## What Seedbed is not

Seedbed is not defined as:

- a generic AI-agent framework;
- a reinforcement-learning library or model trainer;
- a universal multi-agent API;
- a simulator, game engine, or robotics environment;
- a container, cluster, or cloud orchestrator;
- a generic observability platform; or
- a promise of universal persistence, migration, high availability, or exactly-once execution.

Those systems may participate in a Seedbed-based application without Seedbed taking ownership of their domain semantics.

## Who Seedbed is for

Seedbed is initially aimed at technically sophisticated builders responsible for autonomous or adaptive systems that are expected to live long enough for their surroundings to change.

The strongest fit is likely where several of these are true:

- application entities are long-lived or repeatedly re-realized;
- environments, simulators, devices, or integrations may change;
- learning or decision frameworks may evolve independently;
- execution targets or infrastructure may change;
- semantic identity must outlive a particular process or implementation;
- integration and lifecycle machinery is being duplicated across boundaries; or
- a desired change is being deferred because too many unrelated parts of the system would have to move together.

A disposable workload with one fixed environment and framework may not benefit from Seedbed at all.

## Conceptual boundary

The exact public API is still being defined, but the intended separation is roughly:

```text
application meaning and objectives
            │
            ▼
  semantic identity + interactions
            │
        Seedbed boundary
            │
            ▼
customer-owned workload / Simulation
            │
            ├── learning or decision framework
            ├── environment / simulator / device
            └── execution infrastructure
```

Seedbed should coordinate the boundaries it owns without absorbing the meaning or authority of the systems around it.

## Current public status

This repository is Seedbed's **public customer-facing repository**. It is intended to become the durable home for:

- versioned public Seedbed release artifacts;
- customer-facing integration contracts and schemas;
- installation and operational documentation;
- minimal examples;
- release notes and compatibility information; and
- public support and design feedback.

Seedbed implementation source is not published here by default. Public interfaces, documentation, examples, and integration contracts may be public without making the proprietary implementation source public.

### Available today

Today, this repository provides the public support and design-feedback boundary only. The first customer-executable integration surface is still being prepared. The current public integration blocker and its status are tracked in [issue #2](../../issues/2).

Until a release is explicitly published here, do **not** treat private repositories, development branches, commits, internal artifacts, or inferred Python APIs as supported Seedbed customer interfaces.

## Get involved now

Early feedback is particularly useful because important boundaries are still changeable.

Use GitHub Issues for:

- **integration / support questions** — tell us what you are trying to build and where the public contract is insufficient;
- **bug reports** — report incorrect, unsafe, or surprising Seedbed behavior;
- **design / architecture requests** — describe a serious workload that the current model cannot represent cleanly.

Substantial design-change requests are welcome. If Seedbed would force a real workload into an unnatural architecture, we would rather learn that now than encourage a permanent workaround around a pre-release design mistake.

See [SUPPORT.md](SUPPORT.md) for the public support boundary and [TRIAGE.md](TRIAGE.md) for how issues are classified, routed, and kept open through customer-facing resolution.

## Security

Do not post secrets, credentials, confidential source code, private repository access details, customer-sensitive identifiers, or unpatched exploit details in public issues. See [SECURITY.md](SECURITY.md) for the current security-reporting process.

## Releases

No public Seedbed release has been published yet.

When the first implementation-bearing pre-release is ready, this repository will identify the exact release version, supported deployment assumptions, customer artifact, integration contract, installation path, and minimal end-to-end example. A technical implementation is not considered publicly supported merely because it exists internally.

## Maturity

Seedbed is intentionally being presented before it is production-stable so real integrations can influence the design. Support responses distinguish among:

- publicly supported behavior;
- implemented but not yet public behavior;
- architecture that is not yet implemented;
- open design territory; and
- explicitly unsupported scope.

That distinction is part of the project contract, not a disclaimer to be removed once development becomes inconvenient.
