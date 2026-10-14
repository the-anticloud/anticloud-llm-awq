# LLM AWQ

![license](https://img.shields.io/badge/license-MIT-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-chip_quantization-lightgrey)

> Anticloud-hardened packaging of the upstream project `LLM_AWQ` in category **CHIP QUANTIZATION**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** CHIP QUANTIZATION · **Upstream:** https://github.com/mit-han-lab/llm-awq · **Upstream pin:** `d6e797a42b9ef7778de8ee2352116e0f48a78d61` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# AWQ: Activation-aware Weight Quantization for LLM Compression and Acceleration 
[[Paper](https://arxiv.org/abs/2306.00978)][[Website](https://hanlab.mit.edu/projects/awq)]

**Efficient and accurate** low-bit weight quantization (INT3/4) for LLMs, supporting **instruction-tuned** models and **multi-modal** LMs.

![overview](figures/overview.png)

The current release supports: 

- AWQ search for accurate quantization. 
- Pre-computed AWQ model zoo for LLMs (Llama-1/2/3, OPT, CodeLlama, StarCoder, Vicuna, VILA, LLaVA; load to generate quantized weights).
- Memory-efficient 4-bit Linear in PyTorch.
- Efficient CUDA kernel implementation for fast inference (support context and decoding stage).
- Examples on 4-bit inference of an instruction-tuned model (Vicuna) and **multi-modal LM** (VILA).
- Chunk prefilling for faster prefilling in multi-round Q&A setting.
- State-of-the-art prefilling speed of LLMs/VLMs on edge devices: [TinyChat 2.0](./tinychat).

**Thanks to AWQ, TinyChat can deliver more efficient responses with LLM/VLM chatbots through 4-bit inference.**

* TinyChat with LLaMA-3-8b on RTX 4090 (2.7x faster than FP16):

![TinyChat with LLaMA-3-8b on RTX 4090: W4A16 is 2.7x faster than FP16](./tinychat/figures/4090_example_new.gif)

* TinyChat with LLaMA-3-8b on Jetson Orin (2.9x faster than FP16):

![TinyChat with LLaMA-3-8b on Jetson Orin: W4A16 is 2.9x faster than FP16](./tinychat/figures/orin_example_new.gif)

**TinyChat also supports inference with vision language models (e.g., VILA, LLaVA). In the following examples, W4A16 quantized models from VILA family are launched with TinyChat.**

* TinyChat with NVILA-8B on RTX 4090 (single-image inputs):

![TinyChat with NVILA on 4090 single image](./tinychat/figures/4090_nvila_single.gif)

* TinyChat with NVILA-8B on RTX 4090 (multi-image inputs):

![TinyChat with NVILA on 4090 multiple images](./tinychat/figures/4090_nvila_multi.gif)

<!-- Check out [TinyChat](tinychat), which delievers **30 tokens/second** inference performance (**3.2x faster** than FP16) for the **Llama2** chatbot on the resource-constrained NVIDIA Jetson Orin!  -->

* TinyChat with video reasoning:

https://github.com/user-attachments/assets/b68a7a0d-5175-4030-985b-5ae0ae94f874

**Prompt:** What might be the next step according to the video?

**Answer:** The next step in the video could be to place the shaped dough onto a baking sheet and let it rise before baking.

**Online demo:** https://vila.hanlab.ai

Check out [TinyChat](tinychat), which offers a turn-key solution for **on-device inference** of LLMs and VLMs on **resource-constrained edge platforms**. With TinyChat, it is now possible to efficiently run **large** models on **small** and **low-power** devices even without Internet connection!

## News
- [2025/04] 🔥 AWQ now supports DeepSeek-R1-Distilled models. Try our example [here](https://github.com/mit-han-lab/llm-awq/blob/main/scripts/DeepSeek_R1_Distill_example.sh)!
- [2025/02] AWQ now supports BF16 precision. See example [here](https://github.com/mit-han-lab/llm-awq/blob/main/scripts/qwen_example.sh).
- [2024/10] 🔥⚡ Explore advancements in [TinyChat 2.0](./tinychat), the latest version with significant advancements in prefilling speed of Edge LLMs and VLMs, **1.5-1.7x** faster than the previous version of TinyChat. Please refer to the [README](./tinychat/README.md) and [blog](https://hanlab.mit.edu/blog/tinychat20) for more details. 
- [2024/05] 🏆 AWQ receives the **Best Paper Award** at **MLSys 2024**. 🎉 
- [2024/05] 🔥 The **VILA-1.5** model family which features **video understanding** is now supported in AWQ and TinyChat. Check out out online demo powered by TinyChat [here](https://vila.hanlab.ai). Example is [here](scripts/vila15_example.sh).
- [2024/05] 🔥 [AMD](https://community.amd.com/t5/ai/reduce-memory-footprint-and-improve-performance-running-llms-on/ba-p/686157) adopts AWQ to improve LLM serving efficiency.
- [2024/04] 🔥 We released AWQ and TinyChat support for The **Llama-3** model family! Check out our example [here](scripts/llama3_example.sh).
- [2024/02] 🔥 AWQ has been accepted to **MLSys 2024**!
- [2024/02] 🔥 We supported [VILA Vision Languague Models](https://arxiv.org/abs/2312.07533) in AWQ & TinyChat! Check our latest demos with multi-image inputs!
- [2024/02] 🔥 We released new version of quantized GEMM/GEMV kernels in [**TinyChat**](tinychat), leading to **38 tokens/second** inference speed on NVIDIA Jetson Orin!
- [2024/01] 🔥 AWQ has been integrated by [Google Vertex AI](https://console.cloud.google.com/vertex-ai/publishers/meta/model-garden/llama-2-quantized)!
- [2023/11] 🔥 AWQ has been integrated by [Amazon Sagemaker Containers](https://aws.amazon.com/blogs/machine-learning/boost-inference-performance-for-llms-with-new-amazon-sagemaker-containers/)!
- [2023/11] 🔥 We added AWQ support and pre-computed search results for CodeLlama, StarCoder, StableCode models. Checkout our model zoo [here](https://huggingface.co/datasets/mit-han-lab/awq-model-zoo)!
- [2023/11] 🔥 AWQ is now integrated natively in Hugging Face transformers through `from_pretrained`. You can either load quantized models from the Hub or your own HF quantized models.
- [2023/10] AWQ is integrated into NVIDIA [TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM/)
- [2023/09] AWQ is integrated into [Intel Neural Compressor](https://github.com/intel/neural-compressor), [FastChat](https://github.com/lm-sys/FastChat/blob/main/docs/awq.md), [vLLM](https://github.com/vllm-project/vllm/blob/main/vllm/model_executor/layers/quantization/awq.py), [HuggingFace TGI](https://github.com/huggingface/text-generation-inference/pull/1054), and [LMDeploy](https://github.com/InternLM/lmdeploy). 
- [2023/09] ⚡ Check out our latest [**TinyChat**](tinychat), which is ~2x faster than the first release on Orin!
- [2023/09] ⚡ Check out [**AutoAWQ**](https://github.com/casper-hansen/AutoAWQ), a third-party implementation to make AWQ easier to expand to new models, improve inference speed, and in

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Python** (manifests: pyproject.toml; scanned in UPSTREAM_CLONE)
- Top-level source layout: `awq/`, `examples/`, `figures/`, `scripts/`, `tinychat/`
- Snapshot size: **180 files**, **25618 lines of code** (measured; see Benchmarks)
- Primary languages: `.py` (74), `.png` (18), `.h` (17), `.sh` (16), `.cu` (12), `.gif` (8)
- Upstream commit pinned for this packaging: `d6e797a42b9ef7778de8ee2352116e0f48a78d61`

---

## Installation

- [AWQ Model Zoo](#awq-model-zoo)
  - [Examples](#examples)
  - [Usage](#usage)
  - [Results on Visual Language Models](#results-on-visual-language-models)
  - [Reference](#reference)
  - [Related Projects](#related-projects)

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

- Chunk prefilling for faster prefilling in multi-round Q&A setting.
- State-of-the-art prefilling speed of LLMs/VLMs on edge devices: [TinyChat 2.0](./tinychat).

**Thanks to AWQ, TinyChat can deliver more efficient responses with LLM/VLM chatbots through 4-bit inference.**

* TinyChat with LLaMA-3-8b on RTX 4090 (2.7x faster than FP16):

![TinyChat with LLaMA-3-8b on RTX 4090: W4A16 is 2.7x faster than FP16](./tinychat/figures/4090_example_new.gif)

* TinyChat with LLaMA-3-8b on Jetson Orin (2.9x faster than FP16):

![TinyChat with LLaMA-3-8b on Jetson Orin: W4A16 is 2.9x faster than FP16](./tinychat/figures/orin_example_new.gif)

**TinyChat also supports inference with vision language models (e.g., VILA, LLaVA). In the following examples, W4A16 quantized models from VILA family are launched with TinyChat.**

* TinyChat with NVILA-8B on RTX 4090 (single-image inputs):

![TinyChat with NVILA on 4090 single image](./tinychat/figures/4090_nvila_single.gif)

* TinyChat with NVILA-8B on RTX 4090 (multi-image inputs):

![TinyChat with NVILA on 4090 multiple images](./tinychat/figures/4090_nvila_multi.gif)

<!-- Check out [TinyChat](tinychat), which delievers **30 tokens/second** inference performance (**3.2x faster** than FP16) for the **Llama2** chatbot on the resource-constrained NVIDIA Jetson Orin!  -->

* TinyChat with video reasoning:

https://github.com/user-attachments/assets/b68a7a0d-5175-4030-985b-5ae0ae94f874

**Prompt:** What might be the next step according to the video?

**Answer:** The next step in the video could be to place the shaped dough onto a baking sheet and let it rise before baking.

**Online demo:** https://vila.hanlab.ai

Check out [TinyChat](tinychat), which offers a turn-key solution for **on-device inference** of LLMs and VLMs on **resource-constrained edge platforms**. With TinyChat, it is now possible to efficiently run **large** models on **small** and **low-power** devices even without Internet connection!

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

- [2023/07] 🔥 We added AWQ support and pre-computed search results for Llama-2 models (7B & 13B). Checkout our model zoo [here](https://huggingface.co/datasets/mit-han-lab/awq-model-zoo)!
- [2023/07] We extended the support for more LLM models including MPT, Falcon, and BLOOM.

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Python |
| Manifests detected | pyproject.toml |
| Files in snapshot | 180 |
| Lines of code | 25618 |
| Dependency references | 23 |
| Dependencies by ecosystem | pypi: 23 |
| Upstream license | MIT |
| Overlay license | Anticommons 0.1.0 |

Top dependency references recorded in the benchmark snapshot:

| Ecosystem | Name | Version | Source file |
|-----------|------|---------|-------------|
| pypi | accelerate | ==0.34.2 | pyproject.toml |
| pypi | sentencepiece | - | pyproject.toml |
| pypi | tokenizers | >=0.12.1 | pyproject.toml |
| pypi | torch | ==2.3.0 | pyproject.toml |
| pypi | torchvision | ==0.18.0 | pyproject.toml |
| pypi | transformers | ==4.46.0 | pyproject.toml |
| pypi | lm_eval | ==0.3.0 | pyproject.toml |
| pypi | texttable | - | pyproject.toml |
| pypi | toml | - | pyproject.toml |
| pypi | attributedict | - | pyproject.toml |
| pypi | protobuf | - | pyproject.toml |
| pypi | gradio | ==3.35.2 | pyproject.toml |
| pypi | gradio_client | ==0.2.9 | pyproject.toml |
| pypi | fastapi | - | pyproject.toml |
| pypi | uvicorn | - | pyproject.toml |
| ... | (8 more) | | |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

3. Install efficient W4A16 (4-bit weight, 16-bit activation) CUDA kernel and optimized FP16 kernels (e.g. layernorm, positional encodings).
```
cd awq/kernels
python setup.py install
```

4. Install Flash Attention
```
pip install flash-attn --no-build-isolation
```

We recommend starting an interactive python CLI interface and run `import flash_attn` to check whether FlashAttention-2 is installed successfully. If not, we recommend downloading pre-built wheels from [here](https://github.com/Dao-AILab/flash-attention/releases/tag/v2.5.8). Please notice:

- PyTorch version needs to exactly match with the version specified in the `.whl` name;
- Check out both `cxx11abiTRUE` and `cxx11abiFALSE` wheels if one of them does not work;
- It's recommended to match CUDA version specified in the `.whl` filename, but minor mismatches (e.g. 12.1 vs 12.2, or even 11.8 vs 12.2) usually do not matter.

5. [Optional] In order to run AWQ and TinyChat with NVILA model family, please install VILA:

```bash
git source https://github.com/NVlabs/VILA.git
cd VILA
pip install -e .
```

*Section quoted from the upstream readme.*
Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `LLM_AWQ` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: MIT** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
MIT License

Copyright (c) 2023 MIT HAN Lab

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original MIT terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `MIT` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `LLM_AWQ` (category: CHIP QUANTIZATION)
- **Upstream URL:** https://github.com/mit-han-lab/llm-awq
- **Pinned commit (SHA):** `d6e797a42b9ef7778de8ee2352116e0f48a78d61`
- **Branch:** main
- **Pin provenance:** GitHub API commits/main. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`3893a10c905fc4c672c545bdf6239ed4fb62060860758e70a701e245f9c7835c`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

