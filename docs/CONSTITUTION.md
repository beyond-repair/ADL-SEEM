# SEEM Constitution (ADL-SEEM v3.0)

## Article 1 — Purpose

Repositories and statements under the SEEM lineage exist to advance offline-first, auditable, symbolic cognition substrates. No repository may blur engineering validation (CI, attestation, skill gates) with unvalidated claims of unique digital twins, permanent unreplicable minds, or production AGI.

## Article 2 — Classification

Every SEEM-related repository MUST carry exactly one primary class:

| Class | Meaning |
|-------|---------|
| ACTIVE | Engineering maintained; CI required |
| RESEARCH | Hypothesis-grade; no product or AGI claims |
| FROZEN | Complete as reference; no feature work |
| SUPERSEDED | Replaced by a named successor |
| ARCHIVED | Historical only; no new commits expected |

## Article 3 — Canonical authority

The sole authoritative runtime implementation is **sovereign-clean-room**.  
All SEEM-* predecessors and pattern donors MUST point to it.  
Non-canonical work is non-authoritative.

## Article 4 — Claim integrity

Cognitive and performance claims MUST be tagged Level 0–5 per CLAIM_VALIDATION.md.  
Cryptographic success, CI green, or ledger integrity does **not** imply cognitive or AGI validation.

## Article 5 — Boundaries

| Boundary | Rule |
|----------|------|
| Clean-Room vs external models | Offline-first; network_access: false enforced by default |
| VSA source | Must be complete and loadable; placeholders are failure |
| Skill packages | Signed (Ed25519), schema-validated, SHACL-gated before execution |
| Physics bridges | May run offline; do not raise claim level |

## Article 6 — Lifecycle

Creation, promotion, supersession, and archive follow LIFECYCLE.md.

## Article 7 — Amendments

Changes to this constitution land in this repository via reviewed commits on `main`, then propagate to sovereign-clean-room manifests and ADL-Governance registry notes.
