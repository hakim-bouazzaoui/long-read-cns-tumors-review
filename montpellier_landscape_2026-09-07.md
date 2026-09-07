# Montpellier long-read / Oxford Nanopore landscape

**Date of scan:** 2026-09-07  
**Scope:** CHU Montpellier and the immediately connected Montpellier academic/clinical ecosystem (Université de Montpellier, IGF/MGX, PMMG/MOBIDIC, IRCM/ICM), with emphasis on oncology, neuropathology/CNS tumours, infrastructure and bioinformatics.

## Executive conclusion

### Confirmed by public evidence

1. **Long-read / Oxford Nanopore sequencing has already been used by CHU Montpellier teams.**
   - TTN repeated-domain variant localisation in *The Journal of Molecular Diagnostics* (2022).
   - PALB2 intragenic duplication breakpoint characterisation in *Frontiers in Oncology* (2024), with CHU Montpellier Biologie des Tumeurs Solides, Medical Genetics, ChromoStem and **MOBIDIC / PMMG** affiliations.

2. **There is an established ONT-capable genomics platform in Montpellier.**
   - Montpellier GenomiX (MGX), at the IGF / Arnaud-de-Villeneuve campus, publicly lists an **Oxford Nanopore MinION**, long-read gDNA library preparation, direct RNA-seq ONT library preparation and bioinformatics/statistical support.

3. **CHU Montpellier has participated in a peer-reviewed nanopore CNS-tumour study.**
   - Filser et al., *Neuro-Oncology* 2025: nanopore methylation + copy-number classification of medulloblastoma.
   - Montpellier co-authors include **Valérie Rigau** (IGF + Department of Pathology and Onco-biology, Gui de Chauliac University Hospital) and **Gilles Palenzuela** (CHU Montpellier).

4. **There is existing Montpellier bioinformatics experience relevant to a future multimodal nanopore workflow.**
   - PMMG/MOBIDIC is represented in the PALB2 long-read publication, whose analysis used Guppy, Minimap2, IGV, in-house scripts and Sniffles.
   - MGX provides NGS bioinformatics support.
   - The IGF Pannequin/Bassaganyas team is developing computational methods for **multimodal nanopore ctDNA analysis** in colorectal cancer.
   - A 2025 University of Montpellier MSc Bioinformatics project benchmarked `ichorCNA`, `ACE` and `QDNAseq` for CNA analysis on simulated and real low-pass WGS data in that nanopore/ctDNA context.

### Not demonstrated by the public evidence found in this scan

- Routine clinical long-read sequencing for solid tumours across the CHU.
- A validated **intraoperative/rapid nanopore diagnostic pathway for brain tumours at Gui de Chauliac**.
- Proof that the nanopore sequencing runs in the multicentre medulloblastoma paper were physically performed in Montpellier. The study is centrally led by Institut Curie and uses the Curie-developed NanoCliD pipeline; Montpellier is clearly a participating clinical/pathology centre, but local sequencing execution cannot be inferred from authorship alone.

---

## 1. Direct CHU Montpellier long-read experience

### Perrin et al., 2022 — TTN

**Long-Reads Sequencing Strategy to Localize Variants in TTN Repeated Domains**  
*The Journal of Molecular Diagnostics* 24(7):719–726.  
DOI: `10.1016/j.jmoldx.2022.04.006`

CHU Montpellier affiliations include the molecular diagnostic laboratory, medical genetics and ChromoStem. The study implemented a third-generation long-read strategy to localise variants in highly repetitive TTN domains that were difficult to resolve by short reads.

**Interpretation:** operational long-read expertise was already present in the CHU molecular-genetics environment by 2022.

---

## 2. Direct oncology / oncogenetics use at CHU Montpellier

### Ban et al., 2024 — PALB2

**Characterizing PALB2 intragenic duplication breakpoints in a triple-negative breast cancer case using long-read sequencing**  
*Frontiers in Oncology* 14:1355715.  
DOI: `10.3389/fonc.2024.1355715`

### Montpellier affiliations

