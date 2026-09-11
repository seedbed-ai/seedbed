# Support

Seedbed is in very early development. The purpose of public support right now is not only to help integrations succeed, but also to discover where the platform's design is wrong, incomplete, or too rigid.

Public issues are handled under the durable triage process in [`TRIAGE.md`](TRIAGE.md).

## What to report

Please open an issue for:

- integration questions;
- installation or runtime failures;
- unclear or missing documentation;
- design constraints that prevent a serious use case;
- requests for architectural changes;
- security or isolation concerns that do not involve disclosing an active vulnerability publicly.

Serious design-change requests are welcome. If the current model would force your workload into an unnatural architecture, say so clearly and describe the desired behavior and why it matters.

## What to expect

Seedbed is not production-stable yet. You should expect:

- bugs and rough edges;
- incomplete capabilities;
- breaking changes;
- APIs and manifests that may evolve;
- operational gaps;
- support answers that sometimes say a feature is architected but not implemented, or that a design decision is still open.

We will try to distinguish those states explicitly.

## Public issue guidance

Do not post:

- passwords, API keys, tokens, private keys, or secret material;
- confidential source code;
- private repository URLs or access details;
- customer-sensitive identifiers that are unnecessary to reproduce the problem;
- security exploit details for an unpatched vulnerability.

For a private workload, use generic names and describe only the technical contract necessary to understand the issue.

## Support workflow

1. Search existing issues and public documentation.
2. Open the most appropriate issue template.
3. Include the Seedbed release/version or artifact identity when one exists.
4. Describe expected behavior, actual behavior, and why the distinction matters.
5. For design requests, include the concrete workload scenario and constraints.
6. Seedbed support triages the issue under [`TRIAGE.md`](TRIAGE.md) and may answer directly, link an existing capability, identify a known limitation, request bounded evidence, or promote the report into engineering/product work.
7. Customer-readiness blockers remain open until the public support/release boundary actually resolves them; internal implementation alone is not sufficient.

GitHub Issues are currently the authoritative public support channel for the automated Seedbed support workflow. Discussions may be used for broader community conversation, but automated support cannot currently guarantee direct participation there.
