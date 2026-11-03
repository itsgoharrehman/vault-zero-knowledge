## Summary of Changes

Describe the proposed changes, architecture impact, and reason for the modification.

## Security Checklist

Before submitting this pull request, verify each of the following security invariants:

- [ ] **Zero Plaintext Leakage**: Verified that no plaintext passwords, notes, or master keys are written to storage or transmitted over network calls.
- [ ] **Cryptographic Integrity**: All encryption and decryption operations utilize the W3C WebCrypto API (`window.crypto.subtle`).
- [ ] **IV Freshness**: Verified that Initialization Vectors (IVs) are generated via `crypto.getRandomValues` and never hardcoded or reused.
- [ ] **Sanitized Inputs**: All user inputs rendered to the DOM are properly escaped or handled to prevent XSS vulnerabilities.
- [ ] **No Hardcoded Secrets**: Verified that no API keys, tokens, or credentials are committed.
- [ ] **Tested in Browser**: Verified in at least one modern browser (Chrome, Firefox, Safari, Edge).

## Testing Performed

Detail the local tests, test cases, or manual verification steps conducted.