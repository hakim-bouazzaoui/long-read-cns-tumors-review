# Long-read sequencing in CNS tumour diagnostics — literature repository

Curated literature repository for recent (2018–2026) evidence on **long-read / Oxford Nanopore sequencing in brain and CNS tumour diagnostics**, with emphasis on fresh/frozen tissue, methylome classification, genome-wide CNV/SV analysis, targeted SNV detection, and intraoperative/rapid workflows.

## Scope

The bibliography is intentionally restricted to **journal-published articles**. It excludes:
- medRxiv/bioRxiv preprints when a peer-reviewed journal version exists;
- conference-only abstracts/supplements;
- non-journal vendor pages;
- the landmark 2017 Euskirchen et al. same-day nanopore paper because it falls outside the requested 2018–2026 window.

## Files

- `references.bib` — Zotero/BibTeX-ready curated bibliography.
- `references.md` — human-readable categorized list with DOI and relevance.
- `montpellier_landscape_2026-09-07.md` — evidence-graded scan of existing Montpellier/CHU infrastructure, publications and bioinformatics experience.
- `montpellier_local_references.bib` — local Montpellier long-read references.
- `.gitignore` — minimal repository hygiene.

## Core themes represented

1. **Diagnostic framework and clinical need**
   - WHO CNS5 integrated diagnosis.
   - EANO molecular diagnostic guideline.
   - cIMPACT-NOW update 9 on genome-wide DNA methylation profiling.
   - Large clinical methylation-classifier utility cohorts.

2. **Rapid / intraoperative nanopore methylation classification**
   - Djirackor et al. 2021.
   - Sturgeon / Vermeulen et al. 2023.
   - MethyLYZR / Brändl et al. 2025.
   - ROBIN / Deacon et al. 2025.

3. **Multimodal nanopore profiling**
   - Rapid-CNS2 proof-of-concept (2022) and multicenter validation (2025).
   - CNV, SNV/indel, MGMT, methylation class and structural alteration assessment.

4. **Genome-wide CNV / low-pass approaches**
   - iSCORED / Emiliani et al. 2025.
   - Rapid CNV reconstruction combined with methylation classification.

5. **Cross-platform methylation classifiers**
   - nanoDx.
   - Sturgeon.
   - MethyLYZR.
   - MNP-Flex.
   - crossNN.

6. **Fresh / frozen real-world feasibility**
   - Fresh intraoperative biopsies.
   - Cryopreserved/fresh-frozen cohorts.
   - 2026 multi-institutional NOS/NEC validation including frozen tissues.

## Montpellier existing capabilities and experience

The local landscape is unusually favorable for a feasibility study because **long-read sequencing and nanopore bioinformatics are already present in the Montpellier ecosystem**, although no public evidence was found for a routine intraoperative nanopore CNS-tumour diagnostic service.

### Direct CHU / oncology experience

- **PALB2, Frontiers in Oncology 2024** — CHU Montpellier teams (Biologie des Tumeurs Solides, Medical Genetics, ChromoStem, **MOBIDIC / PMMG**, IRCM/ICM) used ONT MinION Mk1B + Flongle to resolve an intragenic `PALB2` tandem-duplication breakpoint.
- The reported analysis used **Guppy**, **Minimap2**, **IGV**, **in-house scripts**, **Sniffles**, RepeatMasker and ClustalW. This is concrete evidence of existing local long-read bioinformatics know-how in a clinically oriented oncology/genetics setting.

### Direct CNS-tumour connection

- **Filser et al., Neuro-Oncology 2025 — “Nanopore sequencing as a cutting-edge technology for medulloblastoma classification”** is included in the main bibliography.
- Montpellier co-authors include **Valérie Rigau** (IGF + Department of Pathology and Onco-biology, Gui de Chauliac University Hospital) and **Gilles Palenzuela** (CHU Montpellier).
- The study combined **sparse genome-wide methylation + copy-number profiling** on medulloblastomas, with 42/44 (95.5%) correctly subgrouped in the frozen EPIC benchmark cohort, 106/116 (91.4%) in the integrated-diagnosis cohort, 17/18 (94.4%) on Flongle, and 28/30 (93.3%) correctly subtyped.
- This demonstrates **Montpellier participation in a peer-reviewed nanopore CNS-tumour classification program**, but does **not** prove that the sequencing runs themselves were performed locally.

### Existing sequencing infrastructure

**Montpellier GenomiX (MGX, IGF / Arnaud-de-Villeneuve campus)** publicly lists:
- Oxford Nanopore Technologies **MinION**;
- long-read gDNA library construction;
- ONT direct RNA-seq library construction;
- NGS statistical / bioinformatics support;
- automated library-preparation and QC equipment.

MGX reports 11 staff and 124 projects for 80 teams from 49 laboratories in 2023, is ISO 9001 and NF X50-900 certified, IBiSA-labelled, and part of France Génomique.

### Existing bioinformatics experience relevant to a multimodal nanopore workflow

- **MOBIDIC / PMMG (CHU Montpellier)** is explicitly represented in the PALB2 long-read publication and contributed to a workflow involving alignment, structural-variant calling and custom scripts.
- **MGX** provides bioinformatics support for NGS and publicly lists genome-assembly and other sequencing-analysis services.
- At the **IGF**, the Pannequin/Bassaganyas team is developing a nanopore-based multimodal colorectal-cancer ctDNA project combining genomic alterations/CNA, methylation and fragmentation signals with computational method development.
- A **2025 University of Montpellier MSc Bioinformatics project** supervised by Laia Bassaganyas benchmarked `ichorCNA`, `ACE` and `QDNAseq` and implemented a pipeline for CNA detection from simulated and real **low-pass whole-genome sequencing** data.
- The University of Montpellier **Bioinformatics Learning Lab (BILL)** has documented MinION data-generation and bioinformatics-analysis projects since 2017–2018.

See `montpellier_landscape_2026-09-07.md` for the evidence-graded local scan and its limitations.

## Notes

This is a literature curation repository, not yet a protocol or project proposal.  
Clinical implementation claims should remain tied to the exact validation setting of each publication.
