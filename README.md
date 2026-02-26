Overview 
The PPCP Transcriptomics Toolkit is an open-source, interactive web application built with R Shiny, designed for the systematic exploration of transcriptomic perturbations in adipose tissue induced by pharmaceuticals and personal care products (PPCPs). PPCPs are ubiquitous environmental endocrine-disrupting chemicals (EDCs) with well-established links to metabolic dysfunction, and adipose tissue serves as the primary reservoir and target organ for these lipophilic compounds. However, public transcriptomic datasets of PPCP exposure in adipose tissue remain fragmented across studies, with significant heterogeneity in experimental design, species models, and technical platforms. This toolkit addresses this gap by integrating 22 high-quality, curated transcriptomic datasets covering 6 major PPCPs (BPA, BPS, BPF, butylparaben, DEHP, dexamethasone) into a unified, user-friendly analytical platform. This toolkit enables researchers, toxicologists, and clinicians to explore dose- and time-specific transcriptional responses to PPCP exposure, identify conserved and chemical-specific gene signatures, and validate candidate biomarkers of metabolic toxicity—all without requiring local data processing or advanced bioinformatics expertise. 

Key Features 
1. Comprehensive Transcriptomic Summary Browser
   ◦ Full access to curated differential gene expression data across all 22 datasets
   ◦ Customizable filtering by statistical thresholds (|logFC|, adjusted p-value)
   ◦ Interactive, sortable data tables with one-click export to Excel/CSV formats
2. Differentially Expressed Gene (DEG) Quantification Module
   ◦ Dynamic DEG filtering by contaminant type, species, exposure concentration, exposure duration, and age
   ◦ Real-time DEG count summary statistics and visualization
   ◦ Automated statistical testing of gene set overlap across exposure conditions via Fisher's exact test
3. Transcriptomic Response Visualization ◦ Interactive, publication-ready volcano plots and MA plots with user-defined thresholds
   ◦ Automated labeling of top 10 up- and down-regulated genes
   ◦ High-resolution plot export for academic publications
4. Targeted Adipocyte Gene Expression Profiling
   ◦ Custom gene list query for targeted expression analysis
   ◦ Flexible grouping by exposure condition, concentration, species, and more
   ◦ Multiple visualization options: bar plots (mean ± SD), violin plots, and box plots
5. Pre-computed Functional Genomics Data
   ◦ KEGG pathway enrichment analysis for up- and down-regulated gene sets
   ◦ Disease ontology mapping via the DisGeNET database, with a focus on cardiometabolic endpoints
   ◦ Weighted Key Driver Analysis (wKDA) results to identify master regulators of PPCP-induced adipocyte dysfunction

Data Source & Processing 
All data integrated into this toolkit was retrieved from the Gene Expression Omnibus (GEO) database (accessions up to December 2023), with a rigorous multi-step curation pipeline: 
1. Systematic Retrieval: Keyword searches using common names, IUPAC chemical names, and standard abbreviations for 6 target PPCPs
2. Strict Inclusion/Exclusion Criteria:
   ◦ Included: Human/mouse/rat adipose tissue or adipocyte cell line models, RNA-seq or single-channel microarray platforms, ≥3 biological replicates per group, direct PPCP exposure design
   ◦ Excluded: Transgenerational/prenatal exposure studies, non-adipose tissue datasets, redundant/duplicated entries, studies with incomplete metadata
3. Standardized Processing Pipeline:
   ◦ Microarray data: Processed via the LIMMA package, with log2 transformation for non-normalized matrices
   ◦ RNA-seq data: Quality control via Trim Galore/Cutadapt, pseudo-alignment and quantification via Salmon, differential expression analysis via DESeq2
   ◦ Cross-species normalization: Mouse/rat gene symbols mapped to human orthologs via the HGNC database
4. Meta-Analysis: Consensus DEGs identified via Robust Rank Aggregation (RRA), with functional enrichment via EnrichR and regulatory network analysis via Mergeomics

Access the Web Application
The production version of the PPCP Adipocyte Transcriptomics Toolkit is freely available online, with no local installation required:🔗 https://healthews.shinyapps.io/PPCPToolkit/ 
The application is compatible with all modern web browsers (Chrome, Firefox, Safari, Edge) and optimized for both desktop and tablet use. Local Installation
