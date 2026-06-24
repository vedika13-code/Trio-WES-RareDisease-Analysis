# Trio-WES-RareDisease-Analysis

## Overview

This project implements a complete trio-based Whole Exome Sequencing (WES) workflow to identify candidate de novo variants associated with rare genetic diseases.

The analysis uses the Genome in a Bottle (GIAB) Ashkenazim Trio and follows standard NGS best practices including quality control, read alignment, variant calling, trio comparison, and candidate variant prioritization.

---

## Objective

Identify high-confidence candidate de novo variants in the proband by comparing variant calls against both parents and prioritize candidate variants for downstream rare disease interpretation.

---

## Samples

| Sample | GIAB ID | Relationship |
| ------ | ------- | ------------ |
| HG002  | NA24385 | Proband      |
| HG003  | NA24149 | Father       |
| HG004  | NA24143 | Mother       |

---

## Dataset

**Genome in a Bottle (GIAB) Ashkenazim Trio**

Reference Genome: **GRCh38 (hg38)**

---

## Workflow

```text
FASTQ Files
    ↓
FastQC
    ↓
Trimmomatic
    ↓
Post-trim FastQC
    ↓
MultiQC
    ↓
BWA-MEM Alignment
    ↓
SAM → BAM
    ↓
BAM Sorting & Indexing
    ↓
GATK HaplotypeCaller
    ↓
Individual VCF Generation
    ↓
bcftools Merge
    ↓
Trio VCF Creation
    ↓
Candidate De Novo Variant Discovery
    ↓
Quality Filtering
    ↓
High-Confidence Candidate Variants
```

---

## Tools Used

* FastQC
* MultiQC
* Trimmomatic
* BWA-MEM
* SAMtools
* GATK HaplotypeCaller
* bcftools
* Google Colab
* Google Drive
* GitHub

---

## Analysis Summary

### Variant Calling Results

| Sample          | Variants Identified |
| --------------- | ------------------: |
| HG002 (Proband) |             399,776 |
| HG003 (Father)  |             399,422 |
| HG004 (Mother)  |             400,620 |

### Trio Analysis Results

| Step                               | Variants Remaining |
| ---------------------------------- | -----------------: |
| Proband variants                   |            399,776 |
| Proband-specific variants          |            326,454 |
| High-confidence candidate variants |                916 |

### Candidate Variant Composition

| Variant Type       | Count |
| ------------------ | ----: |
| SNPs               |   818 |
| Indels             |   102 |
| Multiallelic Sites |    47 |

---

## Key Files Generated

### Alignment Files

* proband.bam
* father.bam
* mother.bam

### Variant Files

* proband.vcf
* father.vcf
* mother.vcf
* trio.vcf

### Candidate Variant Files

* denovo_highconf.vcf
* denovo_stats.txt

---

## Results

A trio-based variant comparison workflow was performed using bcftools to identify variants present in the proband and absent from both parents.

Quality filters were applied:

* QUAL ≥ 30
* DP ≥ 10
* GQ ≥ 20

This reduced the candidate set from approximately 400,000 variants to 916 high-confidence candidate variants.

---

## Limitations

Variant calling was performed independently for each sample using GATK HaplotypeCaller and subsequently compared using bcftools.

Joint genotyping using the GVCF workflow:

* HaplotypeCaller (-ERC GVCF)
* CombineGVCFs
* GenotypeGVCFs

was not performed in this version of the project.

Therefore, identified variants should be considered **putative de novo candidate variants** rather than fully validated de novo mutations.

---

## Future Work

* Functional annotation using ANNOVAR, VEP, or snpEff
* ClinVar pathogenicity assessment
* OMIM disease association analysis
* HPO phenotype matching
* Joint-genotyping GVCF workflow
* Candidate gene prioritization

---

## Repository Structure

```text
Trio-WES-RareDisease-Analysis/
│
├── README.md
├── docs/
├── scripts/
├── results/
│
├── proband.vcf
├── father.vcf
├── mother.vcf
├── trio.vcf
│
└── denovo_highconf.vcf
```

---

## Author

**Vedika Goyal**

B.Tech Computer Science and Bioinformatics
VIT Vellore
