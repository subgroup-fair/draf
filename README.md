# DRAF (Doubly-Regressing Approach for Subgroup Fairness)

Official implementation of **"Doubly-Regressing Approach for Subgroup Fairness"** (ICLR 2026).

[[Paper]](https://openreview.net/forum?id=17UDRTRLmp) [[arXiv]](https://arxiv.org/abs/2510.21091)

## Installation

```bash
git clone https://github.com/subgroup-fair/draf.git
cd main
pip install -r requirements.txt
```

### Requirements

- Python == 3.10
- numpy == 1.26.4
- pandas == 2.1.4
- torch == 2.0.0
- scikit-learn == 1.6.1

## Usage

```bash
python run.py --dataset adult --sens_keys sex,race,age,marital-status --data_dir data/raw/ --method dr --lambda_fair 1.00 --union_mode apriori_forward --n_low_frac 0.2
```

### Arguments

| Flag | Type | Default | Description |
|------|------|---------|-------------|
| `--dataset` | str | `adult` | Dataset name |
| `--data_dir` | str | `data/raw/` | Path to data directory |
| `--method` | str | `dr` | Method to run |
| `--sens_keys` | str | `None` | Separated sensitive attributes |
| `--sens_thresh` | float | `0.5` | Sensitive attribute threshold |
| `--base_model` | str | `mlp` | Base model |
| `--seed` | int | `42` | Random seed |
| `--epochs` | int | `300` | Number of training epochs |
| `--lr` | float | `1e-3` | Learning rate |
| `--lambda_fair` | float | `0.0` | Fairness regularization weight |
| `--n_low_frac` | float | `None` | Minimum subgroup size fraction (gamma in the paper) |
| `--union_mode` | str | `apriori_forward` | Subgroup union mode (`all` or `apriori_forward`) |
| `--x_sensitive` | str | `concat` | Sensitive feature handling (`concat` or `drop`) |
| `--save_dir` | str | `results` | Output directory |

### Datasets

```
data/
└── raw/
    └── adult.csv
```

## Citation

```bibtex
@inproceedings{
  kim2026draf,
  title={Doubly-Regressing Approach for Subgroup Fairness},
  author={Kunwoong Kim and Kyungseon Lee and Jihu Lee and Dongyoon Yang and Yongdai Kim},
  booktitle={The Fourteenth International Conference on Learning Representations},
  year={2026},
  url={https://openreview.net/forum?id=17UDRTRLmp}
}
```
