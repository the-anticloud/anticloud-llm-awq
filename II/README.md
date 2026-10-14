# Independent Insurance — LLM_AWQ

**Project:** LLM_AWQ  
**Category:** CHIP_QUANTIZATION  
**Upstream:** see BENCH.json  
**Pinned commit:** `d6e797a42b9ef7778de8ee2352116e0f48a78d61`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `93ad95290162f625d922d925a825662e144cc4486a306ba5e0cfaf84702dce7e`  
**Date:** October 2026

## Why AI-specific cover matters

Deploying AI in a regulated sector creates liability surfaces that ordinary
technology cover does not reach: inference liability, audit-trail liability,
data-breach liability and IP-infringement liability.

## How this project's architecture reduces insurable risk

| Risk | Cloud AI | LLM_AWQ with AIOSS |
|---|---|---|
| Audit-trail loss | high — vendor-controlled logs | low — append-only chain, verifiable offline |
| Data breach in transit | high — data transits external servers | low — no external endpoint |
| Compliance violation | high — cannot satisfy air-gap requirements | low — structural |
| IP liability | moderate | low — pinned provenance chain |

## Evidence package for an insurer

- AIOSS chain verification for head `93ad95290162f625d922d925a825662e144cc4486a306ba5e0cfaf84702dce7e`
- The 16-check register with per-check evidence hashes
- Framework control mapping in `BENCH.json`

## Contact

lois@0-1.gg
