# Students — LLM_AWQ

**Project:** LLM_AWQ  
**Category:** CHIP_QUANTIZATION  
**Upstream:** see BENCH.json  
**Pinned commit:** `d6e797a42b9ef7778de8ee2352116e0f48a78d61`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `93ad95290162f625d922d925a825662e144cc4486a306ba5e0cfaf84702dce7e`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `d6e797a42b9ef7778de8ee2352116e0f48a78d61`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `93ad95290162f625d922d925a825662e144cc4486a306ba5e0cfaf84702dce7e`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
