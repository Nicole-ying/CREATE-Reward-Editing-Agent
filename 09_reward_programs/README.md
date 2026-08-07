# Reward Programs

This directory should contain representative and complete reward programs produced during the reward-search process.

## Recommended layout

```text
lunarlander/
  seed0/
    round01_reward.py
    round02_reward.py
    ...
    best_reward.py
  seed1/
  seed2/
  seed3/
  seed4/
bipedalwalker/
  seed0/
  seed1/
  seed2/
  seed3/
  seed4/
```

## What to include in appendix PDF

The appendix PDF should not contain every reward program in full if this makes it unreadable. Instead, include representative examples:

1. Initial reward.
2. Failed reward before repair.
3. L1 calibration example.
4. L2 structural refactor example.
5. Best final reward.

The complete reward files can remain in this repository with a table mapping each reward file to environment, condition, seed, round, fitness, and diagnostic note.

## Metadata schema

Create a CSV such as `reward_program_index.csv` with:

```text
environment,condition,lineage_index,round,file,fitness,best_so_far,is_best,edit_level,diagnostic_note,code_hash
```
