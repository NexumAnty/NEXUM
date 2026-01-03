# Security Policy

## Security First, Not Security Theater

NEXUM is built with a security-first mindset.
This project avoids vague promises and focuses on explicit, verifiable guarantees.

Security is treated as a design constraint — not a marketing feature.

---

## Security Philosophy

NEXUM follows these core principles:

- **Explicit guarantees over assumptions**
- **Isolation before obfuscation**
- **Local-first by default**
- **Minimal trusted surface**
- **No hidden telemetry**

If a security property cannot be clearly explained, it is not advertised.

---

## Threat Model Overview

NEXUM is designed to reduce risks related to:

- Browser fingerprinting techniques
- Cross-session and cross-profile correlation
- Cookie, cache, and storage leakage
- Shared runtime and environment contamination
- Proxy misconfiguration exposure

Each browser profile is treated as an isolated environment with a clearly defined lifecycle.

---

## Out of Scope

NEXUM does **not** claim to protect against:

- Operating system compromise
- Hardware-level identifiers
- Network-level surveillance
- User OPSEC failures
- Malicious browser extensions
- Compromised proxy providers

Users are expected to understand that an anti-detection browser is **one layer**, not a complete anonymity solution.

---

## Isolation Model

- Each profile operates in an isolated context
- No shared cookies, storage, or cache
- No cross-profile memory reuse
- Deterministic profile behavior by default

Isolation is treated as a hard requirement, not a configuration option.

---

## Data Handling & Storage

- Profiles are stored locally by default
- Sensitive data is encrypted at rest
- No automatic cloud synchronization
- No background data transmission

Remote synchronization, if introduced, will always be **explicit and opt-in**.

---

## Transparency & Limitations

NEXUM intentionally avoids claims such as:
- "Undetectable"
- "100% anonymous"
- "Invisible"

Instead, documented limitations are considered a security feature.
Knowing what a tool does *not* protect against is critical for safe usage.

---

## Responsible Disclosure

Security research and responsible disclosure are welcome.

At this early stage, vulnerabilities and security concerns should be reported via private communication channels that will be published closer to public beta.

Public disclosure guidelines will be introduced once the core architecture stabilizes.

---

## Security as a Process

Security in NEXUM is not a one-time feature.

It is an ongoing process involving:
- Continuous threat analysis
- Architecture review
- Real-world feedback
- Conservative feature expansion

Changes that weaken isolation or increase the trusted surface are avoided by design.
