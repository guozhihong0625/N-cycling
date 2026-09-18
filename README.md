# N-cycling

Analysis code, processed data, and derived outputs supporting the study of nitrogen-cycling functional genes in the Tonghui and Qing Rivers, Beijing, China.

The repository contains materials for microbial-community analysis, spatiotemporal analysis of nitrogen-cycling genes, AutoML modeling, SHAP interpretation, and partial dependence analysis.

## Study overview

The study integrates physicochemical measurements, microbial-community data, metagenomic N-cycling gene abundances, and interpretable machine-learning analyses. Ten representative N-cycling genes were modeled individually:

`gdh`, `glnA`, `narG`, `nasA`, `nifH`, `nirB`, `nirS`, `norB`, `nosZ`, and `nxrB`.

The machine-learning workflow includes H2O AutoML, model-performance evaluation, feature-importance analysis, SHAP interpretation, one-dimensional partial dependence plots (1D PDPs), and two-dimensional partial dependence plots (2D PDPs).

## Repository contents

| File | Description |
|---|---|
| `DATA.xlsx` | Data workbook provided with the repository. Variable definitions and analytical context are described in the manuscript and Supplementary Materials. |
| `ASV.zip` | Microbial-community and related statistical analyses. Includes R scripts and outputs for alpha diversity, PCoA/beta diversity, PERMANOVA, phylum- and genus-level composition, Proteobacteria analysis, and spatiotemporal plots of representative N-cycling genes. |
| `Genus_level_analysis.zip` | Genus-level microbial-community analysis, including sample metadata, genus summaries, Shannon diversity, differential-abundance results, and comparisons among campaigns, positions, and rivers. |
| `Proteobacteria_analysis.zip` | Derived tables and figures for Proteobacteria-focused analyses. The corresponding analysis script is included in `ASV.zip` as `Proteobacteria_analysis.R`. |
| `spatiotemporal_barplots.zip` | Output figures and plotting data for temporal and spatial variation of the ten representative N-cycling genes in the Tonghui and Qing Rivers. The source plotting script is included in `ASV.zip` as `N-cycling genes spatiotemporal bar plots.R`. |
| `ML.zip` | Gene-specific AutoML and model-interpretation materials. Contains R and Python scripts, model outputs, fitting results, variable-importance results, SHAP results, 1D/2D PDP analyses, and model-stability outputs for the ten representative genes. |

## Main analysis files

### Microbial-community analysis

After extracting `ASV.zip`, key R scripts include:

- `L2.R`
- `L6.R`
- `Proteobacteria_analysis.R`
- `N-cycling genes spatiotemporal bar plots.R`

The archive also contains processed abundance tables, Shannon-diversity results, PERMANOVA results, taxonomic-composition figures, and supporting tables used in the manuscript and Supplementary Materials.

After extracting `Genus_level_analysis.zip`, the main R scripts are:

- `Sample_metadata.R`
- `Shannon.R`

These scripts support genus-level summaries, diversity analysis, and differential-abundance comparisons.

### AutoML and model interpretation

After extracting `ML.zip`, the main directory is `paper_data/`. Separate subdirectories are provided for:

- `gdh`
- `glnA`
- `narG`
- `nasA`
- `nifH`
- `nirB`
- `nirS`
- `norB`
- `nosZ`
- `nxrB`

Each gene folder contains analysis scripts and/or outputs for model fitting and interpretation. Representative files include:

- `<gene>.R` — gene-specific modeling and interpretation workflow
- `<gene>.py` — Python-based analysis/visualization
- `2D_<gene>.py` or related scripts — two-dimensional PDP analysis
- `<gene>_SHAP.pdf` — SHAP output
- `<gene>_PDP.pdf` / `.png` — partial dependence output
- `<gene>_Feature_Importance.pdf` — feature-importance output
- `Model_Stability_Results.xlsx` — model-stability results
- `End_Results.xlsx` — gene-specific summary results

The exact set of files differs slightly among gene folders.

## Software environment

The analyses were developed primarily in:

- **R 4.4.2**
- **Python 3.7.13**
- **H2O AutoML / H2O 3.40.0.1**

Frequently used R packages include:

`h2o`, `shapviz`, `iml`, `caret`, `randomForest`, `gbm`, `vegan`, `ggplot2`, `dplyr`, `tidyr`, `readxl`, `openxlsx`, `pheatmap`, `corrplot`, `patchwork`, and related visualization/data-processing packages.

Frequently used Python packages include:

`h2o`, `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `shap`, and `pdpbox`.

Package availability may vary by script.

## Reproducing the analyses

1. Download or clone the repository.
2. Extract the required `.zip` archive(s).
3. Install the required R/Python packages.
4. Update file paths in the scripts to match your local directory structure.
5. Run the relevant scripts for microbial-community analysis, spatiotemporal analysis, or gene-specific AutoML interpretation.

### Important note on file paths

Some archived scripts preserve the original local Windows file paths used during analysis, for example paths beginning with `E:\Rdoc\...` or `C:\Users\...`. These paths are not portable and should be replaced with paths appropriate to the local working directory before running the scripts.

For reproducible reuse, relative paths are recommended.

## Raw sequence data

The raw sequence data generated in this study have been deposited in the NCBI Sequence Read Archive (SRA) under BioProject accession:

**PRJNA418866**

NCBI BioProject: https://www.ncbi.nlm.nih.gov/bioproject/PRJNA418866

## Notes on interpretation

The repository contains code and analysis materials used to characterize associations between measured environmental variables and N-cycling gene abundance. Gene abundance is interpreted as community-level **genetic potential**, not as direct measurement of gene expression, enzyme activity, or in situ nitrogen-transformation rates.

SHAP and PDP outputs describe the fitted predictive models and should not be interpreted as direct causal effects of individual environmental variables.

## Citation

If you use materials from this repository, please cite the associated manuscript once published.

## Contact

For questions regarding the data or analysis workflow, please contact the corresponding authors listed in the associated manuscript.
