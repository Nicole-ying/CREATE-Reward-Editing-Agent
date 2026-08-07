# Component-Level Evidence

The main paper states that activation-rate and magnitude-share heatmaps are provided in the supplementary material. This directory should contain the evidence supporting those claims.

## Recommended contents

```text
activation_rate_tables/
magnitude_share_tables/
dominance_rankings/
heatmaps/
component_diagnosis_tables/
```

## Required tables

For each representative lineage, prepare a table with the following fields:

| Field | Description |
|---|---|
| `environment` | LunarLander-v3 or BipedalWalker-v3. |
| `condition` | CREATE or ablation condition. |
| `lineage_index` | Search lineage / seed index. |
| `round` | Reward-editing round. |
| `component_name` | Reward component label. |
| `episode_sum_mean` | Mean component contribution. |
| `activation_rate` | Fraction of steps where the component is active. |
| `magnitude_share` | Share of absolute reward magnitude. |
| `dominance_rank` | Rank by magnitude or diagnostic importance. |
| `diagnostic_note` | Inactive, over-dominant, weak, unstable, useful, etc. |

## Priority evidence to include

1. Seed 0 collapse/recovery lineage.
2. Seed 3 progressive convergence lineage.
3. Any lineage showing evidence-poor failure or unconstrained-edit failure.

## Figure guidance

- Use heatmaps for activation rates and magnitude shares.
- Keep one row per reward version and one column per component.
- Use clear captions explaining what diagnosis the heatmap supports.
- Do not infer missing values; mark missing entries as `NA`.
