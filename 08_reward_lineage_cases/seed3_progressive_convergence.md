# Seed 3 Case Study: Progressive Convergence

This case expands the representative trajectory described in the main paper.

## Main-paper summary

Seed 3 improves from approximately `-20` to `148` after an L2 refactor replaces an absolute-distance penalty with potential-difference approach shaping. The evidence organizer reports that the absolute-distance term provides an uninformative gradient: it penalizes distance regardless of whether the lander is approaching the pad. A later overly restrictive adjustment causes temporary regression. Intervention memory localizes the regression to the most recent contact-semantic change. A subsequent L2 edit reconstructs the contact semantic as a reachable gradient from single-leg contact toward simultaneous stable contact; the next policy reaches `254`.

## Table to finalize from logs

| Round | Fitness | Best-so-far | Main symptom | Diagnosed semantic failure | Edit level | Actual edit | Expected next change | Observed outcome |
|---:|---:|---:|---|---|---|---|---|---|
| 1 | approx. -20 | TBD | Initial failure | TBD | TBD | TBD | TBD | Not solved |
| 2 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| 3 | approx. 148 | 148 | Improved but not solved | Absolute-distance term weakly directional | L2 | Potential-difference approach shaping | Improve approach gradient | Improved |
| 4 | approx. 254 | 254 | Contact semantic repaired | Need reachable gradient from partial to stable contact | L2 | Single-leg to simultaneous stable-contact gradient | Improve landing reliability | Solved |

## Evidence to attach

- Component activation-rate table.
- Magnitude-share table.
- Reward code before approach-shaping refactor.
- Reward code after potential-difference approach shaping.
- Reward code after contact-semantic repair.
- Native evaluation trace.
- Memory comparison showing localization of regression.
