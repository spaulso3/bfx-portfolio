# UCSC Genome Browser
## Overview
The [UCSC Genome Browser](https://genome.ucsc.edu/cgi-bin/hgGateway) is a web-based tool for visualizing genomic regions and integrating biological data, including gene annotations, sequence conservation, regulatory elements, and known variants. It is one of the most widely used platforms for exploring genome structure and function.

![main-page.png](../images/ucsc/main-page.png)
*The UCSC Genome Browser landing page.*
## When to Use
Use UCSC to:
* Explore gene structure (exons, introns, alternative splicing)
* Visualize genomics regions and coordinates
* Investigate regulatory elements (promoters, enhancers)
* Examine conservation across species
* View known variants in context
## Key Features
* **Genome Navigation**: Search by gene name, coordinates, or variant ID
* **Track System**: Layer multiple data types (genes, variants, regulatory regions)
* **Comparative Genomics**: View conservation across species
* **Custom Tracks**: Upload your own data
* **Integration with Databases**: Links to external resources and annotations
## Example Workflow
### Goal: Investigate a gene and its surrounding genomic features
1. Go to [UCSC Genome Browser](https://genome.ucsc.edu/cgi-bin/hgGateway)
2. Select the appropriate reference genome (e.g., Human - GRCh38/hg38)
3. Enter a gene name (e.g., *BRCA1*)
4. Adjust the genomic region
5. Enable relevant tracks:
   * Gene annotations
   * Conservation
   * Regulatory elements
   * Variants
6. Explore:
   * Exon/intron structure
   * Conserved regions
   * Nearby variants

![brca1-overview.png](../images/ucsc/brca1-overview.png)
*The default UCSC Genome Browser tracks viewing the BRCA1 gene region*
## Key Tracks
### Gene Annotation (GENCODE, RefSeq, MANE)
* Defines exon-intron structure and transcript isoforms
* Provides the foundation for interpreting all other data
* MANE Select represents a standardized transcript
### OMIM (Disease Context)
* Links genes/variants to disease
### Variants (dbSNP)
* Known SNPs across the region
* Pair with:
  * [ClinVar](https://www.ncbi.nlm.nih.gov/clinvar/) ⮕ clinical significance
  * [gnomAD](https://gnomad.broadinstitute.org/) ⮕ population allele frequency
### Conservation (100 Vertebrates)
* Highlights evolutionarily conserved (thus likely important) sequences across species
### Regulation (ENCODE cCREs, Layered H3K27ac)
* Identifies promoters/enhancers
* H3K27ac peaks mark active regulatory regions
### Expression (GTEx)
* Tissue-specific gene expression
### Repeats (RepeatMasker)
* Identifies repetitive regions (important for alignment/variant interpretation)
## Interpretation Strategy
* Gene + conservation = functional regions
* Variants + frequency = benign vs. impactful
* Regulatory + histone marks = gene regulation
* Expression = tissue relevance
## Common Pitfalls
* Using the wrong genome build can lead to incorrect coordinates
* Overinterpreting single tracks without cross-referencing other data
* Ignoring or overloading track settings
## Alternative Genome Browsers
* [Ensembl](http://www.ensembl.org/) 
* [NCBI Genome Data Viewer](https://www.ncbi.nlm.nih.gov/gdv/)
# Personal Notes
* Turning tracks on/off can avoid clutter.
* Most useful when combined with other external databases