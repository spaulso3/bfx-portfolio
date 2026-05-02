# RNA-seq Analysis Workflow  

RNA-seq analysis is used to measure gene expression by sequencing RNA transcripts and mapping them back to the genome. Compared to DNA-seq, the goal here is not variation discovery but **quantifying how much each gene is expressed and how expression changes across conditions**.

The workflow generally moves from **raw reads → clean reads → aligned reads → expression values → differential expression results**.

---

## Quality Control
Quality control is the first step where raw sequencing data is evaluated for issues like low-quality reads, adapter contamination, or sequencing bias.

### Input / Output  
- Input: FASTQ files  
- Output: QC reports + cleaned FASTQ files

### Common tools  
- FastQC  
- MultiQC  
- Trimmomatic / Cutadapt (for trimming)

### What is assessed  
- Per-base sequence quality  
- GC content distribution  
- Adapter contamination  
- Sequence duplication levels  
- Read length distribution

### Why it matters  
- Poor-quality reads can distort expression estimates  
- Adapter contamination can cause misalignment  
- QC determines whether trimming or filtering is needed  

---

## Alignment
Alignment maps RNA-seq reads back to a reference genome while accounting for splicing (exon–exon junctions).

### Input / Output  
- Input: cleaned FASTQ files  
- Output: BAM/CRAM files

### Common tools  
- STAR (most common for RNA-seq)  
- HISAT2

### Key concept: splicing-aware alignment  
Unlike DNA-seq, RNA reads often span exon boundaries, so aligners must:
- Detect splice junctions  
- Map reads across introns  
- Handle multiple transcript isoforms

### Why it matters  
- Incorrect alignment → incorrect expression estimates  
- Splice-aware mapping is critical for eukaryotic genomes  
- Isoform ambiguity can affect downstream quantification  

---

## Quantification
Quantification measures how many reads map to each gene or transcript to estimate expression levels.

### Input / Output  
- Input: BAM files (or FASTQ for pseudoalignment tools)  
- Output: gene or transcript count matrix

### Common tools  
- featureCounts  
- HTSeq-count

### Output types  
- Raw counts (used for statistical testing)  
- Normalized expression values (TPM, FPKM, CPM)

### Key idea  
“How many reads correspond to each gene or transcript?”

### Why it matters  
- Forms the basis for all downstream expression analysis  
- Different tools can produce slightly different quantification results  
- Transcript-level vs gene-level quantification changes interpretation  

---

## Differential Expression
Differential expression analysis identifies genes whose expression levels differ significantly between conditions (e.g., disease vs control).

### Input / Output  
- Input: count matrix  
- Output: list of differentially expressed genes (DEGs)

### Common tools  
- DESeq2  
- edgeR

### Key outputs  
- log2 fold change  
- p-values and adjusted p-values 
- significance thresholds

### What it tells you  
- Which genes are upregulated or downregulated  
- Strength and significance of expression changes  
- Biological differences between conditions  

---

## Interpretation  

At this stage, we need to ask:

### 1. Biological relevance  
- Are the genes linked to known pathways or diseases?  
- Do they cluster into functional categories?  

### 2. Magnitude vs significance  
- Large fold change ≠ always biologically meaningful  
- Small but consistent changes can still matter  

### 3. Context dependence  
- Tissue type matters a lot  
- Experimental design (batch effects, replicates) is critical  

---

## Common Pitfalls
- Ignoring batch effects (one of the biggest issues in RNA-seq)  
- Confusing transcript-level and gene-level expression  
- Over-interpreting small sample sizes  
- Treating normalized values as raw counts  

---

## Big Picture Summary  

RNA-seq analysis follows a clear progression:

- **Quality control** → ensure data is usable  
- **Alignment** → map reads to genome (splice-aware)  
- **Quantification** → measure expression levels  
- **Differential expression** → identify biological changes  

The final goal is not just a list of genes, but a biological story about how gene expression changes across conditions.

---
