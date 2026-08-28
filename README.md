# GraphStream-IDS

Continual Graph Neural Network for Zero-Day Intrusion Detection Under Network Concept Drift.

Major project — B.Tech CSE, RGUKT Telangana. Research/publication goal.

## Folder structure

```
graphstream-ids/
├── data/
│   ├── raw/          # Original downloaded datasets — never modify these files
│   ├── interim/       # Cleaned/intermediate outputs of preprocessing steps
│   └── processed/     # Final feature-engineered datasets ready for graph construction
├── notebooks/          # Exploratory analysis, dataset audits, prototyping
├── src/                 # Reusable pipeline code (preprocessing, graph construction,
│                         #   models, drift detection, replay memory, evaluation)
├── requirements.txt
└── README.md
```

## Setup

1. Create a virtual environment (Colab or local venv).
2. Install PyTorch first, matching your CUDA version (or CPU-only for Colab free tier).
3. Install PyTorch Geometric following the official install matrix for your PyTorch/CUDA
   combination (version-sensitive — do not just `pip install torch-geometric` blindly).
4. `pip install -r requirements.txt` for everything else.

## Datasets

| Dataset | Source | Status |
|---|---|---|
| CIC-IDS2017 | UNB (nsl.cs.unb.ca/CIC) | Priority 1 — start here |
| CSE-CIC-IDS2018 | UNB | Priority 2 |
| UNSW-NB15 | UNSW Canberra Cyber (request access) | Priority 3 |
| TON-IoT | UNSW Canberra Cyber (request access) | Priority 3 |

Zero-day holdout attack family: **TBD — decide before training any baseline.**

## Roadmap

See project abstract / proposal PDF for the full 6-month week-by-week roadmap.
