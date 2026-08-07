# CREATE Reward Editing Agent

This repository collects supplementary material for the paper:

**CREATE: A Closed-Loop Reward Editing Agent with Training Evidence for Reinforcement Learning**

The repository is organized as a reviewer-facing supplement rather than as a general software package. It is intended to contain the appendix PDF/source, experimental settings, ablation definitions, per-seed and per-round results, pseudocode, reward-interface details, component-level evidence, reward-lineage case studies, representative reward programs, and figure source data.

## Review-stage anonymity

For anonymous submission, do **not** cite this public GitHub URL directly in the paper. Submit an anonymized ZIP/PDF package through the conference submission system. The public URL can be added after acceptance or in the camera-ready version.

Recommended review-stage wording:

> Code, prompts, and supplementary materials are provided in the anonymous supplementary package.

## Repository map

| Directory | Purpose |
|---|---|
| `00_appendix_outline/` | Appendix structure and reproducibility map. |
| `01_experimental_setup/` | Environment, PPO, evaluation, LLM, hardware, and runtime settings. |
| `02_condition_definitions/` | Matched-budget conditions and ablation protocols. |
| `03_full_results/` | Aggregate results, per-seed/per-round schemas, and reproducibility tables. |
| `04_algorithms/` | Pseudocode for CREATE, evidence organization, bounded editing, validation, memory, and best archive. |
| `05_reward_interface_and_validation/` | Reward-code interface, component logging schema, and code validation checks. |
| `06_prompts/` | Prompt templates. This directory is intentionally left as a placeholder for now. |
| `07_component_evidence/` | Activation-rate, magnitude-share, dominance, and component-diagnosis evidence. |
| `08_reward_lineage_cases/` | Case studies explaining how evidence becomes a reward edit. |
| `09_reward_programs/` | Representative and full reward programs by environment and lineage. |
| `10_figures_and_source_data/` | Supplementary figures, source data, and plotting scripts. |

## Current status

This repository currently contains the supplement structure and paper-derived content that can be filled without touching the prompt templates. Items marked `TBD` require exact experimental logs, package versions, hardware information, or raw run outputs before final submission.
