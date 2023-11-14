# RNA-Seq Analysis in R

This repository contains the code and analysis pipeline for differential expression analysis using RNA-Seq data. The analysis is performed using R and includes several steps such as quality control, normalization, differential expression analysis, and feature selection methods. The primary aim is to identify differentially expressed genes across conditions, which will be further analyzed for annotation and pathway analysis in a separate workflow.

## Pipeline Overview

The RNA-Seq analysis pipeline is implemented in R Markdown and consists of the following main components:

1. **Differential Expression Analysis**: Utilizing the DESeq2 package to determine differentially expressed genes between two conditions.
2. **Heatmap Visualization**: Showing expression patterns across samples and genes.
3. **Volcano Plot**: Highlighting significantly differentially expressed genes.
4. **Statistical Testing**: Conducting additional tests such as t-tests to support differential expression findings.
5. **Hierarchical Clustering**: Grouping genes based on expression similarity.
6. **Principal Component Analysis (PCA)**: Reducing dimensionality to visualize the data.
7. **K-Means Clustering**: Identifying gene clusters based on expression profiles.
8. **Random Forest Analysis**: Utilizing this machine learning technique for feature selection.
9. **Gene Set Enrichment Analysis (GSEA): Understanding the biological pathways and processes using the fgsea package.
10. **Statistical Analysis and Visualization: Including PCA plots, lollipop plots, and comparison of P-value distributions across methods.

## Files and Directories

- `Data/`: Contains raw count data and other relevant files used in the analysis.
- `Differential_Expression_and_Feature_Selection.Rmd`: The R Markdown file where the analysis is performed.
- `Differential_Expression_and_Feature_Selection.nb.html`: The HTML output of the R Markdown file for easy viewing.
- `RNA-seq-Analysis-in-R.Rproj`: R project file for setting up the working environment.

## Usage

To run the analysis:

1. Clone the repository to your local machine.
2. Open the `RNA-seq-Analysis-in-R.Rproj` in RStudio.
3. Run the `Differential_Expression_and_Feature_Selection.Rmd` R Markdown file to reproduce the analysis.

## Output

The pipeline outputs a list of top genes identified from various analysis methods, saved as `Data/top_genes_df.csv`. These genes are candidates for further annotation and pathway analysis, which is part of a subsequent analysis step.

## Dependencies

This analysis was performed using R and the following R packages: `DESeq2`, `pheatmap`, `ggplot2`, `dplyr`, `tidyverse`, `randomForest`, among others. Please refer to the session information in the R Markdown document for a complete list of dependencies.

## Contact

For any additional questions or feedback, please contact:

- Alejandro Ponce: aleponce92@gmail.com

## Acknowledgements

This work is part of the coursework for the Master's in Bioinformatics program at XYZ University. Thanks to the instructors and peers who provided insights and feedback throughout the development of this project.