- Laboratoire de Biologie des Tumeurs Solides, CHU Montpellier
- Medical Genetics, Arnaud-de-Villeneuve Hospital
- ChromoStem, CHU Montpellier
- **Montpellier BioInformatics for Clinical Diagnosis (MOBIDIC), Molecular Medicine and Genomics Platform (PMMG), CHU Montpellier**
- IRCM / ICM

### Reported ONT workflow

- long-range PCR;
- ONT SQK-LSK114 library;
- Flongle FLO-FLG114;
- **MinION Mk1B**;
- 18 h sequencing;
- ~1700× targeted read depth;
- Guppy high-accuracy basecalling;
- Minimap2 alignment;
- IGV review;
- in-house scripts for read extraction;
- Sniffles structural-variant calling;
- RepeatMasker / ClustalW for breakpoint context.

The workflow resolved the exact PALB2 tandem-duplication breakpoint and contributed to pathogenic interpretation.

**Important limitation:** this was hereditary-cancer / germline DNA work with targeted amplification rather than native whole-genome sequencing of a fresh solid-tumour biopsy. It nevertheless proves concrete ONT wet-lab and computational experience within the CHU oncology/genetics ecosystem.

**Primary source:** https://pmc.ncbi.nlm.nih.gov/articles/PMC10938850/

---

## 3. CNS tumours — direct Montpellier scientific connection

### Filser et al., 2025 — medulloblastoma

**Nanopore sequencing as a cutting-edge technology for medulloblastoma classification**  
*Neuro-Oncology* 27(5):1313–1324.  
DOI: `10.1093/neuonc/noae279`

### Montpellier co-authors

- **Valérie Rigau** — Institute of Functional Genomics, Montpellier; Department of Pathology and Onco-biology, Gui de Chauliac University Hospital, Montpellier.
- **Gilles Palenzuela** — CHU Montpellier pediatric hematology-oncology.

### Study performance

- 44 **frozen medulloblastomas** benchmarked against EPIC methylation arrays;
- 116-medulloblastoma integrated-diagnosis cohort;
- methylation + genome-wide copy-number profiling;
- **42/44 (95.5%)** correctly subgrouped in the EPIC benchmark cohort;
- **106/116 (91.4%)** correctly subgrouped in the integrated-diagnosis cohort;
- Flongle subset: **17/18 (94.4%)** correctly classified;
- subtype classification: **28/30 (93.3%)**.

The study evaluated clinically relevant methylation and copy-number profiles and showed that sparse nanopore methylation data can reproduce medulloblastoma molecular grouping/subtyping with high concordance.

**Interpretation:** this is the strongest published evidence that the Montpellier neuropathology/neuro-oncology ecosystem is already connected to a national nanopore CNS-tumour classification effort.

**Critical caveat:** the paper is led by Institut Curie and uses the Curie-developed **NanoCliD** pipeline. Public information does not establish that the Montpellier samples were sequenced locally.

**Primary sources:**
- PubMed: https://pubmed.ncbi.nlm.nih.gov/39731757/
- Full text: https://pmc.ncbi.nlm.nih.gov/articles/PMC12187364/

---

## 4. Existing local long-read infrastructure

### Montpellier GenomiX (MGX)

MGX is located at the Institut de Génomique Fonctionnelle on the Arnaud-de-Villeneuve campus.

The current public platform page lists:

- Illumina NovaSeq / MiniSeq;
- **Oxford Nanopore Technologies MinION**;
- robotic library preparation and quantification;
- Fragment Analyzer, Qubit and PCR QC equipment;
- statistical analysis of NGS data.

MGX reports **11 staff** and, for 2023, **124 projects for 80 teams from 49 laboratories and one company**. The platform is ISO 9001 and NF X50-900 certified, IBiSA-labelled and part of the France Génomique national infrastructure.

The current MGX documentation explicitly lists:

- **Construction de banques Long Reads gDNA (Oxford Nanopore Technologies)**;
- **Construction de banques Long reads Direct RNA-seq (Oxford Nanopore Technologies)**;
- bioinformatics services including genome assembly and standard sequencing analyses.

