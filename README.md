# Analysis of DEGs in ASD vs Controls

## Overview
This repository contains an R Markdown document detailing an extensive analysis of differentially expressed genes (DEGs) in individuals with Autism Spectrum Disorder (ASD) 
compared to controls. The analysis is based on data from the GEO database (GSE28521) and involves various bioinformatics techniques and statistical methods.

## Results
[View the Knitted HTML file](https://htmlpreview.github.io/?https://github.com/stratashake/R-Transcriptomics-Pipeline-ASD/blob/main/docs/Output.html)
Specific data, such as GSEA results, Cytoscape's analysis of enriched pathways, and Cytoscape's representation of the WGCNA network can be found in the 'docs' folder.

## Data Source
The data used in this analysis is sourced from the GEO database, specifically from [GSE28521](https://www.ncbi.nlm.nih.gov/geo/geo2r/?acc=GSE28521). 
This dataset includes gene expression profiles from individuals with ASD and control subjects.

## Key Analyses
- **Data Preprocessing**: Filtering data for cortex tissue samples and establishing factors for ASD and control groups.
- **Statistical Analysis & Machine Learning**: Using SAMr for identifying DEGs and Random Forest for feature selection.
- **Clustering and Visualization**: Implementing hierarchical clustering for data visualization.
- **Gene Set Enrichment Analysis (GSEA)**: Conducting pathway analysis to understand the biological significance of DEGs.
- **Weighted Gene Co-expression Network Analysis (WGCNA)**: Building gene co-expression networks to identify modules of correlated genes.
- **Exporting Network Data**: Preparing data for visualization in network analysis tools like Cytoscape.

## Installation and Setup

This analysis was performed using:
- R version 4.3.2 (2023-10-31 ucrt)
- R studio version 2023.6.0.421
- Cytoscape Version: 3.10.1

To run the analysis, you will need R along with several bioinformatics and statistical analysis packages. The primary packages used include:

- `GEOquery`
- `limma`
- `umap`
- `samr`
- `dendextend`
- `randomForest`
- `AnnotationDbi`
- `illuminaHumanv4.db`
- `fgsea`
- `msigdbr`
- `WGCNA`

Optional:
- `maptools` (Note: This package is obsolete and no longer officially supported. It must be compiled from source and is not required to run the main analysis.
  It is used only for specific visualizations as intended by the original authors in the first code chunk.)

### Installing Packages

You can install these packages from CRAN and Bioconductor using the following commands in R:

```{r}
install.packages(c("umap", "randomForest", "dendextend"))

# Install Bioconductor packages
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install(c("GEOquery", "limma", "AnnotationDbi", "illuminaHumanv4.db", "fgsea", "msigdbr", "WGCNA", "samr"))
```

1. Clone the repository: git clone 'https://github.com/stratashake/R-Transcriptomics-Pipeline-ASD'
2. Open the '.rmd' file in RStudio.
3. Install the required R packages (if not already installed).

## Running the Analysis
The R Markdown document is structured to be run in sections, each corresponding to a different phase of the analysis. 
You can run each code chunk individually or run the entire document to perform the full analysis.

## License
This project is licensed under the MIT License

## Contact
For inquiries, please reach out to [matthewdyer.pl@gmail.com](mailto:matthewdyer.pl@gmail.com).
