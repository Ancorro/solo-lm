# Log

## 2026-10-31 (day 1)
- Read sources: nanochat d32 report ([discussion 8](https://github.com/karpathy/nanochat/discussions/8)), nanochat [leaderboard](https://github.com/karpathy/nanochat/blob/master/dev/LEADERBOARD.md) (GPT-2 CORE 0.2565 reached in 1.65 h on 8 H100s, 2026-03-14), [DCLM-1B card](https://huggingface.co/TRI-ML/DCLM-1B), [SmolLM2 paper](https://arxiv.org/abs/2502.02737) (1.7B on 11T tokens), [SPIRAL](https://arxiv.org/abs/2506.24119).
- Note: nanochat master now trains on ClimbMix with later speedups; d32 used FineWeb-Edu. Comparisons to d32 will be at matched FLOPs (floating-point operations) and state the recipe difference.
- HPC H100 partition: 4 nodes; three have 8 x H100 80 GB, one has 16 x 40 GB slices (excluded). QoS (quality of service) cap 8 GPUs per user, 48 h per job. Queue: about 120 pending jobs.
- Submitted 10-minute 8-GPU and 4-GPU probes to measure wait. Slurm estimates the 8-GPU start at 2026-11-01 09:59.
- Shared storage: 339 GB free of 1.5 TB, no per-user quota. Tokenized data for ~38B tokens should fit.
