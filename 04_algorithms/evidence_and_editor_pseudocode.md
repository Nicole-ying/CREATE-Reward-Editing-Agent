# Algorithms 2--4: Evidence, Editing, and Archive Updates

## Algorithm 2: Tool-Assisted Evidence Organizer

```text
Input:
  Training and evaluation record D_t
  Current reward code R_t
  Intervention memory M_t
  Best archive A_best

Output:
  Structured observation O_t

Procedure:
  1. Extract native outcomes:
       mean native return, episode lengths, termination modes,
       solved rate or threshold crossing.

  2. Extract reward-component statistics:
       component episode sums,
       activation rates,
       absolute magnitude shares,
       signs and dominance rankings.

  3. Extract temporal and lineage evidence:
       trend relative to earlier versions,
       difference from parent reward,
       previous edits that succeeded or failed,
       best-so-far reward and current active reward.

  4. Produce O_t as a structured summary.

Constraint:
  The evidence organizer reports what happened. It does not choose the edit,
  recommend coefficients, or rewrite reward code.
```

## Algorithm 3: Bounded Semantic Reward Editor

```text
Input:
  Current reward code R_t
  Structured observation O_t
  Intervention memory M_t
  Best archive A_best

Output:
  Reward edit action A_t = (target semantic q_t, edit level ell_t, edit Delta_t)

Procedure:
  1. Identify the principal observed failure.

  2. Map the failure to one reward semantic q_t.
     Examples: approach shaping, stability, contact/landing event,
     fuel/action cost, crash penalty, timeout behavior.

  3. Select edit level ell_t:
       L1: coefficient, threshold, or gate calibration.
       L2: add, remove, or refactor the mathematical form of one semantic.
       L3: redesign reward decomposition after repeated local failure.

  4. Restrict Delta_t to the components implementing q_t.
     Do not mix independent reward intents in the same ordinary edit.

  5. State the expected next-run change and the main counter-risk.

  6. Generate the revised reward code.
```

## Algorithm 4: Validation, Memory Update, and Best Archive

```text
Input:
  Proposed reward code R_{t+1}
  Previous memory M_t
  Current result J_t
  Current best archive A_best

Procedure:
  1. Validate syntax and reward interface.
  2. Execute the reward on sampled transitions.
  3. Check that reward scalar and component values are finite.
  4. Reject invalid rewards before consuming a PPO training budget.
  5. After valid training and native evaluation, append the transition to memory.
  6. If native fitness improves over the archive, update A_best.
  7. Return the active next reward and the updated archive.
```
