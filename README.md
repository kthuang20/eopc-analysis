# Identifying Genetic Risk Factors for Pancreatic Cancer

## Background
Using a CRISPR/Cas9 screen was done in pancreatic cells taken from a healthy 39-year-old woman who has a family history of EOPC, the research team has found something interesting on chromosome 18. Another member of the lab has already processed some genome sequencing data (`candidate_EOPC_variants.vcf`) from 473 EOPC patients and 891 cancer-free adults to generate germline variants matching the top 3,364 variants from our collaborator’s in vitro screen. The sample phenotypes have also been provided in the file called `phenotypes.tsv`. Both these files are located in the `data/raw/` folder.

## Objective
The objective of this project is to identify whether any genetic variants from the are associated with pancreatic cancer risk.

## Components of this project

The environment and dependencies used in this project are detailed in the `pixi.toml` file.

This code has been separated into two notebooks:
* `01_Preprocessing_Steps.ipynb` – describes the steps taken to set up bcftools and generating the non-reference allele count matrix.
* `02_Association_Analysis.ipynb` – describes the steps taken to prepare the data for modeling, modeling, and the Manhattan plot visualizing any genetic variants that are associated with early onset of pancreatic cancer (EOPC) status.
***NOTE:*** The intermediate files from the analysis can be found in the `data/processed/` folder.

The `results/` folder contains the results from this analysis:
* `manhattan_plot.png` – Manhattan plot summarizing the genetic variant association to pancreatic cancer of 2,784 genetic variants, accounting for ancestry and smoking history. The top 8 genetic variants (all with $p < 1x10^{-8}$) associated with EOPC risk have been annotated with their position on chromosome 18.
* `top_100_variants.tsv` – a ranked list of the top 100 variants most strongly associated with EOPC risk have been exported to the `results` folder as `top_100_variants.tsv`. It includes the genomic position & alleles, odds ratio of the non-reference allele count, β for the non-reference allele count and p-value.
