# Log

## 2026-10-31 (day 1)
- Read sources: nanochat d32 report ([discussion 8](https://github.com/karpathy/nanochat/discussions/8)), nanochat [leaderboard](https://github.com/karpathy/nanochat/blob/master/dev/LEADERBOARD.md) (GPT-2 CORE 0.2565 reached in 1.65 h on 8 H100s, 2026-03-14), [DCLM-1B card](https://huggingface.co/TRI-ML/DCLM-1B), [SmolLM2 paper](https://arxiv.org/abs/2502.02737) (1.7B on 11T tokens), [SPIRAL](https://arxiv.org/abs/2506.24119).
- Note: nanochat master now trains on ClimbMix with later speedups; d32 used FineWeb-Edu. Comparisons to d32 will be at matched FLOPs (floating-point operations) and state the recipe difference.
- HPC dgxh: 4 nodes; dgxh-2..4 have 8 x H100 80 GB, dgxh-1 has 16 x 40 GB slices (excluded). QoS (quality of service) cap 8 GPUs per user, 48 h per job. Queue: about 120 pending jobs.
- Submitted 10-minute 8-GPU and 4-GPU probes to measure wait. Slurm estimates the 8-GPU start at 2026-11-01 09:59.
- Shared storage /nfs/hpc/share: 339 GB free of 1.5 TB, no per-user quota. Tokenized data for ~38B tokens should fit.
- Decision (Steven): ~1B class, nanochat d24/d26 (the size of the leaderboard runs). More compute goes to RL variants.
- Cloned nanochat master (2026-07-03 commit) to /nfs/hpc/share/cleasbys/minilm/nanochat. Submitted CPU setup job: uv venv (torch 2.9.1, CUDA 12.8), 300 ClimbMix shards, tokenizer training (32768 vocab).
- Steven: keep the base (non-instruct) weights in persistent storage. Base checkpoints are written to /nfs/hpc/share/cleasbys/minilm/base/base_checkpoints (shared disk, persistent) and each finished base model is uploaded to a private Hugging Face repo, Ancorro/solo-lm-base, as an off-cluster copy.
- Submitted 1-GPU smoke test (d12, 60 steps, FP8, save at 30, then resume from 30), queued after setup.
- Setup job finished: torch 2.9.1+cu128 venv, 301 ClimbMix shards (26 GB), tokenizer with 32,768 tokens trained. nanochat's d24 leaderboard run used ~170 shards, so 300 covers d24/d26.
- Smoke test is pending behind 1-GPU jobs (priority). 8-GPU probe still estimated 2026-11-01 09:59.
