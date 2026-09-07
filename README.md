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
- `montpellier_landscape_2026-09-07.md` — evidence-graded scan focused on **CHU Montpellier** long-read experience, CNS-tumour links, hospital infrastructure and bioinformatics.
- `montpellier_local_references.bib` — CHU Montpellier long-read references.
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

## CHU Montpellier: existing experience and infrastructure

The local section is deliberately restricted to **evidence directly linked to CHU Montpellier**.

### Direct CHU long-read / oncology experience

- **Perrin et al., Journal of Molecular Diagnostics 2022** — CHU Montpellier molecular genetics teams used a long-read strategy to resolve variants in repetitive `TTN` domains.
- **Ban et al., Frontiers in Oncology 2024** — CHU Montpellier teams including Biologie des Tumeurs Solides, Medical Genetics, ChromoStem and **MOBIDIC / PMMG** used ONT **MinION Mk1B + Flongle** to resolve an intragenic `PALB2` duplication breakpoint.
- The reported `PALB2` analysis used **Guppy**, **Minimap2**, **IGV**, **in-house scripts**, **Sniffles**, RepeatMasker and ClustalW. This is direct evidence of existing CHU experience with ONT reads and structural-variant bioinformatics.

### Direct CNS-tumour connection

- **Filser et al., Neuro-Oncology 2025 — “Nanopore sequencing as a cutting-edge technology for medulloblastoma classification”** is included in the main bibliography.
- Montpellier co-authors include **Valérie Rigau** (Department of Pathology and Onco-biology, Gui de Chauliac University Hospital) and **Gilles Palenzuela** (CHU Montpellier).
- The study combined **sparse genome-wide methylation + copy-number profiling** on medulloblastomas, with 42/44 (95.5%) correctly subgrouped in the frozen EPIC benchmark cohort, 106/116 (91.4%) in the integrated-diagnosis cohort, 17/18 (94.4%) on Flongle, and 28/30 (93.3%) correctly subtyped.
- This demonstrates **CHU Montpellier participation in a peer-reviewed nanopore CNS-tumour classification program**, but does **not** prove that the sequencing runs themselves were performed locally.

### Existing hospital infrastructure

The **Site Unique de Biologie (SUB) Pr Arlette Serre** centralizes almost all CHU Montpellier laboratory biology. Its current organization includes:
- **R+2:** pathology / biopathology and cytogenetics;
- **R+3:** molecular genetics, including the **Plateau de Médecine Moléculaire et de Génomique (PMMG)**;
- **rez-de-jardin:** Centre de Ressources Biologiques / tissue resources;
- **R+5:** CRIBS research and innovation space.

This hospital organization brings pathology, molecular genetics/genomics, biological resources and translational research into a single CHU site. Separately, the `PALB2` publication proves actual CHU use of **MinION Mk1B + Flongle**, although public information does not establish whether ONT is currently deployed as a routine platform or the exact instrument inventory available today.

### Existing CHU bioinformatics experience

**MOBIDIC / PMMG (CHU Montpellier)** is explicitly represented in the published `PALB2` long-read workflow. The analysis included:
- ONT basecalling;
- long-read alignment;
- structural-variant calling;
- visual review;
- custom scripting;
- breakpoint characterization.

This is the most directly relevant published evidence for existing **CHU-based long-read bioinformatics competence**. It should not be overstated as a validated end-to-end CNS pipeline: no public evidence was found for a local clinical workflow integrating rapid CNS methylation classification + CNV + SNV/SV.

See `montpellier_landscape_2026-09-07.md` for the evidence grading and limitations.

## Notes

This is a literature curation repository, not yet a protocol or project proposal.  
Clinical implementation claims should remain tied to the exact validation setting of each publication.
