# Gene Prediction
Gene prediction is the process of identifying genomic regions that are likely to encode genes. This step is about finding structure in raw sequence data, especially in newly sequenced or less-annotated genomes.

In practice, gene prediction sits somewhere between computation and biology, as it relies heavily on algorithms but still requires biological validation.

---

## Command-line Tools Used  

### Common tools  
- AUGUSTUS  
- GeneMark  
- Glimmer (mainly prokaryotes)  
- SNAP

### What they do  
These tools predict:
- Protein-coding genes  
- Exon-intron structure  
- Start and stop codons  
- Potential splice sites

### How they work
Most command-line tools rely on:
- Hidden Markov Models (HMMs)  
- Training sets from known genes  
- Statistical patterns in coding DNA

### Why they’re used  
- Scalable for whole-genome annotation  
- Useful for non-model organisms
- Can run locally on large datasets  

---

## Web-Based Tools  

### Common platforms  
- NCBI ORF Finder  
- Ensembl annotation pipeline 
- UCSC Genome Browser gene tracks

### What they provide  
- Quick visualization of predicted genes  
- Open reading frame (ORF) detection  
- Comparison with known annotations  
- Interactive exploration of gene structure

### Why they’re useful  
- No setup required  
- Good for quick validation  
- Helpful for educational or exploratory work

---

## Basic Methodology  

Gene prediction typically follows a combination of ab initio prediction and evidence-based annotation.

### 1. Ab initio prediction  
- Uses only the DNA sequence  
- Detects coding signals like:
  - Start/stop codons  
  - Codon usage bias  
  - Splice site motifs  
- Does NOT require external data

### 2. Evidence-based prediction  
- Uses external biological data:
  - RNA-seq alignments  
  - Protein homology  
  - Known gene annotations  
- Much more accurate than ab initio alone

### 3. Hybrid approaches  
Most modern pipelines combine both:
- Ab initio predictions provide candidates  
- Evidence-based data refines and validates them  

---

## Limitations
Gene prediction is powerful but far from perfect.

### 1. False positives  
- Random sequences may resemble genes  
- Especially problematic in large genomes

### 2. False negatives  
- Small or unusual genes may be missed  
- Lowly expressed genes are harder to detect

### 3. Complex gene structures  
- Alternative splicing complicates prediction  
- Overlapping genes can confuse models

### 4. Training bias  
- Models perform best on organisms similar to training data  
- Non-model organisms often have lower accuracy

### 5. Lack of functional validation  
- Prediction ≠ confirmed gene  
- Experimental validation is still required  

---

## Interpretation Perspective  

Treat prediction as:
- Hypotheses about gene structure, not final answers  
- Stronger when supported by RNA-seq or protein evidence  
- More reliable in well-annotated genomes  

---

## Big Picture Summary  

Gene prediction is the starting point of genome annotation:

- Raw DNA sequence  
→ computational prediction of genes  
→ refinement with biological evidence  
→ integration into genome databases  

It’s essentially the step that turns an unannotated genome into something biologically interpretable.

---
