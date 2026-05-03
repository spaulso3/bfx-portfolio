# Tool Selection Guide

Selecting the appropriate tool is a critical step in bioinformatics workflows. Different tools are optimized for specific types of analyses, and choosing the correct resource ensures accurate and efficient interpretation of genomic data.

---

## If I Need → Use This

| Task | Recommended Tool | Purpose | Why This Tool |
|------|------------------|---------|---------------|
| Variant pathogenicity | ClinVar | Clinical classification of variants | Aggregates expert-reviewed clinical interpretations |
| Population frequency | gnomAD | Allele frequency in large populations | Helps distinguish rare vs common variants |
| Genomic visualization | UCSC Genome Browser | Explore genomic regions and annotations | Integrates multiple tracks in one interface |
| Regulatory elements | ENCODE | Identify promoters and enhancers | Provides experimental evidence of regulatory activity |
| Gene annotation | GENCODE / RefSeq / MANE | Gene structure and transcripts | Standard reference annotations |
| Gene expression | GTEx | Tissue-specific expression data | Useful for understanding gene relevance in tissues |
| Read alignment | BWA / HISAT2 | Map reads to reference genome | Fast and widely used alignment tools |
| Variant calling | GATK / FreeBayes | Identify genetic variants | Robust and widely adopted pipelines |

---

## Summary

- Tool selection depends on the biological question being asked  
- Combining multiple tools provides stronger evidence and validation
- Understanding tool strengths and limitations is essential for accurate interpretation  

This guide provides a quick reference for selecting appropriate tools across common bioinformatics tasks.
