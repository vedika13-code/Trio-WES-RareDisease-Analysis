# Trio-Based Whole Exome Sequencing Analysis for Rare Disease Variant Discovery

## Overview

This project implements a complete **trio-based Whole Exome Sequencing (WES) bioinformatics pipeline** for identifying and prioritizing candidate **de novo variants** associated with rare genetic diseases.

The analysis was performed using the **Genome in a Bottle (GIAB) Ashkenazim Trio** benchmark dataset and follows GATK Best Practices for joint variant calling. Downstream annotation and biological interpretation were performed using **ANNOVAR**, **OMIM**, and the **Human Phenotype Ontology (HPO)**.

> **Note:** The GIAB Ashkenazim Trio is a benchmark reference dataset and not a clinical cohort. Therefore, the identified variants are presented as candidate variants for methodological demonstration rather than confirmed disease-causing mutations.

---

## Project Objectives

* Perform quality assessment of raw sequencing reads.
* Trim adapters and low-quality bases.
* Align reads to the GRCh38 (hg38) reference genome.
* Perform variant calling using GATK HaplotypeCaller.
* Conduct joint genotyping across the trio.
* Identify candidate de novo variants.
* Functionally annotate variants using ANNOVAR.
* Prioritize variants using OMIM and HPO databases.
* Interpret biologically relevant candidate variants.

---

## Dataset

| Parameter        | Details                                   |
| ---------------- | ----------------------------------------- |
| Dataset          | Genome in a Bottle (GIAB) Ashkenazim Trio |
| Proband          | HG002 (NA24385)                           |
| Father           | HG003 (NA24149)                           |
| Mother           | HG004 (NA24143)                           |
| Sequencing       | Whole Exome Sequencing (WES)              |
| Platform         | Illumina Paired-End                       |
| Read Length      | 2 × 250 bp                                |
| Reference Genome | GRCh38 (hg38)                             |

---

## Bioinformatics Workflow

```text
FASTQ
   │
FastQC
   │
Trimmomatic
   │
Post-trim FastQC + MultiQC
   │
BWA-MEM Alignment
   │
SAMtools (Sort & Index)
   │
GATK HaplotypeCaller (GVCF)
   │
CombineGVCFs
   │
GenotypeGVCFs
   │
Joint Trio VCF
   │
De Novo Variant Filtering
   │
ANNOVAR Annotation
   │
OMIM Mapping
   │
HPO Mapping
   │
Biological Interpretation
```

---

## Software Used

| Tool              | Version                 |
| ----------------- | ----------------------- |
| FastQC            | Latest                  |
| MultiQC           | Latest                  |
| Trimmomatic       | Latest                  |
| BWA-MEM           | Latest                  |
| SAMtools          | Latest                  |
| BCFtools          | Latest                  |
| GATK              | 4.6.2.0                 |
| ANNOVAR           | Latest                  |
| Google Colab      | Runtime Environment     |
| OrbStack (Ubuntu) | Local Linux Environment |

---

## Repository Structure

```text
Trio-WES-RareDisease-Analysis/
│
├── notebooks/
├── scripts/
├── docs/
├── figures/
├── results/
│   ├── vcf/
│   ├── omim/
│   └── hpo/
├── README.md
└── LICENSE
```

---

## Results Summary

| Result                     |  Count |
| -------------------------- | -----: |
| Candidate de novo variants | 12,776 |
| Coding variants            |    116 |
| Nonsynonymous SNVs         |     72 |
| Synonymous SNVs            |     41 |
| Frameshift deletions       |      2 |
| Nonframeshift deletions    |      1 |

### High-impact Candidate Variants

* **CFTR** – Frameshift deletion (p.G1222Vfs*6)
* **MICU3** – Frameshift deletion (p.T512Lfs*6)
* **RIN3** – Nonframeshift deletion (p.G897del)

---

## Biological Interpretation

Candidate variants were prioritized using functional annotation together with OMIM disease associations and Human Phenotype Ontology (HPO) annotations. Because the GIAB Ashkenazim Trio is a benchmark dataset without clinical phenotype information, biological interpretation focused on demonstrating a reproducible rare disease analysis workflow rather than establishing clinical diagnoses.

---

## Future Improvements

* Base Quality Score Recalibration (BQSR)
* Population frequency filtering (gnomAD)
* Pathogenicity prediction (SIFT, PolyPhen-2, CADD)
* ACMG variant classification
* Clinical phenotype integration
* Experimental validation using Sanger sequencing

---

## Acknowledgements

* Genome in a Bottle (GIAB)
* Broad Institute GATK Team
* ANNOVAR
* OMIM
* Human Phenotype Ontology (HPO)
* National Center for Biotechnology Information (NCBI)

---

## Author

**Vedika Goyal**

B.Tech Computer Science and Engineering (Bioinformatics)

VIT Vellore

2026
