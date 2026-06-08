# Newman Machine Learning Operations

Coursework repository for Newman University's Machine Learning Operations course.

This repo is organized by course module so notebooks, assignment artifacts, and notes stay findable as the semester builds up. Most notebooks were authored in Google Colab and may contain Google Drive-specific paths.

## Repository layout

```text
.
├── module-01-mlops-business-case/
│   └── 1.2_wide_to_thin_reshaping.ipynb
├── module-02-eda-win-rates-leakage/
│   └── week-02-eda-win-rates-leakage.ipynb
├── module-03-temporal-feature-engineering/
│   └── assignment-3a-champion-synergies-counters.ipynb
├── docs/
│   └── notebook-index.md
├── requirements.txt
└── README.md
```

## Canvas / module map

| Module | Canvas item / topic | Repository file | Purpose |
|---|---|---|---|
| 1 | 1.1 Organizational Framing | Not currently tracked as a separate file | Written framing assignment for the business use case and deployment context. |
| 1 | 1.2 Wide to Thin Reshaping | `module-01-mlops-business-case/1.2_wide_to_thin_reshaping.ipynb` | Reshapes League of Legends match data from one row per game into one row per player-match, constructs player-level `win`, validates the reshape, and documents the thin-table data dictionary. |
| 2 | EDA, win rates, and leakage | `module-02-eda-win-rates-leakage/week-02-eda-win-rates-leakage.ipynb` | Explores baseline blue-side win rate, champion win-rate features, game-level aggregation, and early leakage issues. |
| 3 | Assignment 3A — Champion Synergies and Counters | `module-03-temporal-feature-engineering/assignment-3a-champion-synergies-counters.ipynb` | Builds temporal, leakage-aware champion synergy/counter features and evaluates models with accuracy, AUC, and Brier score. |

## Local setup

The notebooks are designed for Colab, but the Python dependencies are captured in `requirements.txt` for local inspection or execution.

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Some notebooks use Colab-only imports such as `google.colab.drive`. When running locally, replace those data-loading cells with local paths or Hugging Face downloads.

## Working conventions

- Keep submitted or assignment-facing notebooks inside their module directory.
- Prefer descriptive notebook names over upload timestamps.
- Keep raw data, generated outputs, model artifacts, and local virtual environments out of git.
- If a notebook depends on a large dataset, document the source and loading step in the notebook rather than committing the data file.

## Notebook index

See `docs/notebook-index.md` for a quick inventory of each notebook and its current role in the course sequence.
