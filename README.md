# Trio-WES-RareDisease-Analysis

## Overview

This project implements an end-to-end trio-based Whole Exome Sequencing (WES) workflow using the Genome In A Bottle (GIAB) Ashkenazim Trio to identify candidate de novo variants and perform rare disease interpretation.

The workflow follows standard bioinformatics practices including quality control, read trimming, alignment, variant calling, trio-based filtering, annotation, and phenotype interpretation.

---

## Dataset

### GIAB Ashkenazim Trio

| Sample | Identifier | Role    |
| ------ | ---------- | ------- |
| HG002  | NA24385    | Proband |
| HG003  | NA24149    | Father  |
| HG004  | NA24143    | Mother  |

Reference Genome:

* Human Genome Assembly GRCh38 (hg38)

---

## Workflow

```text
FASTQ
 ↓
FastQC
 ↓
Trimmomatic
 ↓
BWA-MEM Alignment
 ↓
SAMtools Sort & Index
 ↓
GATK HaplotypeCaller
 ↓
VCF Generation
 ↓
Trio VCF Merge
 ↓
De Novo Variant Filtering
 ↓
Annotation
 ↓
OMIM Interpretation
 ↓
HPO Phenotype Matching
```

---

## Tools

* FastQC
* MultiQC
* Trimmomatic
* BWA-MEM
* SAMtools
* GATK 4.6.2.0
* bcftools
* ANNOVAR

---

## Project Status

* [x] Quality Control
* [x] Read Trimming
* [x] Alignment
* [x] BAM Processing
* [ ] Variant Calling
* [ ] Trio VCF Merge
* [ ] De Novo Filtering
* [ ] Annotation
* [ ] Clinical Interpretation

---

## Expected Outputs

* BAM files for all trio members
* Individual VCF files
* Merged Trio VCF
* Candidate de novo variant table
* Annotated variant report
* OMIM interpretation
* HPO phenotype matching
* Final diagnostic report

---

## Author

*Vedika Goyal
*B.Tech Computer Science and Bioinformatics
