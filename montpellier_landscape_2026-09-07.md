# CHU Montpellier long-read / Oxford Nanopore landscape

**Date of scan:** 2026-09-07  
**Scope:** evidence directly linked to **CHU Montpellier**, with emphasis on oncology, neuropathology/CNS tumours, hospital infrastructure and bioinformatics. Academic-only University/IGF projects are deliberately excluded from this version.

## Executive conclusion

### Confirmed by public evidence

1. **Long-read sequencing has already been used by CHU Montpellier teams.**
   - Perrin et al., *The Journal of Molecular Diagnostics* 2022: long-read resolution of variants in repetitive `TTN` domains.
   - Ban et al., *Frontiers in Oncology* 2024: ONT long-read characterization of an intragenic `PALB2` duplication, with CHU Montpellier Biologie des Tumeurs Solides, Medical Genetics, ChromoStem and **MOBIDIC / PMMG** affiliations.

2. **There is direct published CHU experience with ONT wet-lab and long-read bioinformatics in an oncology/genetics setting.**
   - The `PALB2` study used **MinION Mk1B + Flongle**, Guppy, Minimap2, IGV, in-house scripts and Sniffles.

3. **CHU Montpellier has participated in a peer-reviewed nanopore CNS-tumour classification study.**
   - Filser et al., *Neuro-Oncology* 2025: **“Nanopore sequencing as a cutting-edge technology for medulloblastoma classification.”**
   - Montpellier co-authors include **Valérie Rigau**, Department of Pathology and Onco-biology, Gui de Chauliac University Hospital, and **Gilles Palenzuela**, CHU Montpellier pediatric hematology-oncology.

4. **The current CHU biology organization is compatible with translational molecular-genomics development.**
   - The **Site Unique de Biologie (SUB) Pr Arlette Serre** centralizes almost all CHU laboratory biology.
   - R+2: pathology / biopathology and cytogenetics.
   - R+3: molecular genetics, including the **Plateau de Médecine Moléculaire et de Génomique (PMMG)**.
   - Rez-de-jardin: Centre de Ressources Biologiques / tissue resources.
   - R+5: CRIBS research and innovation.

### Not demonstrated by the public evidence found in this scan

- Routine clinical long-read sequencing for solid tumours across the CHU.
- A validated **intraoperative/rapid nanopore diagnostic pathway for brain tumours at Gui de Chauliac**.
- Proof that the nanopore sequencing runs in the multicentre medulloblastoma study were physically performed at CHU Montpellier.
- A publicly documented current ONT instrument inventory at PMMG or elsewhere in the CHU.

---

## 1. Direct CHU Montpellier long-read experience

### Perrin et al., 2022 — TTN

**Long-Reads Sequencing Strategy to Localize Variants in TTN Repeated Domains**  
*The Journal of Molecular Diagnostics* 24(7):719–726.  
DOI: `10.1016/j.jmoldx.2022.04.006`

CHU Montpellier affiliations include the molecular diagnostic laboratory, medical genetics and ChromoStem. The study implemented a third-generation long-read strategy to localise variants in highly repetitive `TTN` domains that were difficult to resolve by short reads.

**Interpretation:** operational long-read expertise was already present in the CHU molecular-genetics environment by 2022.

---

## 2. Direct oncology / oncogenetics use at CHU Montpellier

### Ban et al., 2024 — PALB2

**Characterizing PALB2 intragenic duplication breakpoints in a triple-negative breast cancer case using long-read sequencing**  
*Frontiers in Oncology* 14:1355715.  
DOI: `10.3389/fonc.2024.1355715`

### CHU Montpellier affiliations relevant to the workflow

- Laboratoire de Biologie des Tumeurs Solides, CHU Montpellier
- Medical Genetics, Arnaud-de-Villeneuve Hospital
- ChromoStem, CHU Montpellier
- **Montpellier BioInformatics for Clinical Diagnosis (MOBIDIC), Molecular Medicine and Genomics Platform (PMMG), CHU Montpellier**

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

The workflow resolved the exact `PALB2` tandem-duplication breakpoint and contributed to pathogenic interpretation.

**Interpretation:** this is direct evidence that CHU teams have already handled both the wet-lab and computational components of ONT long-read analysis in an oncology-related setting.

**Important limitation:** this was hereditary-cancer / germline DNA work with targeted amplification rather than native whole-genome sequencing of a fresh solid-tumour biopsy.

**Primary source:** https://pmc.ncbi.nlm.nih.gov/articles/PMC10938850/

---

## 3. CNS tumours — direct CHU Montpellier scientific connection

### Filser et al., 2025 — medulloblastoma

**Nanopore sequencing as a cutting-edge technology for medulloblastoma classification**  
*Neuro-Oncology* 27(5):1313–1324.  
DOI: `10.1093/neuonc/noae279`

### CHU Montpellier co-authors

- **Valérie Rigau** — Department of Pathology and Onco-biology, Gui de Chauliac University Hospital, Montpellier.
- **Gilles Palenzuela** — CHU Montpellier pediatric hematology-oncology.

### Study performance

- 44 **frozen medulloblastomas** benchmarked against EPIC methylation arrays;
- 116-medulloblastoma integrated-diagnosis cohort;
- methylation + genome-wide copy-number profiling;
- **42/44 (95.5%)** correctly subgrouped in the EPIC benchmark cohort;
- **106/116 (91.4%)** correctly subgrouped in the integrated-diagnosis cohort;
- Flongle subset: **17/18 (94.4%)** correctly classified;
- subtype classification: **28/30 (93.3%)**.

The study evaluated sparse nanopore methylation data together with genome-wide copy-number profiles and showed high concordance with reference medulloblastoma classification.

