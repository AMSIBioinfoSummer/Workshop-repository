
## Introduction

This workshop provides a quick (~2 hour), hands-on introduction to current computational analysis approaches for studying single-cell RNA sequencing data. We will discuss the data formats used frequently in single-cell analysis, typical steps in quality control and processing of single-cell data, and some of the biological questions these data can be used to answer. 

Given we only have 2 hours, we will start with the data already processed into a count matrix, which contains the number of sequencing reads mapping to each gene for each cell. The steps to generate such a count matrix depend on the type of single-cell sequencing technology used and the experimental design. For a more detailed introduction to these methods we recommend the long-form single-cell RNA seq analysis workshop from the BioCellGen group ([available here](https://biocellgen-public.svi.edu.au/mig_2019_scrnaseq-workshop/public/)) and the analysis of single-cell RNA-seq data course put together by folks at the Sanger Institute [available here](https://scrnaseq-course.cog.sanger.ac.uk/website/processing-raw-scrna-seq-data.html). Briefly, a count matrix is generated from raw sequencing data using the following steps:

1. If multiple sample libraries were pooled together for sequencing (typically to reduce cost), sequences are separated (i.e. demultiplexed) by sample using barcodes that were added to the reads during library preparation. 
1. Quality control on the raw sequencing reads (e.g. using [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/))
1. Trimming the reads to remove sequencing adapters and low quality sequences from the ends of each read (e.g. using [Trim Galore!](https://github.com/FelixKrueger/TrimGalore)).
1. Aligning QCed and trimmed reads to the genome (e.g. using [STARsolo](https://github.com/alexdobin/STAR/blob/master/docs/STARsolo.md), [Kalliso-BUStools](https://www.kallistobus.tools/about), or [CellRanger](https://support.10xgenomics.com/single-cell-gene-expression/software/pipelines/latest/using/tutorial_ov)).
1. Quality control of mapping results.
1. Quantify the expression level of each gene for each cell (e.g. using bulk tools or single-cell specific tools from STAR, Kallisto-BUStools, or CellRanger). 

Starting with the expression counts matrix, this workshop will cover the following topics:

1. The SingleCellExperiment object
1. Empty droplet identification
1. Cell-level quality control
1. Normalisation
1. Dimension Reduction and visualisaion 
1. Clustering
1. Marker gene/cell annotation
