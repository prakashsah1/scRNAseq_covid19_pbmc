# scRNAseq_covid19_pbmc
This project is aimed at reproducing Figure 1 of the study by Wilk et al. published in Nature Medicine (2020): A single-cell atlas of the peripheral immune response in patients with severe COVID-19.

Data sources:
The dataset includes PBMC samples from 7 COVID-19 patients and 6 healthy age-matched controls.The count matrices were downloaded from the GEO repository: GSE150728. One additional sample (patient 560, labeled as C6) is not available on GEO (due to consent restrictions on sequence-level data) and is instead provided as a pre-processed .rds file in the study’s GitHub repository: Wilk COVID-19 GitHub. Each rds file contained matrices for exon, intron and spanning reads. Exon matrices were extracted from the rds files for each sample and used for analysis.

Figure 1a: Exon matrices for all the samples were pre-processed by filtering for min and max counts (1000, 15000 UMI per cell), doublet ratio<0.75, mitochondial and ribosomal RNAs content <0.2. Matrices were then merged, aligning by gene name and filling zeros for missing genes. Seurat object was created and standard seurat workflow was used (instead of SCTtransform used by authors likely explaining the difference in appearance of the UMAP plot). 
