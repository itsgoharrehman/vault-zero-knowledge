# Contributing to Vault

Thank you for your interest in contributing to Vault.

## Core Development Invariants

All contributions must adhere to our zero-knowledge security guarantees:

1. **Zero Plaintext Transmission**: No master passwords, decrypted notes, or private keys may ever be logged to the console, cached in persistent storage, or transmitted across network requests.
2. **WebCrypto Standard Primitives**: All cryptographic operations must strictly utilize the standard W3C WebCrypto API (`window.crypto.subtle`). Custom cryptographic algorithms or external npm crypto libraries are prohibited.
3. **IV Freshness**: Initialization Vectors must always be 96-bit (12 bytes) cryptographically random values generated via `window.crypto.getRandomValues()`. Never hardcode, serialize, or reuse IVs across encryptions.
4. **Zero Third-Party Telemetry**: Never introduce external analytics, remote fonts, or unvetted CDN scripts that could access DOM values or exfiltrate keystrokes.
5. **Non-Extractable Keys**: Derived AES keys must remain non-extractable in memory (`extractable: false`).

## Code of Conduct

All contributors and participants are expected to adhere to our [Code of Conduct](CODE_OF_CONDUCT.md).

## Development Workflow

1. Fork the repository on GitHub.
2. Clone your fork locally:
   ```bash
   git clone https://github.com/<your-username>/vault-zero-knowledge.git
   cd vault-zero-knowledge
   ```
3. Create a descriptive feature branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. Build and verify locally:
   ```bash
   node build.js
   ```
5. Submit a Pull Request targeting `main`. Complete the mandatory security checklist in the pull request template.