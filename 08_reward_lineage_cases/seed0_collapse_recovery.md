# Seed 0 Case Study: Collapse and Recovery

This case expands the representative trajectory described in the main paper.

## Main-paper summary

Rounds 1--6 explore coefficient scaling, sparse-to-dense conversion, and mathematical-form changes without solving the task. Round 7 replaces a state-based proximity signal with differential progress shaping and collapses to approximately `-389`. The evidence organizer reveals the mechanism: the new signal is near zero when the lander is stationary and becomes negative under disturbance, actively penalizing stability. The intervention memory retains the pre-collapse reward in the best archive. The editor then applies an L2 intervention in round 8: restore a state-based formulation with an altitude factor that suppresses reward exploitation. Fitness rises to `224`. The next exploratory reward falls to approximately `-612`, while the best archive preserves the solved reward.

## Table to finalize from logs

| Round | Fitness | Best-so-far | Main symptom | Diagnosed semantic failure | Edit level | Actual edit | Expected next change | Observed outcome |
|---:|---:|---:|---|---|---|---|---|---|
| 1 | TBD | TBD | Initial failure | TBD | TBD | TBD | TBD | TBD |
| 2 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| 3 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| 4 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| 5 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| 6 | TBD | TBD | Not solved | TBD | TBD | TBD | TBD | TBD |
| 7 | approx. -389 | retained prior best | Collapse after differential progress shaping | Progress signal lacks stable reference frame | L2 diagnosis for next edit | Replace state-based proximity with differential progress shaping | TBD | Collapse |
| 8 | approx. 224 | solved | Recovery | Need stable state-based signal with anti-exploitation factor | L2 | Restore state-based formulation plus altitude factor | Recover controlled approach/landing | Solved |
| 9 | approx. -612 | 224 retained | Exploratory regression | TBD | TBD | TBD | TBD | Best archive prevents regression |

## Evidence to attach

- Component activation-rate table.
- Magnitude-share table.
- Reward code before collapse.
- Reward code at collapse.
- Reward code after L2 recovery.
- Native evaluation trace.
- Best-archive update log.
