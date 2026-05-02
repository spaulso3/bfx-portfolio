# DNA-seq Variant Analysis Workflow  

This section summarizes the basic end-to-end workflow for DNA sequencing analysis. In practice, this is moving from raw reads → aligned genome → called variants → biological meaning.

The exact tools can vary, but the structure is fairly consistent across pipelines.

---

## Overview (FASTQ → BAM → VCF)

A standard DNA-seq workflow follows this progression:

1. **FASTQ** → raw sequencing reads  
2. **BAM** → aligned reads mapped to a reference genome  
3. **VCF** → identified genetic variants  

Each step reduces “raw signal” into something more biologically interpretable.

---

## Alignment  
 
Alignment is the process of mapping sequencing reads back to a reference genome.

### Input / Output  
- Input: FASTQ files (raw reads)  
- Output: SAM/BAM/CRAM files (aligned reads)

### Common tools  
- BWA-MEM  
- Bowtie2  
- minimap2 (more long-read focused)

### What happens conceptually  
- Reads are matched to the most likely location in the reference genome  
- Mismatches are allowed (due to sequencing errors or real variants)  
- Output includes mapping quality scores

### Why it matters  
- Misalignment = false variant calls later  
- Repetitive regions are especially challenging  
- Reference genome choice (hg19 vs hg38) affects everything downstream  

---

## Variant Calling  

Variant calling identifies differences between the aligned sample and the reference genome.

### Input / Output  
- Input: BAM/CRAM files  
- Output: VCF file (Variant Call Format)

### Common tools  
- GATK (HaplotypeCaller)  
- FreeBayes  
- bcftools  

### Types of variants detected  
- SNVs (single nucleotide variants)  
- Indels (insertions/deletions)  
- Sometimes structural variants

### Key idea  
The pipeline is essentially asking: **“Where does this sample differ from the reference genome with high confidence?”**

---

## Annotation (ClinVar, gnomAD, etc.)

Annotation adds biological and clinical context to raw variants.

### Input / Output  
- Input: VCF file  
- Output: annotated VCF or tabular output

### Common annotation resources  
- ClinVar → clinical significance  
- gnomAD → population frequency  
- Ensembl / VEP → transcript-level effects  
- dbSNP → known variant IDs

### What gets added  
- Gene context 
- Functional effect (missense, nonsense, intronic, etc.)  
- Population frequency  
- Clinical interpretation  

---

## Interpretation  

This is the step where raw computational output becomes biological insight.

One should generally filter and prioritize variants using a combination of:

#### 1. Frequency (gnomAD)
- Common variants → likely benign  
- Rare variants → higher interest  

#### 2. Clinical evidence (ClinVar)
- Pathogenic / likely pathogenic → higher confidence  
- VUS → uncertain, needs more context  

#### 3. Functional context (UCSC / ENCODE)
- Coding vs noncoding region  
- Regulatory overlap  
- Conservation signals  

#### 4. Gene relevance
- Known disease-associated genes carry more weight  
- Tissue-specific expression can matter

### Typical filtering strategy  
1. Remove low-quality calls  
2. Filter out common variants (high gnomAD frequency)  
3. Prioritize variants in relevant genes  
4. Check ClinVar for known clinical associations  
5. Evaluate functional context (coding/regulatory impact)

---

## Common Pitfalls  

- Treating VCF files as “final answers” rather than probabilistic calls  
- Ignoring alignment artifacts (especially in repetitive regions)  
- Over-relying on a single annotation source  
- Confusing rarity with pathogenicity  

---

## Big Picture Summary  

DNA-seq analysis is really a "progressive refinement process":

- FASTQ → raw signal  
- BAM → genomic location  
- VCF → differences from reference  
- Annotation → biological meaning  
- Interpretation → clinical or functional insight  

Each step depends heavily on the one before it, so small errors early on can propagate downstream.

---
