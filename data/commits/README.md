# `data/commits/` — per-repo AI commit manifests

Each file `<owner>_<repo>_commits.json` lists the AI-attributed commits found
in a single GitHub repository (the input the analysis pipeline reads).

## What's in this folder

This folder contains **two demo files** that ship with the repository so the
smoke-test workflow (`python3 main.py` → option 5 → dashboard) works out of
the box:

- `superagent-ai_superagent_commits.json` — 35 Claude-authored commits (Figure 5)
- `microsoft_data-formulator_commits.json` — 39 Copilot-authored commits (Listing 3)

The full set of 6,299 `<owner>_<repo>_commits.json` files is **not** committed
to Git. Download `commits.zip` from Hugging Face and extract it here.

## Download the full set

**Hugging Face dataset:** <https://huggingface.co/datasets/yueyuel/tech-debt-ai-coding>

```bash
# from the repo root
pip install -U huggingface_hub
hf download yueyuel/tech-debt-ai-coding commits.zip --repo-type dataset --local-dir data/
unzip data/commits.zip -d data/
ls data/commits/*.json | wc -l   # should print 6299 (plus this README)
```

You only need these files to re-run the analysis pipeline from scratch
(**Tier 3**). For **Tier 1** (verify paper numbers) and **Tier 2** (re-aggregate
from saved analyzer output), the contents of this folder are not needed.

## Schema

See the schema section in [`../README.md`](../README.md) for the JSON layout.
