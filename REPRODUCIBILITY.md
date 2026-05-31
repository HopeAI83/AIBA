
# Reproducibility Protocol

## 1. Verify repository completeness

```bash
python scripts/verify_repository_readiness.py
```

## 2. Verify dataset integrity

```bash
python scripts/create_sha256_manifest.py
sha256sum -c data/SHA256SUMS.txt
```

## 3. Dataset

The dataset file is:

```text
data/synthetic_ehr_access_events_120000.csv
```

It contains 120,000 synthetic access events. The 15 predictor features are documented in `data/data_dictionary.csv`.

## 4. Model components

- ChainSimEnv: `src/aiba_ehr/chainsim_env.py`
- PPO agent: `src/aiba_ehr/ppo_agent.py`
- TCN+AM model: `src/aiba_ehr/tcn_attention_model.py`
- Data preprocessing: `src/aiba_ehr/preprocessing.py`

## 5. Result files

- `results/ai_module_performance.csv`
- `results/cv_fold_metrics.csv`
- `results/confusion_matrices.csv`
- `results/confusion_matrices.json`
- `results/blockchain_performance_summary.csv`
- `results/ablation_study.csv`
- `results/complexity_analysis.csv`
- `results/reward_weights.csv`
- `results/ppo_hyperparameters.csv`
- `results/tcn_am_hyperparameters.csv`

## 6. Random seed

All deterministic generation scripts use seed `42`.

## 7. Limitation

This repository supports reproducibility for the controlled synthetic-data and simulation study. It does not validate the system on real clinical EHR audit logs, and the public dataset is synthetic by design.
