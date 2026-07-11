# tiny

A master repository for the `tiny_*` family of projects — small, focused, from-scratch implementations for learning and experimentation.

## Why "tiny"?

Each sub-repo takes one domain and rebuilds its core ideas with minimal code and minimal dependencies. The goal is not production readiness — it's understanding. If you can implement it small, you actually understand it.

- **Minimal**: no framework magic; the algorithm is the code you read.
- **From scratch**: key components are implemented by hand before reaching for a library.
- **Self-contained**: each repo runs on its own with simple examples.

## Sub-repositories

| Directory | Repository | Description | Status |
|---|---|---|---|
| [ml/](ml/) | [tiny_ml](https://github.com/gzhang71/tiny_ml) | Machine learning and deep learning fundamentals — transformers, attention variants (incl. FlashAttention), classic models | 🟢 Active |
| [rag/](rag/) | [tiny_rag](https://github.com/gzhang71/tiny_rag) | Retrieval-augmented generation — ingestion, chunking, retrieval channels, modular query pipeline | 🟢 Active |
| [causal_inference/](causal_inference/) | [tiny_causal_inference](https://github.com/gzhang71/tiny_causal_inference) | Causal inference methods — propensity score matching and friends | 🟢 Active |
| [rl/](rl/) | [tiny_rl](https://github.com/gzhang71/tiny_rl) | Reinforcement learning for LLM post-training — SFT, PPO, GRPO, DPO | 🟢 Active |

Status legend: 🟢 Active · 🟡 WIP · ⚪ Planned

## Getting all repos at once

The sub-repos are included here as git submodules:

```bash
git clone --recursive https://github.com/gzhang71/tiny.git

# or, if already cloned:
git submodule update --init --recursive
```

Each submodule pin is a snapshot of the sub-repo at a specific commit. A [scheduled GitHub Action](.github/workflows/bump-submodules.yml) bumps all pins to the latest commits daily; to pull immediately, run `git submodule update --remote`.

## More

- [ROADMAP.md](ROADMAP.md) — planned and candidate future `tiny_*` projects
- [notes/](notes/) — cross-cutting learning notes that don't belong to any single sub-repo

## License

The `tiny` series is released under the [MIT License](LICENSE).
