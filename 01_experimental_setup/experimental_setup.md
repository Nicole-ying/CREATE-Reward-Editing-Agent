# Experimental Setup and Hyperparameters

This file summarizes the experimental settings stated in the main paper and marks missing reproducibility details as `TBD`.

## Environments

| Environment | Role | Action space | Training budget per candidate | Native solving threshold |
|---|---|---:|---:|---:|
| LunarLander-v3 | Primary benchmark for baseline comparison and mechanism ablation | Discrete | 1,000,000 environment steps | 200 |
| BipedalWalker-v3 | Secondary validation on continuous-action locomotion | Continuous | 5,000,000 environment steps | 300 |

## Policy optimizer

All reward programs train a freshly initialized PPO policy through Stable-Baselines3.

| Item | Value |
|---|---|
| RL algorithm | PPO |
| Implementation | Stable-Baselines3 |
| Search fitness | Mean undiscounted native episodic return over 20 fixed evaluation episodes |
| Test fitness | Mean native episodic return over 100 unseen evaluation episodes |
| Native objective | Untouched environment reward, not generated reward |
| Generated reward use | Used only for policy optimization |

## LLM backend

| Item | Value |
|---|---|
| LunarLander LLM backbone | DeepSeek V4 Pro |
| BipedalWalker LLM backbone | TBD |
| Temperature | TBD |
| Top-p | TBD |
| Max output tokens | TBD |
| Retry policy | TBD |
| Code-validation feedback policy | TBD |

## Random seeds and lineages

| Item | Value |
|---|---|
| LunarLander lineages per condition | 5 |
| Max reward evaluations per LunarLander lineage | 10 |
| BipedalWalker lineages | 5 |
| Evaluation seeds | TBD |
| Training seeds | TBD |

## Software versions

| Package | Version |
|---|---|
| Python | TBD |
| Gymnasium | TBD |
| Stable-Baselines3 | TBD |
| PyTorch | TBD |
| NumPy | TBD |
| CUDA | TBD |

## Hardware and runtime

| Item | Value |
|---|---|
| CPU | TBD |
| GPU | TBD |
| RAM | TBD |
| Operating system | TBD |
| Approximate training time per LunarLander candidate | TBD |
| Approximate training time per BipedalWalker candidate | TBD |

## Notes for finalization

Before submission, replace all `TBD` entries with exact values from experiment logs or environment files. Avoid reporting only aggregate means; keep the mapping from each result table to its seeds and run IDs.
