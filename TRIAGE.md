# Public support triage governance

This document defines the durable triage process for public Seedbed support and integration issues.

Seedbed is in very early development. Triage exists both to help users and to discover defects in the product, architecture, documentation, operational model, and integration contract before those boundaries harden.

## Goals

Every new or materially updated public issue should receive an explicit disposition. Triage must distinguish evidence from interpretation, identify the owning decision domain, avoid promising capabilities that do not exist, and preserve customer feedback that could justify a serious design change.

Triage is not merely issue cleanup. Customer evidence may change Seedbed.

## Cadence

Triage occurs in three layers:

1. **Recurring intake triage** — review new and materially updated public issues **hourly** through the active Seedbed organization orchestrator.
2. **Event-driven triage** — review immediately when a customer reports a serious blocker, security/isolation concern, data-loss risk, architectural mismatch, release/installation failure, or when a release/integration milestone is actively being exercised.
3. **Backlog reconciliation** — periodically review all open public issues for stale answers, superseded assumptions, unresolved ownership, promised follow-up, and changes in implementation/release status.

A release candidate or public release must include an additional triage pass over all open issues that could affect installation, compatibility, safety, persistence, workload execution, or published documentation.

## Triage record

A support response should make the following clear when relevant:

- **Classification** — question, documentation gap, bug, integration blocker, design request, security/isolation concern, release/install problem, or other bounded class.
- **Maturity state** — implemented and publicly supported; implemented but not yet public/supported; architected but not implemented; open design territory; or unsupported/out of scope.
- **Severity / customer impact** — informational, friction, blocking one integration, data/safety risk, or release-blocking.
- **Authority / owner** — public documentation/support, Seedbed engineering, Seedbed product, company policy, or another explicitly identified authority.
- **Disposition** — answer now, request bounded evidence, document limitation, create/link engineering work, create/link product work, hold for release, or close with reason.
- **Version context** — public release/artifact identity when one exists; otherwise explicitly state pre-release.

The response does not need to use these exact headings when a shorter natural answer is clearer, but the underlying distinctions must be preserved.

## Required triage questions

For every substantive issue, determine:

1. Is the report supported by the public contract, or is the customer being forced to infer undocumented behavior?
2. Is the requested behavior already implemented?
3. If implemented, is it actually part of the supported public surface for the referenced release?
4. If not implemented, is the behavior already architected or still an open design decision?
5. Is the customer proposing a workaround because Seedbed's design is wrong or incomplete?
6. Could the issue cause data loss, unsafe effects, privilege/security failure, isolation failure, silent corruption, or misleading readiness/status?
7. Does resolving it require a change in another authority rather than public support documentation?
8. Does the issue block a current release or customer acceptance milestone?
9. What durable follow-up must remain after the immediate answer?

## Early-development rule

Do not defend an existing Seedbed design merely because it already exists.

When a serious workload exposes an unnatural abstraction, missing authority boundary, unsafe lifecycle, poor persistence model, inadequate isolation model, incompatible media/transport model, or another structural problem, triage should explicitly invite the customer to state the desired behavior and constraints.

A major design request is valid support input at this stage.

Do not encourage customers to build permanent workarounds around acknowledged architectural defects merely to preserve compatibility with pre-release behavior.

## Customer-facing truthfulness

Never describe an internal implementation, private branch, architecture proposal, or passing repository test as a supported public capability unless it has actually crossed the public release/support boundary.

Use these distinctions consistently:

- **Publicly supported now** — customers may rely on it for the identified public release, subject to that release's maturity statement.
- **Implemented, not yet public/supportable** — real engineering exists, but customers should not couple to it yet.
- **Architected, not implemented** — intended semantics exist, but no executable guarantee exists.
- **Open design** — customer requirements are specifically useful and may change the design.
- **Not supported / non-goal** — explicitly outside the current Seedbed contract.

## Severity and escalation

Treat an issue as urgent/event-driven triage when it credibly involves:

- loss or corruption of durable Simulation/customer state;
- execution or externally consequential effects occurring without current authority;
- stale-process or stale-generation adoption;
- secret/credential exposure;
- privilege escalation or isolation escape;
- artifact/provenance mismatch accepted as valid;
- inability to stop or fence execution/effects;
- a regression preventing installation or execution of the current public release;
- a design blocker that makes a serious integration impossible without violating Seedbed's documented boundaries.

Urgency means investigate and route promptly; it does not mean guessing at a fix or bypassing authority boundaries.

## Routing

The public repository is the customer-facing record. When an issue requires private implementation/product work:

1. answer the customer with the supported present-state truth;
2. create or link the owning internal work item without exposing private customer provenance unnecessarily;
3. preserve only the generalized technical requirement needed by the owning authority;
4. keep the public issue open when the customer still has an unresolved blocker;
5. update the public issue when the relevant capability/documentation is actually published.

Do not copy confidential customer repository names, URLs, identities, secrets, or unnecessary implementation details into another repository.

## Closure rules

Close an issue only when one of these is true:

- the question has been answered and no requested follow-up remains;
- the reported bug/design blocker is fixed in an identified public release or explicitly accepted public documentation;
- the issue is a duplicate with a durable canonical link;
- the requester confirms the blocker is resolved and no platform work remains;
- the request is explicitly not planned/out of scope and the rationale is documented.

Do not close a customer-readiness blocker merely because internal code exists. Public availability and the customer's stated acceptance boundary matter.

## Backlog reconciliation checklist

During a backlog pass:

- inspect every open issue and its latest comments;
- identify unanswered or materially changed questions;
- check whether a newer public release or document changes an earlier answer;
- find issues waiting on Seedbed rather than the requester;
- find promised follow-ups with no linked durable work;
- identify duplicate or superseded issues;
- identify unresolved serious design requests;
- identify issues that should block or shape the next public release;
- update stale pre-release statements after a release is published;
- close only under the closure rules above.

## Orchestration integration

Recurring public triage is part of the organization-wide distributed triage subsystem defined in `seedbed-ai/company/governance/distributed-issue-triage.md`. The public repository retains authority over customer-facing triage semantics in this file; the Company orchestrator is the recurring execution surface, not the semantic owner.

The hourly pass is delta-first. Full-backlog reconciliation is bounded/incremental during ordinary cycles and mandatory at release/major integration boundaries. A separate recurring support scheduler is not required while the organization orchestrator provides healthy hourly coverage.

## Current automation boundary

GitHub Issues are the authoritative automated support surface. The connected Seedbed support agent can directly read, comment on, and manage Issues and repository files. Discussions and Wiki may be useful public/community surfaces, but they are not currently reliable direct automation channels and therefore must not be the sole durable location of a support request requiring Seedbed-agent action.
