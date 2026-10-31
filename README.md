# solo-lm

One person with AI coding agents trains a ~2B-parameter language model end to end: data, tokenizer, pretraining, RL (reinforcement learning) post-training, evaluation, release on Hugging Face (Ancorro). Compute is free OSU (Oregon State University) HPC (high-performance computing) H100 GPUs.

**Comparison point.** Karpathy's nanochat d32: 1.88B parameters, 37.6B tokens, about 31 hours on 8 H100s, CORE 0.317, GSM8K 12.7% after SFT (supervised fine-tuning) and 19.9% after RL ([discussion](https://github.com/karpathy/nanochat/discussions/8)). CORE is the DCLM (DataComp for Language Models) average of 22 tasks. Published CORE for open models: OLMo-1B 29.7, SmolLM-1.7B 36.3, DCLM-1B 45.2 ([DCLM-1B card](https://huggingface.co/TRI-ML/DCLM-1B)).

**Question.** Starting from one base model with known, decontaminated training data, does multi-agent self-play RL on text games (as in [SPIRAL](https://arxiv.org/abs/2506.24119), shown on 4B models) transfer to reasoning benchmarks at ~2B scale, compared with direct math RL?

Dated log: [LOG.md](LOG.md). Jobs: [notes/jobs.md](notes/jobs.md).
