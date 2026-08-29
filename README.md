<div align="center">

# ADL-SEEM

### Systems Engineering Standard for Self-Evolving Emergent Mind substrates

[![ACTIVE](https://img.shields.io/badge/status-ACTIVE-22c55e?style=for-the-badge)](https://github.com/beyond-repair/ADL-SEEM)
[![v3.0](https://img.shields.io/badge/Version-3.0-0ea5e9?style=for-the-badge)](docs/CONSTITUTION.md)

</div>

---

## Why it is unique

Most cognitive / AGI seeds grow claims faster than evidence.  
This repository forces **classification, claim levels, lifecycle, and a response contract** so SEEM cannot quietly pretend to be a finished digital twin or production AGI.

It is the **governance twin** of [ADL-Governance](https://github.com/beyond-repair/ADL-Governance) specialized to the SEEM lineage.

---

## Visual workflow

```text
  ┌──────────────────┐
  │ 1. IDEA / CLAIM  │  new cognitive or substrate statement
  └────────┬─────────┘
           ▼
  ┌──────────────────┐
  │ 2. CLASSIFY      │  ACTIVE · RESEARCH · FROZEN · SUPERSEDED · ARCHIVED
  └────────┬─────────┘
           ▼
  ┌──────────────────┐
  │ 3. CLAIM LEVEL   │  0–5  (cognition defaults ≤1 without evidence)
  └────────┬─────────┘
           ▼
  ┌──────────────────┐
  │ 4. REGISTER      │  point at canonical substrate
  └────────┬─────────┘
           ▼
  ┌──────────────────┐
  │ 5. BUILD LOOP    │  implement → test → CI → document → release/archive
  └────────┬─────────┘
           ▼
  ┌──────────────────┐
  │ 6. AUDIT         │  response contract · contradiction check · residual queue
  └──────────────────┘
```

### Step-by-step — how & why

| Step | How | Why |
|-----:|-----|-----|
| **1** | New SEEM-related work appears | Without a gate, duplicates and over-claims explode |
| **2** | Assign lifecycle class | Readers know if it is product or history |
| **3** | Assign claim 0–5 | Stops “hypothesis” reading as “unique digital twin” |
| **4** | Point at canonical | One source of truth for the SEEM runtime |
| **5** | Standard eng loop | No repo bypasses test/docs |
| **6** | Periodic audit | Drift is visible |

---

## Canonical relationship

```text
                    ┌─ ADL-Governance ─┐
                    │  portfolio rules │
                    └────────┬─────────┘
                             │
                    ┌─ ADL-SEEM ───────┐
                    │  SEEM-specific   │
                    │  constitution    │
                    └────────┬─────────┘
                             │
                             ▼
                 sovereign-clean-room
                 (ACTIVE runtime substrate)
```

| Doc | Purpose |
|-----|---------|
| [CONSTITUTION.md](docs/CONSTITUTION.md) | Immutable architectural principles |
| [CLAIM_VALIDATION.md](docs/CLAIM_VALIDATION.md) | Levels 0–5 for cognition claims |
| [LIFECYCLE.md](docs/LIFECYCLE.md) | ACTIVE → ARCHIVED for SEEM lineage |
| [RESPONSE_CONTRACT.md](docs/RESPONSE_CONTRACT.md) | ADL-SEEM v3.0 engineering response schema |
| [CANONICAL.md](docs/CANONICAL.md) | Authoritative implementation pointer |

---

<div align="center">

**Every SEEM-related repo should link here and to ADL-Governance.**

Canonical runtime: [sovereign-clean-room](https://github.com/beyond-repair/sovereign-clean-room)

</div>
