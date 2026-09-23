# TSFM-Robustness-Evaluation

## Source files and analysis for Future Internet Article

Use these files together in the repository in a clean Python environment:

1. `robust_tsfms_experiment_runner.ipynb` — regenerates run-level RMSE and PICP from the SKAB source data and the three forecasting models. This is the expensive, GPU-oriented stage.
2. `robust_tsfms_rmse_picp_results_all_runs.csv` — the archived run-level metrics used for the current paper analysis. Include it in the repository so tables can be rebuilt without rerunning models.
3. `robust_tsfms_reproduction_code.ipynb` — validates the run-level metrics and regenerates the tables and figures. It reads the archived CSV by default. Set `USE_REGENERATED = True` to analyze a fresh runner output.

Basic package prerequisites:
- `pandas`
- `numpy`
- `matplotlib`
- `notebook`

Model package versions:

- `tirex-ts==1.4.2`
- `timesfm[torch]==2.0.1`
- `chronos-forecasting==2.3.0`

Model checkpoints:

- Chronos-2: amazon/chronos-2
- Fallback: s3://autogluon/chronos-2
- TimesFM-2.5: google/timesfm-2.5-200m-pytorch
- TiRex: NX-AI/TiRex
