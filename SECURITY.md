# Security Policy

## Supported Versions

| Version | Supported | Description |
| :--- | :--- | :--- |
| `1.0.x` | Yes | Current stable release branch (`main`) |
| `< 1.0.0` | No | Legacy prototypes |

## Cryptographic Invariants and Scope

Vault is designed around a strict zero-knowledge security boundary:
* Cryptographic primitives are implemented strictly through the standard W3C WebCrypto API (`window.crypto.subtle`).
* Master passwords and encryption keys must never be logged, cached in persistent storage, or transmitted over any network channel.
* Initialization Vectors (IVs) must be cryptographically random and 96 bits (12 bytes) in length, generated via `window.crypto.getRandomValues()`.
* Key derivation must enforce a minimum of 100,000 PBKDF2-HMAC-SHA256 iterations with a unique per-user salt.

## Reporting a Vulnerability

If you discover a security vulnerability, cryptographic weakness, or credential leakage issue, please report it privately:

* **Security Contact**: Gohar Rehman
* **Email**: `goharrehmanfsd260@gmail.com`
* **Response SLA**: Initial acknowledgement within 48 hours; resolution timeline provided within 7 days.

### Report Submission Requirements
Please include:
1. Detailed description of the vulnerability and attack vector.
2. Minimal proof of concept or reproduction steps.
3. Specific affected files, functions, or cryptographic primitives.
4. Proposed mitigation or patch (if available).

Please do not disclose vulnerabilities publicly via GitHub issues or discussions until a remediation patch has been deployed.