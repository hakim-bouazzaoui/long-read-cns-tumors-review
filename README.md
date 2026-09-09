# Long-read sequencing in CNS tumour diagnostics — literature repository

Curated literature and project repository for recent evidence on **long-read / Oxford Nanopore sequencing in brain and CNS tumour diagnostics**, with emphasis on fresh/frozen tissue, genome-wide methylation classification, CNV/SV analysis, targeted SNV detection, rapid/intraoperative workflows, clinical implementation and perioperative decision support.

## Scope

The core scientific bibliography prioritizes **journal-published articles**. Preprints and conference-only abstracts are not included as core evidence when a peer-reviewed version is available. Authoritative diagnostic classifications, clinical guidelines and reporting standards from **WHO/IARC, EANO, cIMPACT-NOW, ICCR, SIOP-Europe/ERN PaedCan and ANOCEF** are also retained because they are directly relevant to hospital implementation.

## Files

- `references.bib` — Zotero/BibTeX-ready curated bibliography, now including authoritative classifications/guidelines as well as peer-reviewed literature.
- `references.md` — human-readable categorized bibliography.
- `methylome_guidelines_and_clinical_implementation_rationale_2026-09-09.md` — detailed WHO/EANO/cIMPACT-NOW/ICCR/SIOPE/ANOCEF argument for genome-wide methylation profiling and implications for accelerated clinical implementation of the Montpellier nanopore workflow.
- `clinical_impact_perioperative.md` — detailed evidence on intraoperative decision-making, with a dedicated **adult diffuse-glioma / glioblastoma** section.
- `surgical_impact_references.bib` — focused BibTeX bibliography for perioperative impact, adult glioma surgery and biology-informed extent-of-resection literature.
- `montpellier_landscape_2026-09-07.md` — CHU Montpellier feasibility context, centered on PMMG.
- `montpellier_local_references.bib` — CHU-linked long-read references.
- `project_manuscript_v0.1.md` — initial AAP manuscript version; retained as a traceable baseline and **not considered the final project framing** after the September 2026 shift toward accelerated clinical implementation.
- `methodology_AAP_JC2026_2026-09-08.md` — initial validation-focused methodology; to be revised after Toulouse workflow feedback and regulatory/quality discussion.

## Current project positioning — updated 9 September 2026

The project should **not be treated as a large local validation study that must be completed before any clinical use is considered**.

The intended trajectory is now:

1. obtain an operational benchmark from a French centre already using rapid methylation/Nanopore workflows, with the **CHU/IUCT Toulouse** as a priority contact;
2. transfer and qualify the workflow locally, including platform, kit, flow cell, extraction, DNA input, multiplexing, classifier, thresholds, QC, reporting and cost;
3. perform a **limited local verification/qualification series** sized according to the actual quality and regulatory purpose rather than an arbitrary 100–200-patient validation cohort;
4. move rapidly to a prospective clinical evaluation integrated with neuropathology once predefined analytical and quality gates are met;
5. if the regulatory and quality framework permits clinical reporting, evaluate perioperative use with neurosurgery, including whether the molecular result is available during the decision window and whether it confirms or changes surgical strategy.

The exact transition from experimental output to a result usable in care must be defined with neuropathology, the molecular laboratory, quality/accreditation stakeholders and DRI/URCE. The EANO guideline explicitly notes that methylation classifiers are not themselves CE-IVD devices and that local diagnostic use requires the appropriate validation/accreditation framework.

## Core scientific themes

1. **Molecular classification as part of modern CNS diagnosis** — WHO CNS5, EANO, cIMPACT-NOW, ICCR, SIOPE/ERN PaedCan and French recommendations.
2. **Genome-wide methylation profiling as a clinical capability** — essential/desirable WHO criteria for multiple entities, diagnostic resolution of difficult cases, NOS/NEC reduction and standardized molecular reporting.
3. **Rapid methylation classification** — nanoDx, Sturgeon, MethyLYZR, MNP-Flex/crossNN.
4. **Multimodal nanopore profiling** — methylation + CNV, with extension to SNV/indel, SV/fusions and MGMT.
5. **Fresh/frozen and intraoperative feasibility** — Djirackor, Sturgeon, Rapid-CNS2, ROBIN and recent validation studies.
6. **Clinical decision impact** — whether obtaining tumour identity during surgery can change the balance between extent of resection and neurological risk.
7. **Adult precision neurosurgery** — whether adult glioma molecular state can inform how aggressively a tumour should be resected and whether rapid molecular data can correct intraoperative diagnostic uncertainty.
8. **Clinical implementation** — analytical qualification, ISO 15189/IVDR considerations, reporting, turnaround time, staff requirements, costs and inter-centre transfer of validated workflows.

