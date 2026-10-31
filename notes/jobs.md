# Submitted jobs

| Date | Job | What | Where | Log |
|---|---|---|---|---|
| 2026-10-31 | 21995230 probe8 | 10 min, 8 GPU queue-wait probe | hpc dgxh (excl. dgxh-1) | /nfs/hpc/share/cleasbys/minilm/logs/probe8-21995230.out |
| 2026-10-31 | 21995231 probe4 | 10 min, 4 GPU queue-wait probe | hpc dgxh (excl. dgxh-1) | /nfs/hpc/share/cleasbys/minilm/logs/probe4-21995231.out |
| 2026-10-31 | 21995333 setup | venv, 300 ClimbMix shards, tokenizer train/eval | hpc share | /nfs/hpc/share/cleasbys/minilm/logs/setup-21995333.out |
| 2026-10-31 | 21995343 smoke | d12 60-step train, save at 30, resume test (after setup) | hpc dgxh 1 GPU | /nfs/hpc/share/cleasbys/minilm/logs/smoke-21995343.out |

Storage rule: base (non-instruct) checkpoints stay in /nfs/hpc/share/cleasbys/minilm/base/base_checkpoints and are copied to private HF repo Ancorro/solo-lm-base after each pretraining run.
