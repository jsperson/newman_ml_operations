# Newman Machine Learning Operations

Coursework repository for Newman University's Machine Learning Operations course.

This repo is organized by course module so notebooks, assignment artifacts, and notes stay findable as the semester builds up. Most notebooks were authored in Google Colab and may contain Google Drive-specific paths.

Artifacts use boring, descriptive filenames in the form `assignment-<number>-<short-topic>.<ext>` when they map directly to a Canvas submission. Lecture or exploratory notebooks keep a `week-XX-<topic>.ipynb` prefix.

## Repository layout

```text
.
├── module-01-mlops-business-case/
│   └── assignment-1.2-wide-to-thin-reshaping.ipynb
├── module-02-eda-win-rates-leakage/
│   └── week-02-eda-win-rates-leakage.ipynb
├── module-03-temporal-feature-engineering/
│   └── assignment-3a-champion-synergies-counters.ipynb
├── module-04-match-outcome-prediction/
│   ├── assignment-4.1-match-outcome-prediction.ipynb
│   ├── assignment-4.2-choice-of-split-strategy.docx
│   └── match-outcome-leaderboard-xgboost.ipynb
├── module-05-filling-the-gaps/
│   └── assignment-5.1-filling-the-gaps.docx
├── module-06-backfill-orchestration/
│   └── assignment-6.1-purpose-of-backfill.docx
├── module-07-choosing-right-metric/
│   └── assignment-7.1-choosing-right-metric.ipynb
├── docs/
│   └── artifact-index.md
├── requirements.txt
└── README.md
```

## Canvas / module map

| Module | Canvas item / topic | Repository file | Purpose |
|---|---|---|---|
| 1 | 1.1 Organizational Framing | Not currently tracked as a separate file | Written framing assignment for the business use case and deployment context. |
| 1 | 1.2 Wide to Thin Reshaping | `module-01-mlops-business-case/assignment-1.2-wide-to-thin-reshaping.ipynb` | Reshapes League of Legends match data from one row per game into one row per player-match, constructs player-level `win`, validates the reshape, and documents the thin-table data dictionary. |
| 2 | EDA, win rates, and leakage | `module-02-eda-win-rates-leakage/week-02-eda-win-rates-leakage.ipynb` | Explores baseline blue-side win rate, champion win-rate features, game-level aggregation, and early leakage issues. |
| 3 | Assignment 3A — Champion Synergies and Counters | `module-03-temporal-feature-engineering/assignment-3a-champion-synergies-counters.ipynb` | Builds temporal, leakage-aware champion synergy/counter features and evaluates models with accuracy, AUC, and Brier score. |
| 4 | 4.1 Match Outcome Prediction | `module-04-match-outcome-prediction/assignment-4.1-match-outcome-prediction.ipynb` | Uses the fixed temporal split, selects a compact set of team-difference features, imputes missing values, scales logistic-regression inputs, and reports AUC, Brier score, and accuracy against the reference baseline. |
| 4 | 4.2 Choice of Split Strategy | `module-04-match-outcome-prediction/assignment-4.2-choice-of-split-strategy.docx` | Written organizational analysis comparing split strategies for a betting operator versus a consumer coaching app, including recommendation-level metrics for champion-switch advice. |
| 4 | Semester Leaderboard: Match Outcome Prediction | `module-04-match-outcome-prediction/match-outcome-leaderboard-xgboost.ipynb` | Builds a current-data XGBoost leaderboard submission with leakage-safe expanding prior win-rate features, temporal validation tuning, required train/test metrics, and generalization-gap checks. |
| 5 | 5.1 Filling the Gaps | `module-05-filling-the-gaps/assignment-5.1-filling-the-gaps.docx` | Written reflection comparing missing-value fill strategies, including Bayesian win rates, mastery values, tier fallback behavior, and the maintainability tradeoffs of simple versus context-aware fills. |
| 6 | 6.1 Purpose of Backfill | `module-06-backfill-orchestration/assignment-6.1-purpose-of-backfill.docx` | Written reflection explaining what dated backfilled run folders contain, why event-time backfills are not perfect historical replay, and how run metadata supports a practical data-retention recommendation. |
| 7 | 7.1 Choosing the Right Metric | `module-07-choosing-right-metric/assignment-7.1-choosing-right-metric.ipynb` | Compares AUC, Brier score, accuracy, and simulated betting-house profit for three probability models, then connects metric choice to deployment, maintenance, and ROI decisions. |

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

## Artifact index

See `docs/artifact-index.md` for a quick inventory of each tracked notebook or written assignment and its current role in the course sequence.
