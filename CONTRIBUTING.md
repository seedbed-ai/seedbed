# Contributing to Seedbed

Seedbed is in very early development. The most valuable public contributions right now are concrete integration evidence, bug reports, and serious design constraints that help expose where the platform is wrong, incomplete, or too coupled.

This public repository is not currently the implementation-source repository, and no customer-executable public release exists yet. The contribution process therefore emphasizes issues and design feedback rather than implementation patches.

## Good contributions right now

Please open an issue when you can provide one of these:

- a real workload or operational scenario that Seedbed should support;
- an integration blocker caused by a missing or unclear public contract;
- a bug or unsafe behavior in a published Seedbed surface when releases exist;
- a design or architecture constraint that the current model cannot represent cleanly;
- a documentation ambiguity or contradiction;
- a security or isolation design concern that can be discussed safely in public; or
- evidence that a current assumption is creating unnecessary coupling or lifecycle work.

Concrete constraints are more useful than broad feature requests. Explain what must remain true for your workload, what is currently difficult or impossible, and the consequences if the constraint is not met.

## Design requests are first-class contributions

Seedbed is intentionally open to substantial design changes at this stage. You do not need to fit a serious workload into the current architecture before asking for change.

If the existing model would require an unnatural workaround, describe the desired behavior directly. Include relevant constraints around identity, persistence, ordering, isolation, timing, resource use, restart/recovery, deployment, or authority where they matter.

## Public implementation contributions

Seedbed implementation source is proprietary by default and is not published in this repository. Do not submit copied, reconstructed, reverse-engineered, leaked, or otherwise unauthorized Seedbed implementation source.

Public code or schema contribution paths may be added later for intentionally public components, examples, SDK/client surfaces, or specifications. When that happens, the repository will document the applicable license and contribution process before accepting those contributions.

## Documentation contributions

For now, use an issue to propose public documentation corrections or improvements. The repository's current pull-request policy may restrict PR creation to collaborators while the public surface is still being established.

## Privacy and security

Do not include:

- passwords, API keys, tokens, private keys, or credentials;
- confidential source code;
- customer secrets or production data;
- unnecessary private repository URLs or identities;
- sensitive personal information; or
- exploit details for an unresolved vulnerability.

Use generic workload names when private provenance is not necessary. See [SECURITY.md](SECURITY.md) for vulnerability reporting and [SUPPORT.md](SUPPORT.md) for the support boundary.

## What happens after you file an issue

Public issues are handled under [TRIAGE.md](TRIAGE.md). Seedbed may:

- answer directly from the current public contract;
- identify an implemented-but-not-yet-public capability;
- identify architecture that is not implemented yet;
- treat the area as open design territory;
- create or link internal engineering/Product work; or
- explain that the request is intentionally outside the current scope.

Customer-readiness blockers stay open until the public boundary actually resolves them; internal implementation alone is not treated as customer completion.
