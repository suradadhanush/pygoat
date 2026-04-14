# Contributions to OWASP PyGoat

Contributed 5 production-impact pull requests to OWASP PyGoat as part of GSoC 2026 preparation — fixing installation failures, cross-platform bugs, container management issues, and security misconfigurations.

---

## Pull Requests

### [PR #441 — Docker base image fix](https://github.com/adeyosemanputra/pygoat/pull/441)

**Impact:** Fixed broken installations caused by Debian Buster (EOL).

- Upgraded base image → `python:3.11-bookworm`
- Removed invalid pinned dependencies
- Restored Docker build compatibility across environments

---

### [PR #442 — Cross-platform port detection](https://github.com/adeyosemanputra/pygoat/pull/442)

**Impact:** Fixed container startup failure on Windows systems.

- Replaced hardcoded errno (`111`) with `errno.ECONNREFUSED`
- Enabled platform-independent port detection
- Fixed typo in user-facing message

---

### [PR #443 — Container lifecycle + validation fixes](https://github.com/adeyosemanputra/pygoat/pull/443)

**Impact:** Resolved multiple critical runtime failures in container handling and request processing.

- Fixed container reuse (short ID vs full ID mismatch)
- Corrected PUT request parsing (`request.body`)
- Added subprocess error handling (previously silent failures)
- Fixed port conflict (8000 → 8001)
- Added unit tests for validation logic

---

### [PR #444 — Cross-platform exception handling](https://github.com/adeyosemanputra/pygoat/pull/444)

**Impact:** Prevented crashes on Linux/macOS environments.

- Replaced `WindowsError` with `OSError`
- Ensured compatibility across all OS environments
