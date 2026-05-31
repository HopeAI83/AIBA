# AIBA-EHR Reproducibility Repository

This repository contains the public reproducibility package for the manuscript:

**AI-Accelerated Blockchain Architecture for Efficient and Secure Electronic Healthcare Record Exchange**

Scientific Reports submission ID: `b0d8734d-aa17-4036-b6d0-57cecdbfc94f`

## Repository purpose

This repository provides the code, synthetic dataset, configuration files, result tables, figures, and reproduction scripts required to inspect and reproduce the experimental materials reported in the revised manuscript.

The repository is prepared for **GitHub-only public availability**. No Zenodo, Figshare, or other DOI archive is claimed in this version.

## Contents

```text
configs/        Experiment configuration files
src/aiba_ehr/   Python source code for AIBA-EHR modules
scripts/        Reproduction and verification scripts
data/           Synthetic EHR access-event dataset and metadata
results/        Result tables used for manuscript reporting
figures/        Generated figures and manuscript figure copies
docs/           Documentation, data card, codebook, and manuscript statements
```

## Editor-required reproducibility components

| Required component | Repository location |
|---|---|
| ChainSimEnv blockchain simulation environment | `src/aiba_ehr/chainsim_env.py` |
| PPO reinforcement learning agent | `src/aiba_ehr/ppo_agent.py` |
| TCN+AM anomaly detection module | `src/aiba_ehr/tcn_attention_model.py` |
| Exact public synthetic dataset used for repository release | `data/synthetic_ehr_access_events_120000.csv` |
| Dataset dictionary | `data/data_dictionary.csv` |
| Cross-validation fold assignments | `data/cv_fold_assignments.csv` |
| Checksum manifest | `data/SHA256SUMS.txt` |
| Main reproduction script | `scripts/reproduce_all_results.py` |
| Repository verification script | `scripts/verify_repository_readiness.py` |

## Dataset summary

The dataset file `data/synthetic_ehr_access_events_120000.csv` contains 120,000 synthetic EHR access events generated with deterministic seed control.

- Number of rows: 120,000
- Feature columns: 15 model features
- Metadata columns: `event_id`, `event_timestamp`
- Label column: `is_anomaly`
- Random seed: 42
- No real patient data, protected health information, identifiable health information, or human-subject data are included.

## Installation

Create a Python environment and install the required packages:

```bash
python -m venv .venv
source .venv/bin/activate  # Linux/macOS
pip install -r requirements.txt
```

Alternatively, using Conda:

```bash
conda env create -f environment.yml
conda activate aiba-ehr
```

## Reproduce repository results

Run:

```bash
python scripts/reproduce_all_results.py
```

Then verify repository readiness:

```bash
python scripts/verify_repository_readiness.py
```

Expected verification outcome:

```text
AIBA-EHR repository verification passed.
Dataset rows: 120000
Repository readiness check PASSED.
```

## Important reproducibility note

The synthetic dataset in this GitHub repository is the public dataset distributed with the reproducibility package. Because the previously used original CSV was not available in the uploaded revision materials, this repository uses a deterministic public synthetic dataset generated from the documented schema, seed, and experimental configuration. Manuscript availability statements should refer to this GitHub repository as the public source of the dataset and code.

## License

- Code: MIT License, see `LICENSE`.
- Synthetic data: see `DATA_LICENSE.md`.

## Citation

Please cite the manuscript and this GitHub repository URL when using the code or synthetic dataset.
