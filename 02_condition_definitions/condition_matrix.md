# Condition Definitions and Ablation Protocols

The LunarLander-v3 experiments compare five conditions under a matched reward-evaluation budget. Each condition uses the same environment description, reward interface, code checks, PPO budget, and LLM backbone unless explicitly ablated.

## Condition matrix

| Condition | Max evaluations per lineage | Independent candidates | Sequential revision | Persistent memory | Evidence organizer | Activation / magnitude evidence | Temporal / cross-round evidence | Bounded L1/L2/L3 editing | Best archive |
|---|---:|---|---|---|---|---|---|---|---|
| Independent-10 | 10 | Yes | No | No | No | No | No | No | Post-hoc best only |
| Stateless iterative revision | 10 | No | Yes | No | No | No | No | No | No persistent best archive in editor |
| CREATE w/o evidence enrichment | 10 | No | Yes | Yes | Removed | No | No | Yes | Yes |
| CREATE w/o hierarchical editing | 10 | No | Yes | Yes | Yes | Yes | Yes | Removed | Yes |
| CREATE | 10 | No | Yes | Yes | Yes | Yes | Yes | Yes | Yes |

## Shared setup

- Primary environment: LunarLander-v3.
- Policy optimizer: PPO through Stable-Baselines3.
- Training budget per candidate: 1,000,000 environment steps.
- Search fitness: mean undiscounted native return over 20 fixed evaluation episodes.
- Test fitness: native return over 100 unseen evaluation episodes after reward selection.
- Native solving threshold: 200.
- LLM backbone for LunarLander conditions: DeepSeek V4 Pro.

## Notes for finalization

The appendix should include exact seeds, run IDs, and prompt variants for each condition. Prompt files are intentionally not populated yet in this repository.
