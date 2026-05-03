# Common Pitfalls

Bioinformatics analyses are powerful but prone to misinterpretation if limitations are not considered. Recognizing common pitfalls is essential for producing accurate and reliable results.

---

## Misinterpreting Variants

- Not all variants are clinically significant  
- Variants of Uncertain Significance (VUS) should not be overinterpreted  
- Conflicting database annotations (e.g., ClinVar) require careful evaluation  

Key takeaway: Always integrate multiple sources of evidence before drawing conclusions.

---

## Low Coverage Issues

- Regions with low read depth may produce unreliable results  
- Variants detected in low-coverage areas are more likely to be false positives  
- Important regions may be missed entirely  

Key takeaway: Check coverage before trusting variant calls.

---

## Database Limitations

- Databases may be incomplete or biased toward certain populations  
- Absence of a variant in a database does not imply it is novel or pathogenic  
- Clinical annotations may be outdated or conflicting  

Key takeaway: Databases are tools, not definitive answers.

---

## Alignment Errors

- Reads may map incorrectly in repetitive regions  
- Structural variants are harder to detect accurately  
- Misalignment can lead to false variant calls  

Key takeaway: Validate results, especially in complex genomic regions.

---

## Overreliance on Single Tools

- Different tools use different algorithms and assumptions  
- Results may vary between pipelines  
- Using only one tool can introduce bias  

Key takeaway: Cross-validate results with multiple tools when possible.

---

## Summary

- Bioinformatics results require critical evaluation, not just execution  
- Awareness of limitations improves accuracy and reliability  
- Combining tools and evidence leads to more robust conclusions  

Understanding these pitfalls is essential for responsible and effective genomic analysis.