## Why the methylome argument matters

WHO CNS5 already incorporates methylation classes into the diagnostic criteria of multiple CNS tumour types. The 2023 EANO molecular diagnostics guideline recommends that access to DNA methylation analysis, either on-site or by referral, be available at any institution involved in CNS tumour diagnostics. cIMPACT-NOW update 9 (2025) gives explicit recommendations for genome-wide methylation profiling, including prioritization of diagnostically difficult or discordant cases and tumours for which methylation classification is the only way to define the type. ICCR 2024 added methylome profiling as a core molecular reporting element aligned with WHO CNS5 essential diagnostic criteria. cIMPACT-NOW update 11 provides a concrete example in which a posterior fossa ependymoma cannot be definitively assigned as PFB without a concordant methylation profile and otherwise remains NOS.

The sixth edition of the WHO CNS classification is **in progress** as of September 2026. Its final wording must not be predicted, but the current direction of travel is clear: integrated molecular and epigenetic classification is becoming increasingly central to neuropathology.

See `methylome_guidelines_and_clinical_implementation_rationale_2026-09-09.md` for the evidence hierarchy, exact caveats and proposed project wording.

## CHU Montpellier — feasibility context

The local feasibility argument is deliberately CHU-centered.

### PMMG / R+3

The project is positioned within the **Plateau de Médecine Moléculaire et de Génomique (PMMG), R+3**, where molecular-genomics expertise and the clinically oriented bioinformatics team are already present.

### Existing long-read experience

CHU Montpellier teams already have published long-read experience:

- **Perrin et al., J Mol Diagn 2022** — long-read resolution of variants in repetitive `TTN` domains.
- **Ban et al., Frontiers in Oncology 2024** — ONT MinION Mk1B + Flongle used to resolve a `PALB2` intragenic duplication in an oncology/genetics setting.

The `PALB2` workflow included ONT sequencing and downstream analysis with **Guppy, Minimap2, IGV, in-house scripts and Sniffles**, with **MOBIDIC / PMMG, CHU Montpellier** explicitly represented among the affiliations. This supports both wet-lab and bioinformatics feasibility without claiming that a complete CNS workflow already exists locally.

### Direct CNS-tumour experience connected to CHU Montpellier

**Filser et al., Neuro-Oncology 2025 — “Nanopore sequencing as a cutting-edge technology for medulloblastoma classification”** is included in the bibliography. CHU Montpellier co-authors include **Valérie Rigau** and **Gilles Palenzuela**. The study demonstrates high-concordance nanopore methylation/CNV classification on frozen medulloblastomas and provides direct local scientific experience with the approach, while not proving that the sequencing runs themselves were performed at Montpellier.

### Toulouse benchmark

The same Filser study includes **Anne Isabelle Bertozzi** (CHU Toulouse) and **Emmanuelle Uro-Coste** (IUCT-Oncopole/Toulouse). Public teaching material from Emmanuelle Uro-Coste also explicitly discusses **Nanopore in an extemporaneous/rapid methylation context**. This makes Toulouse a relevant priority centre for operational feedback.

The public record does not establish the exact current routine workflow, platform, kit, cost or regulatory implementation. Those elements must be obtained directly before the Montpellier protocol and budget are frozen.

### What remains to demonstrate locally

The relevant local question is no longer simply whether nanopore methylation classification can work. Published evidence already supports that principle. The questions are now:

- can an existing workflow be transferred and qualified rapidly at Montpellier;
- what local verification is required before clinical reporting;
- what are the real turnaround time, failure modes and cost in the Montpellier environment;
- how should the result be integrated with neuropathology;
- and, once clinically qualified, can it provide useful molecular information while neurosurgical decisions remain modifiable?

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

That remains a scientifically useful gap: **adult clinical need, biological rationale and technical feasibility are already present; direct adult nanopore clinical-impact evidence remains incomplete.**

See `clinical_impact_perioperative.md` for the detailed evidence hierarchy and `surgical_impact_references.bib` for the focused bibliography.