**Official sources:**
- https://www.igf.cnrs.fr/plateformes/mgx/
- https://project.mgx.cnrs.fr/projects/documentation/documents

### Interpretation for feasibility

A Montpellier project would therefore not need to create all long-read wet-lab competence de novo. Existing infrastructure covers at least MinION sequencing, long-read library preparation, QC and bioinformatics support.

However, the public pages do **not** establish an existing clinical PromethION/GridION service or a validated intraoperative CNS workflow at PMMG/Gui de Chauliac.

---

## 5. Existing bioinformatics experience relevant to a CNS nanopore workflow

### 5.1 CHU Montpellier — MOBIDIC / PMMG

The PALB2 long-read publication explicitly affiliates Simon Cabello-Aguilar with **Montpellier BioInformatics for Clinical Diagnosis (MOBIDIC), Molecular Medicine and Genomics Platform (PMMG), CHU Montpellier**.

The reported analysis chain included:

- Guppy basecalling;
- Minimap2 alignment;
- IGV review;
- in-house scripts;
- Sniffles SV calling;
- RepeatMasker / ClustalW.

This is not yet an end-to-end native CNS-tumour workflow, but it is direct evidence that clinically oriented CHU bioinformatics has already handled ONT long reads and structural-variant analysis.

### 5.2 MGX bioinformatics support

MGX states that it provides statistical analysis for NGS applications and lists bioinformatics services. The platform therefore combines sequencing with internal downstream analysis rather than functioning only as a wet-lab core.

A historical University of Montpellier platform fiche also documented substantial dedicated compute/storage and GPU resources. Because hardware inventories change quickly, any future project should verify present-day compute specifications directly with MGX rather than rely on historical numbers.

### 5.3 IGF — active computational oncology with nanopore

The Julie Pannequin / Laia Bassaganyas group runs an official project titled:

**Surveillance de l’ADN tumoral circulant (ADNct) pour l’analyse des récidives du cancer colorectal**.

The project explicitly combines:

- nanopore sequencing;
- clinical and preclinical genomic data;
- multimodal ctDNA analysis;
- CNA / genomic alterations;
- methylation;
- fragmentation;
- computational-method development.

The group describes Laia Bassaganyas' expertise in NGS data analysis, development of bioinformatics tools for cancer genomics/transcriptomics, aneuploidy and structural genomic variants.

**Official sources:**
- https://www.igf.cnrs.fr/equipes/equipe-pannequin/
- https://www.igf.cnrs.fr/equipes/equipe-pannequin/projet-surveillance-de-ladn-tumoral-circulant-pour-lanalyse-des-recidives-du-cancer-colorectal/

### 5.4 2025 MSc Bioinformatics — low-pass CNA pipeline

A 2025 University of Montpellier MSc Bioinformatics project supervised by **Laia Bassaganyas** was titled:

**Séquençage long-read pour le développement d’un outil multimodal destiné au suivi du cancer colorectal à partir de biopsie liquide**.

The work focused on bioinformatic CNA analysis from simulated and real data and included:

- benchmarking `ichorCNA`;
- benchmarking `ACE`;
- benchmarking `QDNAseq`;
- implementation of a pipeline adapted to **low-pass whole-genome sequencing**.

This is directly relevant to the computational problem of extracting large-scale copy-number information from shallow genome-wide data.

**Source:** https://informatique-fds.edu.umontpellier.fr/files/2025/06/Programme.pdf

### 5.5 Bioinformatics Learning Lab (BILL)

The University of Montpellier Bioinformatics Learning Lab documents a MinION-based proof-of-concept dating back to 2017–2018 in which students generated molecular data and performed downstream bioinformatics analysis, contributing to a peer-reviewed publication.

**Source:** https://informatique-fds.edu.umontpellier.fr/etudiants/masters-transdisciplinaires/master-bioinformatique/bill-bioinformatics-learning-lab/

### Overall interpretation

