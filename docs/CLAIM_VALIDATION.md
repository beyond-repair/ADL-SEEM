# Claim Validation Policy (SEEM)

## Levels

| Level | Name | Meaning |
|-------|------|---------|
| 0 | Idea | Informal concept |
| 1 | Mathematical framework | Equations/structure only |
| 2 | Numerical fit | Fits data under stated assumptions |
| 3 | Independent reproduction | Third-party recompute |
| 4 | Experimental evidence | Controlled experiment |
| 5 | Engineering validation | Deployed, measured system |

## Mandatory rules for SEEM lineage

1. Default for cognitive / digital-twin / AGI claims: **Level 0–1** unless higher is evidenced.
2. Software readiness (tests, CI, attestation, skill crypto) is tracked **separately** from claim level.
3. A green CI, Ed25519 signature, Merkle proof, or SHACL pass does **not** raise cognitive claim level.
4. Claims of “unique digital twin impossible to replicate without history” require Level 3+ independent reproduction.
5. Claims of production AGI or autonomous permanent mind require Level 5 and explicit measurement protocol.

## Software vs Cognition

| Track | What is measured |
|-------|------------------|
| Software maturity | Test suite, CI status, VSA load success, skill gate integrity |
| Cognitive claim | Actual demonstrated reasoning, memory permanence, evolution under controlled protocol |
