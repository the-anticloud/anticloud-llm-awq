# Ethics — LLM_AWQ

**Project:** LLM_AWQ  
**Category:** CHIP_QUANTIZATION  
**Upstream:** see BENCH.json  
**Pinned commit:** `d6e797a42b9ef7778de8ee2352116e0f48a78d61`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `93ad95290162f625d922d925a825662e144cc4486a306ba5e0cfaf84702dce7e`  
**Date:** October 2026

## Position

LLM_AWQ is packaged for offline deployment with a verifiable audit trail. The
ethical questions this raises are answered by making the system's behaviour
checkable rather than by policy statements.

## The four commitments

1. **No hidden egress.** The deployment has no external API dependency; this is
   testable by running it with the network disconnected.
2. **Attributable output.** Every artifact is recorded in a hash chain, so what
   the system produced can be reconstructed.
3. **Operator control.** The institution owns the hardware and the keys.
4. **Refusal to overclaim.** Where a certification is not held, the project says
   so rather than implying it.

## Dual use

This project is packaged for civilian and public-sector deployment. Where an
upstream has dual-use characteristics, the licence gate and the reference-only
marking in `BENCH.json` record that.
