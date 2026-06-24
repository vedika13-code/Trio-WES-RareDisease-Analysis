# Workflow

FASTQ
↓
FastQC
↓
Trimmomatic
↓
FastQC
↓
MultiQC
↓
BWA-MEM Alignment
↓
SAM → BAM
↓
Sorting
↓
Indexing
↓
GATK HaplotypeCaller
↓
Individual VCFs
↓
bcftools Merge
↓
Trio VCF
↓
De Novo Filtering
↓
Annotation
↓
Rare Disease Interpretation
