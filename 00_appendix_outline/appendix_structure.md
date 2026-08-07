# Appendix Structure

Recommended title:

**Appendix: Supplementary Material for CREATE: A Closed-Loop Reward Editing Agent with Training Evidence for Reinforcement Learning**

The appendix should prioritize experimental credibility before prompt details. The main paper already states that full prompts, model settings, hyperparameters, per-seed traces, and environment configurations are provided in the supplementary material. It also states that activation-rate and magnitude-share heatmaps are in the supplementary material. Therefore, the supplement should make these items easy to find.

## Recommended order

### Appendix A. Supplementary Overview and Reproducibility Map
Explain what the appendix contains and how each section supports the claims in the main paper.

### Appendix B. Experimental Setup and Hyperparameters
Move this early. Reviewers need to evaluate the experimental budget before reading prompt details.

Include:
- Gymnasium environments and versions.
- Stable-Baselines3 and PPO settings.
- Training steps per candidate.
- Evaluation episodes.
- Task thresholds.
- Random seeds.
- LLM backend and decoding settings.
- Hardware and runtime.

### Appendix C. Compared Conditions and Ablation Protocols
Define each matched-budget condition and list what evidence, memory, and editing constraints it uses.

### Appendix D. Full Per-Seed and Per-Round Results
Move this early. Aggregate tables in the main paper should be backed by per-seed/per-round data.

Include:
- LunarLander-v3 per-lineage traces.
- LunarLander-v3 held-out test results.
- BipedalWalker-v3 per-version results.
- Solved rounds and best-so-far curves.

### Appendix E. CREATE Algorithms and Pseudocode
Give the complete control flow for the reward-editing loop.

### Appendix F. Reward Program Interface and Validation Rules
Define the reward-code interface, component logging schema, and validation checks.

### Appendix G. Prompt Templates
Prompt templates should be included later than the experiment settings. This directory is intentionally not filled yet.

### Appendix H. Component-Level Evidence and Diagnostic Tables
Include activation-rate tables, magnitude-share tables, dominance rankings, and heatmaps.

### Appendix I. Reward-Lineage Case Studies
Expand seed 0 collapse/recovery and seed 3 progressive convergence from the main paper.

### Appendix J. Reward Programs and Representative Edits
Show representative reward versions and link them to the corresponding edit decisions.

### Appendix K. Additional Figures and Source Data
Provide figure source data and plotting scripts.

## Review-stage note

During anonymous review, remove or mask author-identifying repository URLs. Use an anonymized supplementary package instead of a public personal GitHub link.
