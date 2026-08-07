# Anonymous Review Submission Checklist

Use this checklist before uploading the supplementary package to the conference submission system.

## Anonymity

- [ ] Remove personal GitHub URLs from the main paper.
- [ ] Remove usernames, local paths, and institution names from logs.
- [ ] Remove API keys and service account identifiers.
- [ ] Remove commit history if uploading a ZIP.
- [ ] Replace public repository links with: `anonymous supplementary package`.

## Appendix completeness

- [ ] Appendix PDF exists.
- [ ] Experimental setup and hyperparameters are complete.
- [ ] Condition matrix is complete.
- [ ] Per-seed and per-round results are included.
- [ ] CREATE pseudocode is included.
- [ ] Reward interface and validation rules are included.
- [ ] Prompt templates are included or clearly deferred for a later revision.
- [ ] Component evidence tables and heatmaps are included.
- [ ] Reward-lineage case studies are included.
- [ ] Representative reward programs are included.
- [ ] Figure source data and plotting scripts are included.

## Reproducibility

- [ ] `requirements.txt` has exact versions.
- [ ] `environment.yml` has exact versions.
- [ ] Run commands are documented.
- [ ] Table reproduction scripts are provided.
- [ ] Figure reproduction scripts are provided.
- [ ] All `TBD` entries are either filled or explicitly justified.

## Paper consistency

- [ ] The main paper's claims match the supplementary tables.
- [ ] The solved counts match per-seed results.
- [ ] The training budgets match condition definitions.
- [ ] The appendix contains every item promised in the main paper.
