# Command Line Interface — LLM_AWQ

**Upstream:** https://github.com/mit-han-lab/llm-awq

## Anticloud CLI

```bash
# Install
pip install anticloud-llm-awq

# Run offline with PAX inference
anticloud-llm-awq --offline --pax-local

# Run with AIOSS logging
anticloud-llm-awq --aioss-log ./ledger.jsonl

# Single binary (after build)
./llm_awq --config config.yaml
```

## Options

| Flag | Description |
| --- | --- |
| `--offline` | Disable all network calls |
| `--pax-local` | Use local PAX inference at 127.0.0.1:11434 |
| `--aioss-log PATH` | Write AIOSS audit chain to PATH |
| `--encrypt` | Enable AES-256 at rest for output files |
| `--gpu` | Force GPU inference |
| `--cpu` | Force CPU inference |
| `--config PATH` | Load configuration from YAML file |
