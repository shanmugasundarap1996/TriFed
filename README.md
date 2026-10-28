# TriFed-Diabetes: upload package

Copies of the final files (nothing re-run or regenerated).

| Folder | Contents |
|---|---|
| `01_Paper` | Anonymized manuscript (`manuscript.tex/.pdf`, Springer Nature `sn-jnl` template, `sn-basic` author-year references), `references.bib`, `manuscript.bbl`, class/style files, `Fig1`-`Fig9`, and the separate `TitlePage.tex/.pdf`. Compile: pdflatex, bibtex, pdflatex, pdflatex. |
| `02_Supplementary` | Online Resource 1 (`ESM_1.pdf`, `ESM_1.tex`) and its four figures. |
| `03_Dataset` | `pima-indians-diabetes.csv` (768 records, 8 predictors, outcome) and `client_partitions/seed_*/` (five Dirichlet(0.5) clients and the global test set for each of the ten evaluation seeds; protocol in `FINAL_PROTOCOL.txt`). |
| `04_Implementation` | `notebooks/R1`-`R3` (Phase I baselines, CIR-CalBoost, federated methods with drift and prevalence correction); `federated_engine/fl_engine.py`, `run_all.py`, `log_indicators.py` (QPW-Fed, FedAvg, FedProx, FedAdam, uniform aggregation, drift, indicator logging); `figure_scripts/` for the paper figures. |
| `05_Results` | `R1_R3_notebook_outputs/` (per-trial, per-round, and prediction files from R1-R3), `federated_engine_outputs/` (all rounds, client weights, QPW indicators, calibration, runtime), `phase_results_csv/` (per-phase result and table CSVs), `RESULTS_EXPLAINED.md`. |
| `06_Tables` | `ALL_RESULTS_TABLES.xlsx` and the tables T01-T23 as Markdown. |
| `07_Figures` | `main_text/` Fig1-Fig9 (Figs. 1, 2, 4 also as vector PDF) and `supplementary/` Figs. S1-S4. |

Notes
- The scripts and notebooks use absolute paths (`D:\diabetic project\...`); change the path variables at the top before running elsewhere. `fl_engine.py` reads the client partitions from `03_Dataset/client_partitions`.
- `ESM_1.tex` loads its figures from `../figures/`; when compiling it from `02_Supplementary`, change `\graphicspath` to `{figures/}`.
