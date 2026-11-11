# solo-lm

One person with AI coding agents trains a ~2B-parameter language model end to end: data, tokenizer, pretraining, RL (reinforcement learning) post-training, evaluation, release on Hugging Face (Ancorro). Compute is free OSU (Oregon State University) HPC (high-performance computing) H100 GPUs.

**Comparison point.** Karpathy's nanochat d32: 1.88B parameters, 37.6B tokens, about 31 hours on 8 H100s, CORE 0.317, GSM8K 12.7% after SFT (supervised fine-tuning) and 19.9% after RL ([discussion](https://github.com/karpathy/nanochat/discussions/8)). CORE is the DCLM (DataComp for Language Models) average of 22 tasks. Published CORE for open models: OLMo-1B 29.7, SmolLM-1.7B 36.3, DCLM-1B 45.2 ([DCLM-1B card](https://huggingface.co/TRI-ML/DCLM-1B)).

**Question.** Starting from one base model with known, decontaminated training data, does multi-agent self-play RL on text games (as in [SPIRAL](https://arxiv.org/abs/2506.24119), shown on 4B models) transfer to reasoning benchmarks at ~2B scale, compared with direct math RL?

Dated log: [LOG.md](LOG.md).

## Sources and attribution

- [nanochat](https://github.com/karpathy/nanochat), Andrej Karpathy: training code and recipe (d24/d26), and the d32 comparison point ([discussion 8](https://github.com/karpathy/nanochat/discussions/8), [leaderboard](https://github.com/karpathy/nanochat/blob/master/dev/LEADERBOARD.md)).
- [ClimbMix](https://huggingface.co/datasets/nvidia/ClimbMix), NVIDIA: pretraining data.
- [SPIRAL](https://arxiv.org/abs/2506.24119): multi-agent self-play RL on text games.
- [DCLM-1B](https://huggingface.co/TRI-ML/DCLM-1B), Toyota Research Institute and the DataComp team: CORE metric and published CORE scores.
- [SmolLM2](https://arxiv.org/abs/2502.02737), Hugging Face: comparison model.

## Repo rules

This repo can be made public at any time, history included.

- No secrets: keys go in `.env` (untracked); `.env.example` lists the names only.
- No private information: cluster paths, host names, run logs, costs and personal notes go in `private/`, which is untracked and backed up outside git.
- Large data stays out of git; a script downloads it.
- Sources: add each new source to "Sources and attribution" in the commit that starts using it.
- Keep the real history: no squashing or force-pushing published commits.
