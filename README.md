# RNA-Seq Analysis in R

This repository contains the code and analysis pipeline for differential expression analysis using RNA-Seq data in R. The analysis is divided into two main notebooks: one focusing on differential expression and feature selection, and the other on gene annotation and pathway analysis.

## Table of Contents
1. [Pipeline Overview](#pipeline-overview)
2. [Files and Directories](#files-and-directories)
3. [Setup Instructions](#setup-instructions)
4. [Usage](#usage)
5. [Output Details](#output-details)
6. [Dependencies](#dependencies)
7. [Plots and Visualizations](#plots-and-visualizations)
8. [Contact](#contact)
9. [Acknowledgements](#acknowledgements)

## Pipeline Overview

### Differential Expression and Feature Selection
This part of the analysis, implemented in `Differential_Expression_and_Feature_Selection.Rmd`, includes:
- Differential Expression Analysis
- Heatmap and Volcano Plot Visualization
- Statistical Testing and Hierarchical Clustering
- Principal Component Analysis (PCA) and K-Means Clustering
- Random Forest Analysis for Feature Selection

### Gene Annotation and Pathway Analysis
The second notebook, `Gene_Annotation_and_Pathway_Analysis.Rmd`, focuses on:
- Enrichment analysis of the selected genes
- Gene Set Enrichment Analysis (GSEA) using DESeq2 data

## Files and Directories
- `Data/`: Contains DESeq2 results and lists of important genes.
- `Differential_Expression_and_Feature_Selection.Rmd`: First part of the analysis.
- `Gene_Annotation_and_Pathway_Analysis.Rmd`: Second part focusing on enrichment and GSEA.
- `RNA-seq-Analysis-in-R.Rproj`: R project file.

## Input Data Requirements

To successfully run the analysis, the following types of input data are required:

### Counts Data
- **Description**: This file contains the raw count data from RNA sequencing. It is expected to be a matrix with genes listed in rows and samples in columns.
- **Format**: The file should be in a compressed format (e.g., `.csv.gz`) to manage large data sizes efficiently.
- **Placement**: Ensure that this file is placed in the `Data/` directory of the project.

### Sample and Data Relationship Format (SDRF) Metadata File
- **Description**: This metadata file provides crucial context about the samples, such as experimental conditions, sample preparation details, and sequencing information. It's essential for interpreting the count data accurately.
- **Format**: Typically, this file is in a tabular format (e.g., `.txt` or `.csv`), containing structured metadata.
- **Placement**: Similar to the counts data, this file should also be located in the `Data/` directory.

### Important Notes
- **Alignment**: The metadata should align correctly with the samples mentioned in the counts data. Any mismatch may lead to incorrect or misleading analysis results.
- **File Naming**: Ensure that the files are named appropriately and match the references in the analysis scripts. Different file names or paths could cause errors in the analysis process.


## Setup Instructions
To ensure you have all the required packages installed, you can run the following command in R. This script checks for the presence of each package and installs it if it's not already installed:
```R
required_packages <- c("enrichR", "ggplot2", "stringr", "fgsea", "msigdbr", 
                       "reshape2", "gridExtra", "tximport", "DESeq2", 
                       "rhdf5", "pheatmap", "AnnotationDbi", "org.Hs.eg.db",
                       "readr", "xml2", "tidyverse", "dendextend", "factoextra",
                       "FactoMineR", "cluster", "randomForest", "caret", "UBL")

new_packages <- required_packages[!(required_packages %in% installed.packages()[,"Package"])]
if(length(new_packages)) install.packages(new_packages)

# Load the packages
lapply(required_packages, library, character.only = TRUE)
```


## Usage
To run the analysis:
1. Clone the repository.
2. Open `RNA-seq-Analysis-in-R.Rproj` in RStudio.
3. Run `Differential_Expression_and_Feature_Selection.Rmd`.
4. Follow with `Gene_Annotation_and_Pathway_Analysis.Rmd`.

## Output Details
The pipeline outputs include:
- Lists of top genes from various analysis methods.
- Annotated genes and pathway analysis results.

## Dependencies

This project relies on several R packages, organized here by their primary purpose:

### Data Import and Processing
- `readr`: For reading and writing data.
- `tximport`: For importing transcript-level estimates.
- `rhdf5`: Interface to the HDF5 binary data format.

### Statistical Analysis and Bioinformatics
- `DESeq2`: For differential gene expression analysis.
- `randomForest`: For applying Random Forest algorithms.
- `caret`: For classification and regression training.
- `UBL`: For unbalanced dataset handling.

### Data Visualization and Plotting
- `ggplot2`: For creating various types of plots.
- `pheatmap`: For generating heatmaps.
- `gridExtra`: For arranging multiple grid-based plots.
- `factoextra`: For extracting and visualizing the results of multivariate data analyses.
- `FactoMineR`: For PCA and other analysis.
- `dendextend`: For manipulating and visualizing dendrograms.

### Gene Set Enrichment and Annotation
- `enrichR`: For accessing several enrichment analysis databases.
- `fgsea`: For fast gene set enrichment analysis.
- `msigdbr`: A Molecular Signatures Database (MSigDB) R package.
- `AnnotationDbi`: For annotation database interface.
- `org.Hs.eg.db`: For genome-wide annotation for Human.

### Data Transformation and Manipulation
- `reshape2`: For reshaping data.
- `tidyverse`: For an easy-to-use collection of R packages for data science.
- `stringr`: For string operations.
- `xml2`: For reading XML files.
- `cluster`: For "clustering" package.

## Plots and Visualizations

**Hierarchical Clustering Dendrogram**
This dendrogram shows the results of hierarchical clustering, illustrating how genes group together based on their expression profiles.
![Hierarchical Clustering Dendrogram](plot/dendogram.png)

**Initial Heatmap of DESeq2 Results**
The heatmap visualizes expression levels across genes and samples, highlighting patterns and differences in gene expression.
![Initial Heatmap of DESeq2 Results](plot/heatmap.png)

**Elbow Method for Determining Optimal Number of Clusters**
This plot helps in determining the optimal number of clusters for K-means clustering by showing the variance explained by each number of clusters.
![Elbow Method for Determining Optimal Number of Clusters](plot/elbow.png)

**OOB Error Plot for Optimal Number of Trees in Random Forest**
The Out-of-Bag (OOB) error plot indicates the optimal number of trees for the Random Forest model, balancing complexity and accuracy.
![OOB Error Plot for Optimal Number of Trees in Random Forest](plot/oob.png)

**PCA Cluster Results**
The PCA plot displays the clustering of samples based on their gene expression, reducing the high-dimensional data into principal components.
![PCA Cluster Results](plot/pca.png)

**Initial Volcano Plot of DESeq2 Results**
This volcano plot highlights significantly differentially expressed genes, considering both fold changes and statistical significance.
![Initial Volcano Plot of DESeq2 Results](plot/volcano_plot.png)

**Top Genes Selected Lollipop Graph Based on Enrichment Results**
The lollipop graph shows the top genes selected based on enrichment results, illustrating the significance and magnitude of their expression changes.
![Top Genes Selected Lollipop Graph](plot/topgenes.png)


## Contact
For questions or feedback, please contact:
- Alejandro Ponce: aleponce92@gmail.com

## Acknowledgements
This work is part of the Master's in Bioinformatics program at Brandeis University.


