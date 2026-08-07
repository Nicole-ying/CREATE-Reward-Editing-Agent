# Figures and Source Data

This directory should contain supplementary figures, source data, and plotting scripts.

## Recommended contents

```text
figure_source_data/
  fig2_budget_curve.csv
  fig3_ablation.csv
  fig4_repair_trajectories.csv
supplementary_figures/
  activation_rate_heatmaps/
  magnitude_share_heatmaps/
  extra_lineage_traces/
plotting_scripts/
  plot_budget_curve.py
  plot_ablation.py
  plot_repair_trajectories.py
  plot_component_heatmaps.py
```

## Figure requirements

- Every main-paper figure should have source data.
- Every supplementary figure should be reproducible from a script.
- Do not include screenshots when vector graphics or source data are available.
- Captions should state what claim the figure supports.

## Priority figures

1. Main budget curve source data.
2. Held-out and ablation figure source data.
3. Seed 0 and seed 3 repair traces.
4. Activation-rate heatmaps.
5. Magnitude-share heatmaps.
