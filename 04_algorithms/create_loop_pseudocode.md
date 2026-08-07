# Algorithm 1: CREATE Reward-Editing Loop

This pseudocode expands the high-level observe--reflect--act equations in the main paper into an auditable experimental procedure.

```text
Input:
  Environment E
  Native evaluation reward r_env
  Initial task description d
  Maximum reward evaluations K
  Policy-training budget B
  Evaluation episode count N
  Solving threshold tau

Initialize:
  R_0 <- RewardInitialization(d)
  M_0 <- empty intervention memory
  A_best <- None
  J_best <- -infinity

For t = 0, 1, ..., K-1:
  1. Validate R_t against reward interface and runtime checks.
     If invalid:
       record invalid-code observation in M_t
       revise without consuming PPO budget
       continue

  2. Train policy pi_t using generated reward R_t for B environment steps.

  3. Evaluate pi_t using untouched native reward r_env over N episodes.
     Obtain native fitness J_t and episode-level outcomes.

  4. Log named reward-component statistics during training/evaluation.
     Include activation rates, magnitude shares, component sums,
     termination patterns, episode lengths, and temporal trends.

  5. O_t <- EvidenceOrganizer(D_t, M_t, A_best)
     The organizer summarizes evidence but does not choose an edit.

  6. If J_t > J_best:
       A_best <- (R_t, pi_t, J_t, t)
       J_best <- J_t

  7. If J_best >= tau:
       stop and return A_best

  8. (h_t, q_t, ell_t, Delta_t) <- RewardEditor(R_t, O_t, M_t, A_best)
     The editor identifies one principal semantic failure q_t,
     selects an edit level ell_t in {L1, L2, L3}, and proposes a bounded edit.

  9. R_{t+1} <- ApplyEdit(R_t, Delta_t)

  10. Append to M_{t+1}:
       observation O_t,
       hypothesis h_t,
       target semantic q_t,
       edit level ell_t,
       code diff or reward version,
       expected next change,
       observed outcome when available.

Return A_best
```

## Implementation notes

- The policy is optimized with the generated reward, but reward quality is selected only by native environment return.
- The best archive is separate from the active lineage, preventing exploratory regressions from overwriting the best reward found so far.
- The bounded-edit rule is used to make each expensive training run interpretable as a focused intervention test.
