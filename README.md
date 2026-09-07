# Long-read sequencing in CNS tumour diagnostics — literature repository

Curated literature repository for recent (2018–2026) evidence on **long-read / Oxford Nanopore sequencing in brain and CNS tumour diagnostics**, with emphasis on fresh/frozen tissue, methylome classification, genome-wide CNV/SV analysis, targeted SNV detection, and rapid/intraoperative workflows.

## Scope

The core bibliography is restricted to **journal-published articles**. Preprints and conference-only abstracts are not included as core references when no full peer-reviewed version is available.

## Files

- `references.bib` — Zotero/BibTeX-ready curated bibliography.
- `references.md` — human-readable categorized bibliography.
- `clinical_impact_perioperative.md` — detailed evidence on intraoperative decision-making, with a dedicated **adult diffuse-glioma / glioblastoma** section.
- `surgical_impact_references.bib` — focused BibTeX bibliography for perioperative impact, adult glioma surgery and biology-informed extent-of-resection literature.
- `montpellier_landscape_2026-09-07.md` — CHU Montpellier feasibility context, centered on PMMG.
- `montpellier_local_references.bib` — CHU-linked long-read references.

## Core scientific themes

1. **Molecular classification as part of modern CNS diagnosis** — WHO CNS5, EANO, cIMPACT-NOW, methylation-classifier clinical utility.
2. **Rapid methylation classification** — nanoDx, Sturgeon, MethyLYZR, MNP-Flex/crossNN.
3. **Multimodal nanopore profiling** — methylation + CNV, with extension to SNV/indel, SV/fusions and MGMT.
4. **Fresh/frozen and intraoperative feasibility** — Djirackor, Sturgeon, Rapid-CNS2, ROBIN and recent validation studies.
5. **Clinical decision impact** — whether obtaining tumour identity during surgery can change the balance between extent of resection and neurological risk.
6. **Adult precision neurosurgery** — whether adult glioma molecular state can inform how aggressively a tumour should be resected and whether rapid molecular data can correct intraoperative diagnostic uncertainty.

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

### Direct nanopore decision-impact evidence

- **Djirackor et al. 2021**: in 20 intraoperative cases, the molecular result would have supported a change in surgical strategy in **12/20**. The full cohort included 55 adults, although the decision-impact subset was not stratified by age.
- **Sturgeon / Nature 2023**: real-time use in 25 operations with <90 min sample-to-diagnosis, establishing the technical basis for molecular decision support during surgery.
- **Sie et al. / Neuro-Oncology 2026**: 94 consecutive paediatric patients in routine care; Sturgeon actually **changed surgical strategy in 14.3%** of informative cases, toward either more aggressive or more limited resection. This is currently the clearest peer-reviewed demonstration of real-time nanopore decision impact.

### Adult diffuse-glioma evidence

The adult literature now supplies a complementary chain of evidence:

- **Wu et al., BMC Medicine 2025**: prospective multicentre adult-type diffuse-glioma study showing that ~35-min molecular testing can correct important frozen-section interpretations; 40 lower-grade calls were redirected toward glioblastoma and 20 apparent gliosis cases were molecularly identified as diffuse glioma.
- **Drexler et al., Neuro-Oncology 2023**: methylation subclasses predicted differential association between extent of resection and survival in IDH-wildtype glioblastoma — benefit for RTK I/II but not demonstrable for MES.
- **Drexler, Lim & Hervey-Jumper, Neuro-Oncology 2025**: explicit framework for molecularly informed glioblastoma surgery and potential use of intraoperative nanopore methylation data.
- **iSCORED / Genome Medicine 2025**, **Rapid-CNS2 / Nature Medicine 2025** and **ROBIN / Neuro-Oncology 2025** demonstrate that adult-relevant methylation + genome-wide CNV information can already be generated within the operative window.
- **PIONEER Consortium / RANO resect, Lancet Oncology 2026** provides the contemporary adult framework for intraoperative decision-making and for measuring neurological, functional and quality-of-life outcomes.

### Current adult evidence gap

There is still no large **adult-only, peer-reviewed nanopore study** showing a clean prospective endpoint such as percentage of operations whose extent of resection was actually changed, reduction in second-look surgery, or reduction in neurological morbidity.

That is a scientifically important distinction: **adult clinical need, biological rationale and technical feasibility are already present; direct adult nanopore clinical-impact evidence remains incomplete.**

See `clinical_impact_perioperative.md` for the detailed evidence hierarchy and `surgical_impact_references.bib` for the focused bibliography.
