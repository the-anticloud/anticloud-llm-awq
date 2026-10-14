# Educators — LLM_AWQ

**Project:** LLM_AWQ  
**Category:** CHIP_QUANTIZATION  
**Upstream:** see BENCH.json  
**Pinned commit:** `d6e797a42b9ef7778de8ee2352116e0f48a78d61`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `93ad95290162f625d922d925a825662e144cc4486a306ba5e0cfaf84702dce7e`  
**Date:** October 2026

## Teaching with LLM_AWQ

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `93ad95290162f625d922d925a825662e144cc4486a306ba5e0cfaf84702dce7e` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
