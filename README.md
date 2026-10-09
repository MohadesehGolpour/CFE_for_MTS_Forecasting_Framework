# CFE for Multivariate Time-Series Forecasting — Evaluation Framework

This repository contains the experimental code and saved outputs for the paper
**“Comparing Counterfactual Explanations for Multivariate Time Series Forecasting:
A Unified Evaluation Framework.”**

It evaluates seven counterfactual variants derived from five methodological
families on 21 multivariate forecasting tasks: 17 BRGM piezometric series plus
ETTh1, ETTh2, Weather, and Electricity.

## Structure

```text
CFE_for_MTS_Forecasting_Framework/
├── Data/
│   ├── piezos/
│   └── Other/
│       ├── ETT-small/
│       ├── electricity/
│       └── weather/
├── notebooks/
│   ├── 01_dataset_characterization.ipynb
│   ├── 02_gru_model_selection_piezometers.ipynb
│   ├── 03_gru_model_selection_public_datasets.ipynb
│   ├── 04_verify_piezometer_gru_models.ipynb
│   ├── 05_counterfactual_benchmark_piezometers.ipynb
│   ├── 06_counterfactual_benchmark_public_datasets.ipynb
│   ├── 07_cross_dataset_analysis.ipynb
│   └── 08_correlation_analysis.ipynb
├── Results/
├── requirements.txt
└── REPRODUCIBILITY.md
```

## Data layout

```text
Data/
├── piezos/
│   ├── piezo1.csv ... piezo9.csv
│   └── piezo11.csv ... piezo18.csv
└── Other/
    ├── ETT-small/
    │   ├── ETTh1.csv
    │   └── ETTh2.csv
    ├── electricity/
    │   └── electricity.csv
    └── weather/
        ├── weather.csv
        └── weather_cleaned.csv
```

There are 17 BRGM files; `piezo10` is not part of the benchmark.

`weather.csv` is the original file. Notebook 01 reproduces the duplicate removal,
10-minute grid reconstruction, and interpolation that produced
`weather_cleaned.csv`, which is used by the forecasting experiments.

## Recommended run order

1. `01_dataset_characterization.ipynb`
2. `02_gru_model_selection_piezometers.ipynb`
3. `03_gru_model_selection_public_datasets.ipynb`
4. `04_verify_piezometer_gru_models.ipynb`
5. `05_counterfactual_benchmark_piezometers.ipynb`
6. `06_counterfactual_benchmark_public_datasets.ipynb`
7. `07_cross_dataset_analysis.ipynb`
8. `08_correlation_analysis.ipynb`

The canonical notebooks resolve paths from the repository root; users do not need
to edit local Windows/macOS/Google Drive paths.

## Results

`Results/` is the final saved result tree supplied with this artifact. It contains
the selected GRU checkpoints, aggregate CF results, statistical outputs, and
correlation-analysis outputs.

A subset of qualitative per-dataset CF plots was omitted from the supplied copy
to keep the artifact size manageable. The aggregate CSV files used for the paper
are retained.

