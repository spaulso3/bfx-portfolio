# Single-cell RNA-seq Overview  

Single-cell RNA-seq (scRNA-seq) extends traditional RNA-seq by measuring gene expression at the level of individual cells rather than bulk tissue. Instead of averaging signals across many cells, you get a high-resolution view of cell diversity within a sample.

In practice, scRNA-seq shifts the question from:

“What genes are expressed in this tissue?” → “What cell types are present, and what are they doing?”

---

## Key Differences from Bulk RNA-seq  

Bulk RNA-seq measures the **average expression across all cells**, while single-cell RNA-seq resolves **cell-to-cell variability**.

### Bulk RNA-seq  
- Measures average gene expression across many cells  
- Good for detecting overall changes between conditions  
- Masks rare cell populations  
- Simpler and more stable statistically

### Single-cell RNA-seq  
- Measures expression in individual cells  
- Reveals cell type composition and heterogeneity 
- Captures rare or transient cell states  
- More noisy and sparse data

### Key technical differences  
- scRNA-seq data is sparse (lots of zeros) due to dropout  
- Requires specialized normalization methods  
- Higher dimensionality (thousands of cells × thousands of genes)  
- Strong dependence on computational clustering  

---

## Clustering Concept
Clustering is the process of grouping cells based on similarity in their gene expression profiles.

### Core idea  
Cells with similar expression patterns are assumed to represent:
- The same cell type 
- Or a similar cell state

### Typical workflow  
1. Normalize expression data  
2. Identify highly variable genes  
3. Reduce dimensionality (PCA → UMAP/t-SNE)  
4. Cluster cells (graph-based clustering methods)  
5. Assign biological labels to clusters

### Common tools  
- Seurat (R)  
- Scanpy (Python)

### Visualization methods  
- UMAP (most commonly used)  
- t-SNE
- PCA

### Why clustering matters  
- Converts thousands of cells into interpretable groups  
- Enables identification of unknown cell types  
- Helps detect rare populations

---

## Biological Interpretation
Once clusters are identified, the main goal is to connect them back to biology.

### 1. Cell type identification  
Clusters are annotated using known marker genes:
- Example:  
  - CD3D → T cells  
  - EPCAM → epithelial cells  
  - PTPRC (CD45) → immune cells

### 2. Cell state analysis  
Beyond identity, clusters can reflect:
- Activation states  
- Stress responses  
- Cell cycle phases  
- Differentiation stages

### 3. Heterogeneity within tissues  
scRNA-seq reveals:
- Mixed cell populations in what previously looked like “one tissue type”  
- Rare cell populations that bulk RNA-seq would miss  
- Continuous transitions between states (not always discrete groups)

### 4. Biological insight strategy  
When interpreting results, think in layers:
- What clusters exist?
- What genes define them? 
- Do they match known biology?
- Are there unexpected or novel populations?

---

## Common Pitfalls
- Over-interpreting clusters as strict “cell types” (they may be gradients)  
- Ignoring batch effects or technical variation  
- Relying only on UMAP visualization without marker validation  
- Confusing clustering artifacts with biological signal  

---
## Big Picture Summary
Single-cell RNA-seq adds a new dimension to transcriptomics:
- Bulk RNA-seq → averages across cells  
- scRNA-seq → resolves individual cellular identities  

The real power comes from combining:
- Clustering (computational structure)  
- Marker genes (biological interpretation)  
- Context (tissue and experimental design)  

It’s less about “genes changing” and more about **which cells are present and what states they represent**.

---
