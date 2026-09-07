# Long-read sequencing in CNS tumour diagnostics — literature repository

Curated literature repository for recent (2018–2026) evidence on **long-read / Oxford Nanopore sequencing in brain and CNS tumour diagnostics**, with emphasis on fresh/frozen tissue, methylome classification, genome-wide CNV/SV analysis, targeted SNV detection, and rapid/intraoperative workflows.

## Scope

The core bibliography is restricted to **journal-published articles**. Preprints and conference-only abstracts are not included as core references when no full peer-reviewed version is available.

## Files

- `references.bib` — Zotero/BibTeX-ready curated bibliography.
- `references.md` — human-readable categorized bibliography.
- `clinical_impact_perioperative.md` — evidence specifically addressing intraoperative decision-making and potential clinical value.
- `montpellier_landscape_2026-09-07.md` — CHU Montpellier feasibility context, centered on PMMG.
- `montpellier_local_references.bib` — CHU-linked long-read references.

## Core scientific themes

1. **Molecular classification as part of modern CNS diagnosis** — WHO CNS5, EANO, cIMPACT-NOW, methylation-classifier clinical utility.
2. **Rapid methylation classification** — nanoDx, Sturgeon, MethyLYZR, MNP-Flex/crossNN.
3. **Multimodal nanopore profiling** — methylation + CNV, with extension to SNV/indel, SV/fusions and MGMT.
4. **Fresh/frozen and intraoperative feasibility** — Djirackor, Sturgeon, Rapid-CNS2, ROBIN and recent validation studies.
5. **Clinical decision impact** — whether obtaining tumour identity during surgery can change the balance between extent of resection and neurological risk.

## CHU Montpellier — feasibility context

The local feasibility argument is deliberately simple and **CHU-centered**.

### PMMG / R+3

The project is positioned within the **Plateau de Médecine Moléculaire et de Génomique (PMMG), R+3**, where molecular-genomics expertise and the clinically oriented bioinformatics team are already present.

### Existing long-read experience

CHU Montpellier teams already have published long-read experience:

- **Perrin et al., J Mol Diagn 2022** — long-read resolution of variants in repetitive `TTN` domains.
- **Ban et al., Frontiers in Oncology 2024** — ONT MinION Mk1B + Flongle used to resolve a `PALB2` intragenic duplication in an oncology/genetics setting.

The `PALB2` workflow included ONT sequencing and downstream analysis with **Guppy, Minimap2, IGV, in-house scripts and Sniffles**, with **MOBIDIC / PMMG, CHU Montpellier** explicitly represented among the affiliations. This supports both wet-lab and bioinformatics feasibility without claiming that a complete CNS workflow already exists locally.

### Direct CNS-tumour experience connected to CHU Montpellier

**Filser et al., Neuro-Oncology 2025 — “Nanopore sequencing as a cutting-edge technology for medulloblastoma classification”** is included in the bibliography. CHU Montpellier co-authors include **Valérie Rigau** and **Gilles Palenzuela**. The study demonstrates high-concordance nanopore methylation/CNV classification on frozen medulloblastomas and provides direct local scientific experience with the approach, while not proving that the sequencing runs themselves were performed at Montpellier.

### What remains to demonstrate

Public evidence does not show that CHU Montpellier already has a validated local workflow for **rapid CNS methylation classification + genome-wide CNV ± SNV/SV** in the intraoperative setting. That gap is the relevant feasibility question.

## Perioperative clinical-value angle

The strongest rationale is not simply “faster molecular diagnosis”. It is **molecular information delivered while the neurosurgical strategy is still modifiable**.

- **Djirackor et al. 2021**: in 20 intraoperative cases, the molecular result would have supported a change in surgical strategy in **12/20**.
- **Sturgeon / Nature 2023**: real-time use in 25 operations with <90 min sample-to-diagnosis, establishing the technical basis for molecular decision support during surgery.
- **Rapid-CNS2 / Nature Medicine 2025**: 18 real intraoperative cases; methylation + CNV provided clinically relevant additional information in **13/18 (72.2%)**, although results were deliberately not yet used to drive surgery in that validation study.
- **ROBIN / Neuro-Oncology 2025**: 50 prospective intraoperative cases, <2 h turnaround and 90% concordance with final integrated diagnosis; strong feasibility, but not a patient-outcome trial.
- **Eelkman Rooda et al. / Child's Nervous System 2026**: recent peer-reviewed review focused specifically on how intraoperative nanopore sequencing can individualize extent-of-resection decisions and on the need to measure neurological morbidity, second-look surgery and patient-reported outcomes prospectively.

The evidence therefore supports a careful formulation: **decision impact is already demonstrated; reduction in neurological morbidity or improved survival remains to be proven prospectively.**

See `clinical_impact_perioperative.md` for the detailed evidence hierarchy.
