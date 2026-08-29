# ADL-SEEM v3.0 Loader Hardening

**Status:** Accepted (2026-08-29)  
**Applies to:** sovereign-clean-room and any future dynamic skill loading under the SEEM lineage.

## Executive Summary

The current loader executes Base64-decoded Python source through:

```python
exec(base64.b64decode(_b64).decode("utf-8"), globals())
```

This design introduces unnecessary security, auditability, and maintainability risks. The recommended architecture is to eliminate dynamic execution from the trusted core and replace it with statically imported, reviewable Python modules. Dynamic execution, if retained for future extensibility, must be isolated behind cryptographic verification and OS-level containment.

## Findings

### Current Risks

The existing loader combines multiple high-risk characteristics:

- Dynamic code execution
- Import-time execution
- Full access to module globals
- No cryptographic provenance verification
- No containment boundary

As a result, any executed payload inherits the privileges and trust of the hosting process.

### Security Assessment

Language-level restrictions such as restricted builtins, custom globals dictionaries, AST rewriting, or bytecode filtering may reduce accidental misuse but do **not** constitute a reliable security boundary against a determined adversary.

For untrusted execution, OS-enforced isolation is required.

## Recommended Architecture

### Path A — Preferred

Replace Base64 payload execution with statically imported source modules.

```python
from core.vsa_engine import CleanRoomVSAEngine   # example
```

**Benefits**

- Complete source visibility
- Static analysis compatibility
- Reproducible builds
- Simplified provenance tracking
- Reduced attack surface

### Path B — Controlled Dynamic Loading (Exception Only)

If dynamic loading remains a requirement:

1. Verify Ed25519 signatures before execution
2. Execute only inside an isolated worker process
3. Disable network access by default
4. Apply seccomp filters (default-deny allow-list)
5. Apply resource limits (cgroups / rlimits)
6. Communicate through a strict IPC protocol
7. Treat all payloads as hostile

## Trust Model

| Component              | Trust Level | Execution Model      |
|------------------------|-------------|----------------------|
| Core Engine            | Trusted     | Static Import        |
| Governance Layer       | Trusted     | Static Import        |
| Provenance Layer       | Trusted     | Static Import        |
| First-Party Skills     | Signed      | Static or Isolated   |
| Third-Party Skills     | Untrusted   | Isolated Process     |
| External Contributions | Untrusted   | Container or Micro-VM|

## Migration Plan

**Phase 1**  
- Inventory all `exec()` / `eval()` usage  
- Classify payloads as trusted or untrusted  
- Document all dynamic execution paths  

**Phase 2**  
- Convert trusted payloads into standard Python modules  
- Replace Base64 execution with imports  
- Delete unused `_vsa_part_*.py` and placeholder chunks once replaced  
- Add automated integrity checks to the build pipeline  

**Phase 3**  
- Create an isolated execution service for optional skill packages  
- Add signature verification  
- Add resource controls and audit logging  

**Phase 4**  
- Evaluate WASM-based plugin execution  
- Evaluate micro-VM deployment for third-party extensions  
- Define capability-based plugin interfaces  

## Acceptance Criteria

- No dynamic execution in the trusted core
- All first-party modules statically reviewable
- Signed provenance for executable extensions
- Isolation boundary for all untrusted code
- Reproducible build and deployment pipeline
- Full audit trail for skill execution
- Fail-closed on any integrity or isolation failure

## Decision

ADL-SEEM v3.0 shall prioritize static, reviewable source modules for all core functionality. Dynamic execution shall be considered an exception mechanism and must be cryptographically verified and isolated before execution.

## Notes

- The CRITICAL OPERATOR_QUEUE item (missing `_vsa_b64_5/6/7` in sovereign-clean-room) must be resolved before Path A can be declared complete. Do **not** invent engine source.
- This document is an architectural note under the ADL-SEEM constitution; amendments follow Article 7.
