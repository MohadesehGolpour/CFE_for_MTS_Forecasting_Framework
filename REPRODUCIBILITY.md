# Reproducibility notes

## Notebook-to-output mapping

| Notebook | Main output folder |
|---|---|
| 01 | `Results/EDBT_dataset_characterization/` |
| 02 | `Results/EDBT_piezo_GRU/` |
| 03 | `Results/EDBT_public_GRU_v6/` |
| 04 | `Results/EDBT_piezo_GRU/best_model_re_evaluation/` |
| 05 | `Results/EDBT-results/` |
| 06 | `Results/EDBT-results-public-datasets/` |
| 07 | `Results/nemenyi_results_corrected/` |
| 08 | `Results/EDBT-results-public-datasets/All/meta_analysis_corrected/` |

The cleaned notebooks deliberately preserve the executed numerical settings and
method logic. The main changes are repository-relative paths, removal of
superseded scratch analysis, and clearer execution order.

The supplied `Results/` files are copied unchanged. Some historical CSV/JSON
metadata therefore contains absolute paths from the original execution machine;
those strings are provenance metadata only and are not used by the cleaned
notebooks.

Random seeds are preserved. Exact bit-for-bit equality across different
GPU/CUDA/cuDNN/PyTorch environments is not guaranteed, so saved checkpoints and
final outputs are included alongside the code.

Exact package versions are pinned only where they were visible in the supplied
executed notebooks. Compatible ranges are used where the historical exact version
was not recorded rather than inventing a version.
