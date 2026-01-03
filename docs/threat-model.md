# NEXUM Threat Model

This document outlines the threat model for NEXUM.
It defines what threats are considered, reduced, or explicitly out of scope.

---

## Threat Model Scope

NEXUM focuses on mitigating threats related to browser-based identification and session correlation.

The threat model assumes:
- The host operating system is trusted
- The user controls their proxy configuration
- The user follows basic operational security practices

---

## Threats Addressed

NEXUM is designed to reduce the following risks:

### 1. Browser Fingerprinting

- Canvas, WebGL, Audio, and API-based fingerprinting
- Inconsistent fingerprint behavior across sessions
- Entropy leakage through shared state

Mitigation:
- Controlled fingerprint stabilization
- Profile-specific configuration
- Deterministic runtime behavior

---

### 2. Session Correlation

- Cross-account linking via shared browser state
- Correlation through timing or storage artifacts

Mitigation:
- Strong profile isolation
- No shared cookies or storage
- Explicit session lifecycle management

---

### 3. Network-Level Correlation

- IP leakage between profiles
- Accidental proxy misconfiguration

Mitigation:
- Profile-bound proxy settings
- Network abstraction layer
- Explicit validation of proxy state

---

### 4. Local Data Leakage

- Cross-profile access to local data
- Residual artifacts after profile deletion

Mitigation:
- Encrypted local storage
- Explicit profile teardown
- No background persistence

---

## Threats Not Addressed

NEXUM does NOT attempt to protect against:

- Compromised operating systems
- Hardware-level identifiers
- Kernel or firmware malware
- Malicious browser extensions
- Proxy or VPN provider surveillance
- User OPSEC failures

---

## Assumptions & Limitations

Security guarantees depend on:
- Correct system configuration
- Trusted execution environment
- Responsible usage patterns

NEXUM does not claim perfect anonymity.

---

## Security Philosophy

Clear limitations are considered a security feature.
Understanding what a tool does *not* protect against is essential.

This threat model will evolve as the project matures.
