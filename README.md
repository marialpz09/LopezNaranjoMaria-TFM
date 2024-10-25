# scRNA-seq-Endothelial cells-Mice

# System requirements
The code was written in R. It was tested with R version 4-3-3 packages dependencies include: Seurat (version: 5.0.1), SingleR (version 2.4.1), celldex (version 1.12.0), DESeq2 (version 1.42.4), clusterProfiler (version 4.10.1) and org.Mm.eg.db (version 3.18.0).

All of the R packages are available at Bioconductor, installation was performed following the guide of Bioconductor.

Seurat: analysis includes quality control, normalization, sample aggregating, dimension reduction, clustering and visualization. The expected outputs include cell clusters, gene expression matrix and various plots for visualization (UMAP, marker gene expression). https://github.com/satijalab/seurat

SingleR: performs cluster type annotation from single-cell RNA sequencing data, by leveraging reference transcriptomic datasets. In this case celldex datasets. https://bioconductor.org/packages/release/bioc/html/SingleR.html

celldex: provides a collection of reference datasets with curated cell type labels, for automated annotation of single-cell data. https://bioconductor.org/packages/release/data/experiment/html/celldex.html

DESeq2: perform variance-mean dependence in count data from pseudo-bulk expression profiles aggregated for each condition, and test differential expression analysis. https://bioconductor.org/packages/release/bioc/html/DESeq2.html

clusterProfiler: functional characteristics analysis for gene functional annotation. It will output the enriched functions and statistics. https://bioconductor.org/packages/release/bioc/html/clusterProfiler.html

org.Mm.eg.db: genome wide annotation for mose, used for annotation of functions markers. https://bioconductor.org/packages/release/data/annotation/html/org.Mm.eg.db.html

Content
Preprocessing -> quality control, normalization, sample integration, dimension reduction, clustering and visualization.

Anotation -> clusters annotation and validation based on known markers from literature and SingleR with ImmGen Data Base.

targetingEndothelials -> identification of CD45+CD31- subset. Differential expression analysis between biological conditions. Gene ontology enrichment for up-regulated and down-regulated genes and visualization.


Inputs for use
The inputs for the R analysis include the filtered feature-barcode matrix obtain following the pipeling from CellRanger (10X GENOMICS). https://support.10xgenomics.com/single-cell-gene-expression/software/pipelines/latest/output/matrices

The filtered feature-barcode matrix includes three gzipped tsv files with feature and barcode sequences corresponding to row and column indices respectively. Each sample have a feature-barcode matrix respectively with:

barcode.tsv.gz

features.tsv.gz

matrix.mtx.gz

This four filtered feature-barcode matrix are the inputs for the Prepocessing and the output from this Rmd is the input for the rest of the scripts.