Montpellier already has experience across several computational blocks that would be needed for a future CNS long-read feasibility workflow:

- ONT basecalling;
- long-read mapping;
- structural-variant calling;
- custom scripting;
- low-pass whole-genome CNA analysis;
- multimodal nanopore data analysis;
- NGS statistical/bioinformatics platform support.

What is **not** publicly documented is a validated local end-to-end pipeline integrating **rapid CNS methylation classification + CNV + optional SNV/SV** in a clinical or intraoperative setting.

---

## 6. Active oncology research in Montpellier using the same conceptual model

The Pannequin/Bassaganyas ctDNA project is particularly relevant conceptually because it aims to derive multiple signals from the same native DNA sample:

- genomic alterations / CNA;
- methylation;
- fragmentation;
- low tumour-fraction / MRD information.

This is close to the multimodal philosophy of current CNS nanopore approaches, even though the biological material and clinical question are different.

---

## 7. Other Montpellier ONT experience

### CNR Leishmanioses / parasitology

A CHU/UM CNR report describes MinION long-read WGS development/validation for *Leishmania*, independently demonstrating hands-on experience with high-molecular-weight DNA, MinION sequencing and genome assembly in the Montpellier hospital-university biology environment.

This is not oncology and should be treated only as supporting technical context.

### University training / outreach

The University of Montpellier has an official MinION video and educational activity around third-generation sequencing:

- **OSNI – MinION (version longue)**: https://video.umontpellier.fr/video/15585-osni-minion-version-longue/
- BILL page: https://informatique-fds.edu.umontpellier.fr/etudiants/masters-transdisciplinaires/master-bioinformatique/bill-bioinformatics-learning-lab/

Again, these are contextual indicators of local familiarity rather than proof of clinical deployment.

---

## 8. Evidence grading

| Question | Current public evidence |
|---|---|
| Is long-read sequencing used in Montpellier? | **Yes — strong** |
| At CHU Montpellier? | **Yes — strong** |
| In oncology? | **Yes — strong for oncogenetics/research**, not demonstrated as broad routine tumour WGS |
| For CNS tumours? | **Yes as multicentre research participation** — medulloblastoma 2025 |
| Is Valérie Rigau linked to published CNS nanopore work? | **Yes — directly, as co-author** |
| Local CNS nanopore sequencing physically performed at CHU? | **Not proven publicly** |
| Intraoperative CNS nanopore diagnosis at Gui de Chauliac? | **No public evidence found** |
| Local ONT-capable sequencing platform? | **Yes — MGX MinION** |
| Local long-read library preparation? | **Yes — MGX gDNA and direct RNA-seq ONT services** |
| Existing CHU bioinformatics experience with ONT/SV? | **Yes — PALB2 / MOBIDIC-PMMG** |
| Existing local low-pass CNA bioinformatics experience? | **Yes — IGF / MSc Bioinformatics project** |
| Active local multimodal oncology nanopore research? | **Yes — IGF colorectal ctDNA project** |

---

## 9. Key local journal references

1. Perrin A, et al. *J Mol Diagn.* 2022. DOI `10.1016/j.jmoldx.2022.04.006`.
2. Ban IO, et al. *Front Oncol.* 2024. DOI `10.3389/fonc.2024.1355715`.
3. **Filser M, et al. *Neuro-Oncology.* 2025. DOI `10.1093/neuonc/noae279` — includes Valérie Rigau and Gilles Palenzuela, CHU Montpellier.**

## 10. Bottom line

The public evidence supports a precise formulation:

> Montpellier does not appear to have a publicly documented routine intraoperative nanopore CNS-tumour diagnostic service, but it already has **relevant wet-lab infrastructure, long-read clinical/research experience, ONT structural-variant bioinformatics, low-pass CNA expertise, an active multimodal nanopore oncology project, and direct neuropathology/neuro-oncology participation in a published medulloblastoma nanopore classification study**.

That distinction should be preserved in any future scientific or funding document: **the site is not starting from zero, but the specific rapid integrated CNS workflow still appears to require local development and validation.**
