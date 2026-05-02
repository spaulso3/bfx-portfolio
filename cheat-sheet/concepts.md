# Useful Commands / Concepts
Understanding core computational concepts is essential for interpreting sequencing data and executing bioinformatics workflows. The following concepts are frequently used across DNA-seq and RNA-seq analyses.

---

## Alignment Basics
Alignment is the process of mapping sequencing reads to a reference genome to determine their genomic origin.

**Common tools:**
- BWA (Burrows-Wheeler Aligner)
- Bowtie2
- HISAT2 (for RNA-seq)

**Basic command example (BWA):**

bwa mem reference.fasta reads.fastq > aligned.sam

**Key ideas:**
- Reads are matched to the reference genome based on sequence similarity  
- Mismatches and gaps may occur due to sequencing errors or true biological variation  
- Output is typically stored in SAM/BAM format  

---

## Read Depth

Read depth (or sequencing depth) refers to the number of reads that cover a specific genomic position.

**Example command (SAMtools):**

samtools depth aligned.bam

**Key points:**
- Higher depth increases confidence in base calls and variant detection  
- Low-depth regions are more prone to errors  
- Often expressed as "X" (e.g., 30× means each base is read ~30 times on average)  

---

## Coverage
Coverage describes how much of the genome (or a target region) is represented by sequencing reads.

**Types of coverage:**
- Breadth of coverage → Percentage of the genome covered by reads  
- Depth of coverage → Number of reads per position (closely related to read depth)  

**Example command:**

samtools coverage aligned.bam

**Key points:**
- High coverage ensures more complete genome representation  
- Uneven coverage can result from GC bias or sequencing limitations  

---

## Variant Types

Variants are differences between a sample and the reference genome.

**Common types:**
- **SNPs (Single Nucleotide Polymorphisms)** → Single base changes  
- **Insertions (INS)** → Addition of nucleotides  
- **Deletions (DEL)** → Loss of nucleotides  
- **Structural variants (SVs)** → Larger changes (e.g., duplications, inversions, translocations)

**Key points:**
- Variant calling tools (e.g., GATK, FreeBayes) identify these differences  
- Interpretation depends on genomic context (coding vs non-coding regions)  
- Some variants are benign, while others may impact gene function or disease risk  

---

## Summary

- **Alignment** → Maps reads to a reference genome  
- **Read depth** → Number of reads at a specific position  
- **Coverage** → Extent and uniformity of sequencing across the genome  
- **Variant types** → Differences between sample and reference genome  

These concepts form the foundation for downstream analyses such as variant calling, gene expression quantification, and genomic interpretation.
