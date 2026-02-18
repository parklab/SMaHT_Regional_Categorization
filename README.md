# SMaHT_Regional_Categorization
This repository has the description of the hg38 genome categorization of easy, difficult, and extreme region.

## Genomic Region Stratification for Mosaic Variant Benchmarking

This repository provides a three-tier genomic region stratification framework designed to evaluate somatic and mosaic variant detection performance across genomic contexts. Regions are categorized based on **practical variant callability**, integrating population-scale accessibility masks and pan-genome mappability resources.

All coordinates are defined on **GRCh38**, with an official reference genome used in SMaHT (Somatic Mosiacism across Human Tissue) Network.

---

## Genomic Region Definitions

| Category | Definition | Interpretation for Variant Calling | Source |
|--------|------------|-------------------------------------|--------|
| **Easy** | Regions included in the **1000 Genomes Project strict accessibility mask** | Most confidently mappable and consistently variant-callable regions across diverse human samples; minimal short-read artifacts | 1000 Genomes Project strict mask ([link](https://github.com/1000genomes/)) |
| **Difficult** | Regions included in **PanMask pm151 (strict)** but excluded from the 1000 Genomes strict mask | Moderately mappable regions where short-read variant calling is feasible but error-prone; elevated method-dependent artifacts | PanMask pm151 (Li *et al.*, 2025) ([link](https://github.com/lh3/pangraph)) |
| **Extreme** | Regions outside both the 1000 Genomes strict mask and PanMask pm151 | Poorly resolved regions including highly repetitive or structurally complex loci; unreliable for low-VAF variant detection | Not covered by population or pan-genome masks |

---

## Notes on Source Resources

- **1000 Genomes strict accessibility mask**  
  Defines genomic regions that are consistently accessible across population samples and are widely used for benchmarking and analytical validation in short-read sequencing.

- **PanMask pm151**  
  A pan-genome–based accessibility framework derived from hundreds of high-quality human assemblies, designed to reduce reference bias and better represent structural and repetitive complexity across genomes.

---

## Intended Use

This stratification is intended for:

- Benchmarking mosaic and somatic variant callers  
- Comparing sensitivity and precision across genomic contexts  
- Identifying region-specific error modes and guiding method development  