**Interpretation:** this is the strongest published evidence connecting CHU Montpellier neuropathology / pediatric neuro-oncology to a nanopore CNS-tumour classification programme.

**Critical caveat:** the paper is led by Institut Curie and uses the Curie-developed **NanoCliD** pipeline. Public information does not establish that the Montpellier samples were sequenced locally.

**Primary sources:**
- PubMed: https://pubmed.ncbi.nlm.nih.gov/39731757/
- Full text: https://pmc.ncbi.nlm.nih.gov/articles/PMC12187364/

---

## 4. Existing CHU hospital infrastructure relevant to feasibility

### Site Unique de Biologie (SUB) Pr Arlette Serre

The current CHU organization centralizes almost all laboratory biology in one building. According to the CHU:

- **R+2:** anatomo-pathology / biopathology and cytogenetics;
- **R+3:** molecular genetics, including the **Plateau de Médecine Moléculaire et de Génomique (PMMG)**;
- **rez-de-jardin:** Centre de Ressources Biologiques and tissue resources;
- **R+5:** CRIBS, research and innovation.

The CHU explicitly frames the SUB around **rapid turnaround, hyperspecialized analyses, research and innovation**.

This organization is relevant because a future CNS long-read workflow would need tight integration between:

1. tissue/pathology assessment;
2. molecular-genomics wet lab;
3. bioinformatics;
4. access to frozen/biobanked material;
5. translational research infrastructure.

All of these functions are represented within the CHU biology organization.

### Direct evidence of ONT access/use

The `PALB2` publication documents actual use of **MinION Mk1B + Flongle** by a CHU-affiliated workflow. This supports local practical experience with ONT technology.

However, the publication does **not** establish:
- ownership of a specific instrument by PMMG;
- current instrument inventory;
- routine clinical availability;
- a validated CNS-specific workflow.

### Official CHU sources

- Site Unique de Biologie: https://www.chu-montpellier.fr/fr/a-propos-du-chu/decouvrir/etablissements/site-unique-de-biologie
- CRIBS: https://www.chu-montpellier.fr/fr/cribs
- CHU article describing the SUB organization and PMMG at R+3: https://www.chu-montpellier.fr/fr/information-transversale/actualites/le-pole-biologie-pathologie-se-regenere-8688

---

## 5. Existing CHU bioinformatics experience relevant to a CNS nanopore workflow

### MOBIDIC / PMMG

The `PALB2` long-read publication explicitly affiliates **Montpellier BioInformatics for Clinical Diagnosis (MOBIDIC), Molecular Medicine and Genomics Platform (PMMG), CHU Montpellier**.

The reported analysis chain included:

- ONT basecalling with Guppy;
- long-read alignment with Minimap2;
- IGV review;
- in-house scripts;
- structural-variant calling with Sniffles;
- breakpoint-context analysis with RepeatMasker / ClustalW.

### What this demonstrates

There is direct published evidence that CHU bioinformatics has already handled:

- ONT reads;
- long-read mapping;
- structural-variant detection;
- custom scripting;
- breakpoint interpretation.

This is directly relevant to the computational component of a future CNS long-read workflow.

### What it does not demonstrate

It does **not** show that CHU Montpellier already has a validated local pipeline for:

- sparse methylation CNS classification;
- rapid genome-wide CNV calling from low-pass ONT data;
- integrated CNS methylation + CNV + SNV/SV reporting;
- intraoperative real-time analysis.

Those capabilities would need to be demonstrated rather than assumed.

---

## 6. Evidence grading — CHU Montpellier only

| Question | Current public evidence |
|---|---|
| Long-read sequencing already used by CHU teams? | **Yes — strong** |
| ONT/MinION already used in a CHU oncology-related workflow? | **Yes — PALB2 2024** |
| Existing CHU bioinformatics experience with ONT/SV? | **Yes — MOBIDIC/PMMG + PALB2 workflow** |
| CHU participation in a nanopore CNS-tumour study? | **Yes — medulloblastoma 2025** |
| Valérie Rigau linked to published CNS nanopore work? | **Yes — directly as co-author** |
| Frozen CNS tissue represented in that study? | **Yes** |
| Local CNS nanopore sequencing physically performed at CHU? | **Not proven publicly** |
| Intraoperative CNS nanopore diagnosis at Gui de Chauliac? | **No public evidence found** |
| Hospital infrastructure linking pathology, molecular genetics, CRB and research? | **Yes — SUB / PMMG / CRIBS** |
| Current CHU ONT instrument inventory publicly documented? | **No** |
| Validated local CNS methylation + CNV bioinformatics pipeline? | **No public evidence found** |

---

## 7. Key CHU-linked journal references

1. Perrin A, et al. *J Mol Diagn.* 2022. DOI `10.1016/j.jmoldx.2022.04.006`.
2. Ban IO, et al. *Front Oncol.* 2024. DOI `10.3389/fonc.2024.1355715`.
3. **Filser M, et al. *Neuro-Oncology.* 2025. DOI `10.1093/neuonc/noae279` — includes Valérie Rigau and Gilles Palenzuela, CHU Montpellier.**

## 8. Bottom line

The CHU-specific evidence supports a deliberately conservative formulation:

> **CHU Montpellier already has published long-read experience, documented ONT/MinION use in an oncology-related workflow, CHU-based long-read/SV bioinformatics through MOBIDIC-PMMG, a centralized molecular-genomics/pathology infrastructure at the Site Unique de Biologie, and direct participation of its neuropathology/neuro-oncology teams in a published nanopore medulloblastoma classification study. What is not publicly documented is a local validated rapid or intraoperative nanopore CNS-tumour diagnostic workflow.**
