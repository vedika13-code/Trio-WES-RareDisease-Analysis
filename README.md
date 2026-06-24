# Trio-WES-RareDisease-Analysis

## Overview

This project implements a complete trio-based Whole Exome Sequencing (WES) workflow to identify candidate de novo variants associated with rare genetic diseases.

The analysis uses the Genome in a Bottle (GIAB) Ashkenazim Trio and follows standard NGS best practices including quality control, read alignment, variant calling, annotation, and rare disease interpretation.

---

## Objective

Identify high-confidence candidate de novo variants in the proband by comparing variants against both parents and perform downstream rare disease interpretation.

---

## Samples

| Sample | GIAB ID | Relationship |
| ------ | ------- | ------------ |
| HG002  | NA24385 | Proband      |
| HG003  | NA24149 | Father       |
| HG004  | NA24143 | Mother       |

---

## Dataset

Genome in a Bottle (GIAB) Ashkenazim Trio

Reference Genome: GRCh38 (hg38)

---

## Workflow

1. FastQC Quality Assessment
2. Adapter and Quality Trimming (Trimmomatic)
3. Post-trimming Quality Control
4. MultiQC Summary Report
5. Alignment using BWA-MEM
6. BAM Processing and Indexing
7. Variant Calling using GATK HaplotypeCaller
8. Trio VCF Generation
9. De Novo Variant Filtering
10. Variant Annotation
11. Rare Disease Interpretation
12. Final Candidate Variant Prioritization

---

## Tools Used

* FastQC
* MultiQC
* Trimmomatic
* BWA-MEM
* SAMtools
* GATK
* BCFtools
* ANNOVAR
* GitHub

---

## Current Progress

### Completed

* FastQC
* Trimmomatic
* Post-trim FastQC
* MultiQC
* hg38 Download
* BWA Indexing
* Alignment
* BAM Processing
* BAM Indexing

### In Progress

* GATK HaplotypeCaller

### Planned

* Trio VCF Merge
* De Novo Variant Detection
* Annotation
* OMIM Interpretation
* HPO Matching
* Final Report

---

## Repository Structure

See the docs folder for workflow details and project logs.

---

## Author

Vedika Goyal

B.Tech Computer Science and Bioinformatics
VIT Vellore
