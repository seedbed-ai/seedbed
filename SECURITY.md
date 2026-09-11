# Security policy

Seedbed is in very early development and no customer-executable public release is available yet. Security feedback is still welcome, especially when it concerns architecture, isolation, authority boundaries, secret handling, artifact integrity, or a future public integration surface.

## Reporting a potential vulnerability

Do **not** publish exploit details, secrets, credentials, private source code, customer-sensitive evidence, or other material that could make an unresolved vulnerability easier to abuse.

If GitHub shows a private **Report a vulnerability** option for this repository, use that channel for vulnerability details.

If no private vulnerability-reporting option is available, open a public issue containing only a sanitized request for private security coordination. Use a title such as:

`security: private reporting requested`

Include only enough non-sensitive information to establish that a private conversation is needed. Do not include reproduction details, exploit code, secrets, or vulnerable private-system information in that issue.

For security or isolation **design questions that do not disclose an exploitable vulnerability**, use the normal public issue process.

## What to include privately

When a private reporting channel is established, useful information includes:

- the affected Seedbed release or artifact identity, when one exists;
- the affected component or public interface;
- the expected security boundary;
- the observed behavior and impact;
- minimal reproduction steps;
- prerequisites or attacker capabilities;
- whether exploitation appears active or only theoretical; and
- any proposed mitigation, if you have one.

Please minimize customer-identifying information and redact unrelated secrets.

## Current support boundary

Before the first public executable release, some reports may concern architecture or unpublished implementation rather than a supported public capability. Seedbed will distinguish those states rather than presenting internal implementation as a customer-facing security guarantee.

Once public releases exist, this policy will be expanded with supported-version windows, disclosure expectations, and release-specific remediation guidance.
