# CHU Montpellier long-read / Oxford Nanopore feasibility context

**Date:** 2026-09-07  
**Scope:** deliberately restricted to elements directly useful for establishing feasibility at **CHU Montpellier / PMMG**.

## Bottom line

The feasibility argument does not need a broad inventory of the Montpellier ecosystem. It can rest on three direct points:

1. **The project is based at the PMMG, R+3**, within the CHU molecular-genomics environment.
2. **CHU teams already have published long-read / ONT experience**, including direct use of MinION/Flongle in an oncology-related workflow.
3. **The clinically oriented bioinformatics expertise is already present at MOBIDIC / PMMG**, including published handling of ONT reads, long-read alignment, custom scripting and structural-variant calling.

This supports a credible feasibility claim without implying that an end-to-end rapid CNS nanopore workflow is already in routine use.

---

## 1. Existing CHU long-read experience

### Perrin et al., 2022 — TTN

**Long-Reads Sequencing Strategy to Localize Variants in TTN Repeated Domains**  
*The Journal of Molecular Diagnostics* 24(7):719–726.  
DOI: `10.1016/j.jmoldx.2022.04.006`

CHU Montpellier teams implemented a third-generation long-read strategy to localise variants in highly repetitive `TTN` domains that were difficult to resolve by short reads.

**Feasibility message:** long-read sequencing expertise is not new to the CHU molecular-genetics environment.

---

## 2. Existing ONT experience in an oncology-related CHU workflow

### Ban et al., 2024 — PALB2

**Characterizing PALB2 intragenic duplication breakpoints in a triple-negative breast cancer case using long-read sequencing**  
*Frontiers in Oncology* 14:1355715.  
DOI: `10.3389/fonc.2024.1355715`

CHU-linked affiliations include Biologie des Tumeurs Solides, Medical Genetics, ChromoStem and **Montpellier BioInformatics for Clinical Diagnosis (MOBIDIC), Molecular Medicine and Genomics Platform (PMMG), CHU Montpellier**.

### Reported ONT workflow

- ONT SQK-LSK114 library;
- Flongle FLO-FLG114;
- **MinION Mk1B**;
- Guppy basecalling;
- Minimap2 alignment;
- IGV review;
- in-house scripts;
- Sniffles structural-variant calling;
- RepeatMasker / ClustalW for breakpoint context.

**Feasibility message:** the CHU has already implemented a complete targeted ONT wet-lab + computational workflow in an oncology/genetics context.

**Limitation:** this was a targeted germline/oncogenetics application, not native low-pass whole-genome sequencing of a fresh CNS tumour.

---

## 3. Bioinformatics expertise at PMMG / MOBIDIC

The same publication provides direct evidence that **MOBIDIC / PMMG** has already worked with the main computational building blocks required for long-read analysis:

- ONT basecalling;
- long-read mapping;
- inspection/QC of long-read alignments;
- custom scripting;
- structural-variant detection;
- breakpoint interpretation.

For a future CNS workflow, additional modules would still need to be implemented/validated locally, particularly:

- real-time methylation calling;
- sparse CNS methylation classification;
- low-pass genome-wide CNV calling;
- integrated reporting of methylation + CNV ± targeted SNV/SV.

The important feasibility point is that **the necessary bioinformatics team and general long-read competence are already in place**, rather than needing to create a computational capability from zero.

---

## 4. Direct CHU scientific connection to CNS nanopore classification

### Filser et al., 2025 — medulloblastoma

**Nanopore sequencing as a cutting-edge technology for medulloblastoma classification**  
*Neuro-Oncology* 27(5):1313–1324.  
DOI: `10.1093/neuonc/noae279`

CHU Montpellier co-authors include **Valérie Rigau** and **Gilles Palenzuela**.

Key performance results include:

- 44 frozen medulloblastomas benchmarked against EPIC arrays;
- **42/44 (95.5%)** correctly subgrouped in that benchmark cohort;
- **106/116 (91.4%)** correctly subgrouped in the integrated-diagnosis cohort;
- Flongle subset: **17/18 (94.4%)** correctly classified;
- subtype classification: **28/30 (93.3%)**.

**Feasibility message:** CHU Montpellier clinicians/scientists are already connected to a peer-reviewed nanopore CNS-tumour classification programme.

**Caveat:** the study was led by Institut Curie; public information does not prove that the sequencing runs were physically performed at CHU Montpellier.

---

## 5. Feasibility statement suitable for later project drafting

> **The study would be conducted within the PMMG (R+3), where long-read sequencing experience and the required clinically oriented bioinformatics expertise are already present. CHU Montpellier teams have previously published ONT-based analyses, including MinION/Flongle sequencing and long-read structural-variant analysis, and CHU investigators have participated in a recent Neuro-Oncology study applying nanopore methylation/CNV profiling to medulloblastoma. The project therefore builds on existing local expertise while addressing a capability not yet validated locally: rapid integrated nanopore profiling of CNS tumours.**
