# Coursework Artifact Index

This file tracks the class notebooks and written assignments in repository order. It is meant to answer: “Where did I put that assignment?” without archaeology. Revolutionary technology.

## Module 1 — MLOps Business Case

### `module-01-mlops-business-case/assignment-1.2-wide-to-thin-reshaping.ipynb`

Primary role: assignment notebook.

Covers:
- Organizational framing for the League of Legends prediction use case.
- Wide-to-thin reshape from game-level rows to player-match rows.
- Construction of player-level `win` from game-level `bwin` and player side.
- Validation checks for row counts and game/team/player consistency.
- Thin-table data dictionary.

## Module 2 — EDA, Win Rates, and Leakage

### `module-02-eda-win-rates-leakage/week-02-eda-win-rates-leakage.ipynb`

Primary role: lecture / exploratory notebook.

Covers:
- Dataset download/loading.
- Thin-table construction used by later notebooks.
- Game-level aggregation from player rows.
- Baseline blue-side win rate.
- Champion win-rate feature exploration.
- Early model evaluation and leakage discussion.

## Module 3 — Temporal Structure and Feature Engineering

### `module-03-temporal-feature-engineering/assignment-3a-champion-synergies-counters.ipynb`

Primary role: assignment notebook.

Covers:
- Champion synergy and counter pair construction.
- Temporal feature availability using prior game history.
- Bayesian-smoothed win-rate features.
- Patch-scoped train/test evaluation.
- Model comparison using accuracy, AUC, and Brier score.

## Module 4 — Match Outcome Prediction

### `module-04-match-outcome-prediction/assignment-4.1-match-outcome-prediction.ipynb`

Primary role: assignment notebook.

Covers:
- Fixed patch-aware temporal train/test split for the feature-engineered match dataset.
- Feature selection using team-difference columns, target correlation, and redundancy checks.
- Missing-value handling for blue-minus-red difference features, including missingness indicators.
- Logistic regression with `StandardScaler` in a pipeline.
- Test-set AUC, Brier score, and accuracy compared with the reference baseline.
- Reflection on feature signal, pre-game prediction limits, split validity, and organizational value.

### `module-04-match-outcome-prediction/assignment-4.2-choice-of-split-strategy.docx`

Primary role: written assignment.

Covers:
- Organizational comparison of split strategies for a sports-betting operator and a consumer coaching app.
- Patch-boundary walk-forward validation risks for betting/pricing use cases.
- Player-level chronological validation for personalized champion-switch recommendations.
- Recommendation-level metrics for Team B, including predicted uplift, confidence, and calibration.

## Maintenance checklist

When adding a new artifact:

1. Put it in the matching `module-XX-topic/` directory.
2. Use a descriptive filename instead of the Colab upload timestamp.
3. Update the README module map.
4. Add a short entry here with the notebook's purpose and main outputs.
5. Do not commit raw datasets, local caches, virtual environments, or generated model artifacts.
