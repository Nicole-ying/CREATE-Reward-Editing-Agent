# Reward Program Interface and Validation Rules

This section should document the executable reward-code contract used in CREATE.

## Reward function contract

Each generated reward program should expose a function compatible with the environment-specific reward wrapper.

Minimum expected outputs:

1. A finite scalar generated reward used for policy optimization.
2. A dictionary of named component values used for logging and diagnosis.

Example abstract form:

```python
def compute_reward(...):
    # environment-specific state/action/transition inputs
    component_a = ...
    component_b = ...
    reward = component_a + component_b
    components = {
        "component_a": component_a,
        "component_b": component_b,
    }
    return reward, components
```

Do not use this abstract signature as the final implementation specification. Replace it with the exact LunarLander-v3 and BipedalWalker-v3 wrapper signatures from the experiment code.

## Component logging schema

For each named component, logs should support:

| Field | Purpose |
|---|---|
| `component_name` | Human-readable semantic label. |
| `episode_sum` | Total contribution over an episode. |
| `activation_rate` | Fraction of steps with non-negligible component value. |
| `magnitude_share` | Share of absolute reward magnitude. |
| `sign` | Positive, negative, or mixed contribution. |
| `dominance_rank` | Ranking by magnitude or behavioral relevance. |
| `notes` | Optional diagnosis or lineage note. |

## Validation checks

Before spending PPO training budget, a generated reward should pass:

- Python syntax check.
- Required function/interface check.
- Runtime execution on sampled transitions.
- Finite scalar reward check.
- Finite component value check.
- Component dictionary presence check.
- No missing imports or unavailable dependencies.
- No mutation of environment internals outside the reward wrapper.
- Optional duplicate-code hash check.

## Invalid reward handling

An invalid reward should not consume a full policy-training run. Instead, the failure message should be treated as an observation and returned to the reward-editing step.

## Items to fill from code

- Exact `compute_reward` signature for LunarLander-v3.
- Exact `compute_reward` signature for BipedalWalker-v3.
- Runtime sample-transition construction.
- Component logging implementation path.
- Code hash / duplicate detection implementation path.
