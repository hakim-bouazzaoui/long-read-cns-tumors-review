# Perioperative clinical impact of rapid molecular / nanopore CNS tumour classification

**Question:** is the value proposition limited to faster diagnosis, or is there evidence that intraoperative molecular information can change neurosurgical management?

## Executive conclusion

The literature has moved beyond analytical feasibility. The strongest current evidence supports a model of **biology-informed intraoperative decision support**: molecular information can be generated while surgery is still ongoing and can influence the balance between oncological benefit and neurological risk.

The evidence is not uniform across age groups:

- **real-world change in surgical strategy:** now directly demonstrated with nanopore in paediatric CNS tumours (Sie et al., *Neuro-Oncology*, 2026);
- **mixed adult/paediatric decision-impact evidence:** demonstrated earlier by Djirackor et al. 2021, but the decision-impact subset was not stratified by age;
- **adult diffuse glioma:** strong and rapidly growing evidence that molecular information obtained intraoperatively changes diagnostic interpretation and is biologically relevant to extent-of-resection decisions, but there is still no large adult-only peer-reviewed nanopore study with a clean endpoint such as percentage of operations whose extent of resection was actually changed;
- **reduction in neurological morbidity, quality-of-life benefit or survival benefit caused by nanopore-guided surgery:** not yet proven in a controlled prospective trial.

For an adult-focused project, this remaining gap is important: the field has established the clinical need, biological rationale and technical feasibility, but still lacks definitive adult prospective impact data.

---

# Part I — Direct evidence that rapid molecular diagnosis can influence surgery

## 1. Djirackor et al., Neuro-Oncology Advances 2021

**Intraoperative DNA methylation classification of brain tumors impacts neurosurgical strategy**  
DOI: `10.1093/noajnl/vdab149`

- 105 patients overall, including **55 adults and 50 paediatric patients**.
- Adult cases included glioblastomas, oligodendrogliomas and astrocytomas.
- Nanopore methylation classification concordant with final diagnosis in **93/105 (89%)**.
- Correct diagnosis in **6/6** cases where frozen section was inconclusive.
- Result returned to the operating room at a median of **97 min**.
- In the **20 intraoperative cases**, precise molecular classification **would have supported modification of the surgical strategy in 12/20 (60%)**.

### Why it matters

The paper illustrates both directions of benefit:

1. **Avoiding under-resection / an unnecessary second operation** when frozen section is uncertain or misleading and the tumour is actually resectable.
2. **Avoiding unnecessary additional high-risk resection** when molecular subtype indicates limited expected oncological gain from pursuing a small residual lesion.

### Limitation for an adult-only argument

The overall cohort was half adult, but the 12/20 decision-impact cases were not reported separately by age. The study therefore supports the general neurosurgical concept but does not provide an adult-specific percentage of strategy changes.

---

## 2. Vermeulen et al., Nature 2023 — Sturgeon

**Ultra-fast deep-learned CNS tumour classification during surgery**  
DOI: `10.1038/s41586-023-06615-2`

- 25 real surgeries.
- Total diagnostic turnaround **<90 min**.
- 18/25 correct diagnoses; 7 abstentions rather than forced calls.

This paper established that sparse nanopore methylation classification can be delivered **within the operative decision window**. It strongly supports feasibility but did not quantify a controlled reduction in reoperations, morbidity or altered extent of resection.

---

## 3. Sie et al., Neuro-Oncology 2026 — real-world strategy change

**How 'Sturgeon' guides the surgeon in pediatric neuro-oncology**  
DOI: `10.1093/neuonc/noag187`  
PMID: `42576322`

This is no longer a preprint: it was published as a peer-reviewed *Neuro-Oncology* clinical investigation on **10 August 2026**.

Since May 2023, frozen-section analysis plus intraoperative Sturgeon nanopore classification had been implemented as standard of care at the Princess Máxima Center.

- **94 consecutive paediatric patients**.
- Correct Sturgeon diagnosis: **82/94 (87.2%)** in <90 min.
- No confident diagnosis: 11.7%.
- Incorrect diagnosis: 1.1%.
- When informative, Sturgeon **supported the intended surgical strategy in 85.7%**.
- It **changed the actual surgical strategy in 14.3%**, toward either more aggressive or more limited resection.
- The authors report association with a low complication rate and fewer second-look surgeries.

### Interpretation

This is currently the strongest peer-reviewed demonstration that intraoperative nanopore molecular diagnosis can **actually change neurosurgical management**, rather than merely providing information that could theoretically do so.

### Relevance to an adult project

The biological and workflow principle is highly relevant, but the population is paediatric. It therefore provides proof-of-concept for **clinical impact**, not direct adult validation.

---

# Part II — Adult diffuse glioma: evidence that molecular information matters during surgery

## 4. Wu et al., BMC Medicine 2025 — adult-only prospective molecular diagnosis

**Rapid diagnosis of adult-type diffuse glioma using a layered scheme**  
DOI: `10.1186/s12916-025-04124-9`  
PMID: `40457320`

This is one of the most important recent adult papers for the clinical rationale, although the rapid assay is **PCR-based rather than nanopore**.

### Cohorts

- Retrospective derivation cohort: **746 adults**, age 18–80 years, supratentorial diffuse glioma WHO grades 2–4.
- Prospective multicentre cohort: **296 patients across four centres**.
- Rapid intraoperative detection of `IDH1/2` and `TERTp` within approximately **35 min**.
- **223 gliomas + 2 non-gliomas (76.5%)** could be accurately classified intraoperatively using the first molecular layer.

### Direct correction of frozen-section interpretation

Two findings are particularly relevant for surgery:

- **40 patients** initially interpreted as lower-grade glioma on frozen section had `TERTp`-mutant, IDH-wildtype tumours supporting a glioblastoma diagnosis, later confirmed postoperatively.
- **20 patients** initially interpreted as gliosis on frozen section were shown intraoperatively to harbour `IDH` or `TERTp` alterations and were correctly reclassified as diffuse gliomas and subtyped.

The authors explicitly state that this approach **significantly influences surgical strategies and decision-making**.

### Why it matters for a nanopore project

This paper proves, in a large adult prospective population, that **molecular information available during surgery materially changes the interpretation of lesions that frozen section can misclassify**.

It also exposes the limitation of a narrow rapid PCR strategy: the second diagnostic layer still needs information such as:

- `CDKN2A/B` homozygous deletion;
- `EGFR` amplification;
- `+7/-10`;
- `1p/19q` codeletion;
- H3 alterations.

The authors specifically note the difficulty of rapid intraoperative detection of `CDKN2A/B` homozygous deletion. This is a strong rationale for evaluating a **genome-wide nanopore approach able to combine methylation and CNV information** rather than only a few hotspot mutations.

---

## 5. Drexler et al., Neuro-Oncology 2023 — tumour biology may modify the benefit of maximal resection

**DNA methylation subclasses predict the benefit from gross total tumor resection in IDH-wildtype glioblastoma patients**  
DOI: `10.1093/neuonc/noac177`  
PMID: `35868257`

This multicentre study is central to the adult surgical rationale.

- 430 newly diagnosed IDH-wildtype glioblastomas underwent global DNA methylation profiling.
- 345 fulfilled the main analysis criteria.
- In **RTK I** and **RTK II** methylation subclasses, gross-total / near-gross-total resection was associated with longer OS and PFS than partial resection.
- In the **mesenchymal (MES)** subclass, the study found **no significant survival benefit from maximized extent of resection**.
- At recurrence, re-resection was associated with benefit in RTK I/II but not MES.

### Why it matters

This directly challenges the simplistic idea that every molecularly defined glioblastoma derives the same benefit from pursuing maximal resection at all costs.

The clinically attractive concept is therefore not **“nanopore lets us resect more”**, but:

> **rapid molecular classification may help match surgical aggressiveness to the tumour's expected biological benefit from resection, particularly when further resection carries functional risk.**

This is retrospective/non-randomized evidence and must not be presented as a validated treatment-selection rule. But it provides unusually strong biological rationale for obtaining methylation information before the operation is over.

---

## 6. Drexler, Lim & Hervey-Jumper, Neuro-Oncology 2025 — adult glioblastoma precision surgery framework

**Molecular-based decision-making in glioblastoma surgery: When to aim for supramaximal resection**  
DOI: `10.1093/neuonc/noaf062`  
PMID: `40037513`

This 2025 review explicitly asks whether glioblastoma biology should determine when to pursue supramaximal resection.

It highlights:

- emerging evidence that benefit from maximal resection may differ across molecular / methylation subclasses;
- the potential value of integrating molecular states into surgical decision-making;
- intraoperative nanopore methylation classification as an emerging technology capable of providing substantially richer molecular information than morphology alone;
- the need for prospective studies demonstrating that molecularly guided surgery improves outcomes.

The review specifically notes the reported difference in resection benefit between **RTK I / RTK II and MES methylation subclasses** and identifies intraoperative methylation-aware nanopore sequencing as a plausible route toward biology-informed surgical decisions.

---

# Part III — Adult-relevant nanopore workflows already operate within the surgical window

## 7. Emiliani et al., Genome Medicine 2025 — iSCORED

**Nanopore-based random genomic sampling for intraoperative molecular diagnosis**  
DOI: `10.1186/s13073-025-01427-7`

The prospective intraoperative cohort comprised **15 diagnostically challenging primary CNS tumours**:

- 8 high-grade gliomas;
- 4 low-grade gliomas;
- 3 spindle-cell neoplasms.

The entire workflow from specimen arrival to integrated graphs was completed in approximately **105 min**.

Outputs included:

- genome-wide CNV;
- focal oncogene amplification;
- sparse methylation classification.

Among the high-grade gliomas, Sturgeon methylation profiling correctly classified **7/8 as glioblastoma**. CNV profiles captured characteristic glioblastoma alterations including `+7/-10`, and all tested oncogene amplifications were detected (**10/10**, including `EGFR`, `PDGFRA`, `CDK4`, `MDM2/MDM4`, `KIT`). Lower-grade glioma classification included detection of `1p/19q` codeletion in oligodendroglioma.

### Interpretation

This is highly relevant to adult glioma practice because it demonstrates that the **methylation + genome-wide CNV information needed for integrated adult glioma diagnosis can be generated during the operation**.

The cohort is glioma-heavy but should not be described as a formal adult-only impact study. It did not quantify actual change in extent of resection.

---

## 8. Patel et al., Nature Medicine 2025 — Rapid-CNS2

**Prospective, multicenter validation of a platform for rapid molecular profiling of central nervous system tumors**  
DOI: `10.1038/s41591-025-03562-5`

- 301 samples overall.
- 18 actual real-time intraoperative workflows.
- Methylation + CNV information available within a 30-min sequencing window; sample-to-result intraoperative workflow around 90 min.
- In **13/18 (72.2%)** intraoperative cases, methylation + CNV provided clinically relevant information beyond morphology.

Adult-relevant examples included:

- distinguishing **IDH-mutant astrocytoma from IDH-wildtype glioblastoma**;
- clinically relevant CNV profiles;
- meningioma molecular risk information.

### Limitation

The molecular results were **not yet used to alter surgical management** in this validation study.

---

## 9. Deacon et al., Neuro-Oncology 2025 — ROBIN

**ROBIN: A unified nanopore-based assay integrating intraoperative methylome classification and next-day comprehensive profiling for ultra-rapid tumor diagnosis**  
DOI: `10.1093/neuonc/noaf103`

- 50 prospective intraoperative cases.
- Diagnostic turnaround <2 h.
- 90% concordance after the full run.
- Adult-relevant entities included glioblastoma, astrocytoma, oligodendroglioma and meningioma.
- Continued sequencing could provide `+7/-10`, `1p/19q`, `CDKN2A/B` co-deletion, `IDH1/2`, `TERT`, `TP53`, MGMT and structural alterations/fusions.

### Interpretation

ROBIN strongly supports technical feasibility of a **single adult-compatible multimodal assay**, but was not designed to quantify changes in surgical strategy or neurological outcome.

---

# Part IV — Adult surgical standards make the clinical question timely

## 10. PIONEER Consortium / RANO resect, Lancet Oncology 2026 — Part 1

**A comprehensive framework for glioma surgery ... part 1: intraoperative recommendations for mapping, monitoring, and decision making**  
DOI: `10.1016/S1470-2045(25)00531-5`  
PMID: `41449153`

This 2026 policy review is specifically about **adult patients with newly diagnosed or recurrent diffuse glioma**.

It states that:

- more extensive resection is associated with longer PFS and OS;
- intraoperative mapping / monitoring are used to increase resection while preserving function;
- intraoperative decision-making remains heterogeneous;
- **emerging intraoperative diagnostics may affect surgical strategy**;
- the field is moving toward personalized surgical care rather than a single uniform resection rule.

### Relevance

This provides a high-level adult neuro-oncology framework in which a rapid molecular assay is not merely a laboratory innovation: it is an additional **intraoperative decision variable** alongside mapping, monitoring and anatomical constraints.

---

## 11. PIONEER Consortium / RANO resect, Lancet Oncology 2026 — Part 2

**A comprehensive framework for glioma surgery ... part 2: perioperative recommendations for neurological, language, functional, and quality-of-life assessment**  
DOI: `10.1016/S1470-2045(25)00532-7`  
PMID: `41449155`

Part 2 addresses how perioperative benefit and harm should actually be measured. It emphasizes standardized evaluation of:

- neurological deficits;
- language function;
- functional status;
- quality of life.

### Relevance for future clinical endpoints

If an adult nanopore feasibility study later progresses to an impact study, the endpoints should not be limited to sequencing accuracy. Relevant endpoints include:

- change in intended extent of resection;
- achieved extent of resection;
- second-look surgery;
- new neurological deficit;
- language/cognitive change where relevant;
- functional outcome;
- patient-reported quality of life.

---

# Part V — Evidence map: paediatric proof of impact vs adult opportunity

| Clinical question | Best current evidence | Population | What is proven? |
|---|---|---|---|
| Can nanopore classification arrive during surgery? | Sturgeon 2023; Rapid-CNS2 2025; ROBIN 2025; iSCORED 2025 | Mixed / adult-relevant | **Yes** |
| Can rapid molecular testing correct frozen-section interpretation in adult glioma? | Wu et al., BMC Medicine 2025 | **Adult-only** | **Yes** |
| Can tumour molecular biology alter expected benefit from maximal resection? | Drexler et al., Neuro-Oncology 2023 | **Adult GBM** | **Association demonstrated** |
| Is biology-informed GBM surgery an active contemporary concept? | Drexler et al., Neuro-Oncology 2025 | **Adult GBM** | **Yes, strong rationale** |
| Does nanopore actually change surgical strategy in real time? | Sie et al., Neuro-Oncology 2026 | **Paediatric** | **Yes: 14.3% changed** |
| Adult-only nanopore cohort with actual quantified strategy change? | — | Adult | **Major current evidence gap** |
| Reduction in adult neurological morbidity due to nanopore guidance? | — | Adult | **Not proven** |
| Survival improvement caused by nanopore-guided surgery? | — | Any | **Not proven** |

---

# Part VI — What makes the adult angle interesting

The adult literature now supports a coherent causal chain:

1. **Extent of resection matters in adult diffuse glioma**, but must be balanced against functional morbidity (PIONEER/RANO 2026).
2. **The expected benefit of aggressive resection may not be biologically uniform**, including across glioblastoma methylation subclasses (Drexler et al. 2023; 2025).
3. **Frozen section can misclassify clinically important adult gliomas**, and rapid molecular testing can correct that interpretation within tens of minutes (Wu et al. 2025).
4. **Nanopore can already provide much richer information during the same operative window**: methylation class, genome-wide CNV, `+7/-10`, `1p/19q`, focal amplifications and, with continued sequencing, SNV/SV information (iSCORED, Rapid-CNS2, ROBIN).
5. **Actual real-time strategy change has now been demonstrated with nanopore in paediatric care** (Sie et al. 2026).
6. **What remains insufficiently demonstrated is the same clinical-impact step in adult neuro-oncology.**

That gap is potentially a stronger scientific position than another pure feasibility study.

---

# Evidence hierarchy for a jury

| Claim | Evidence level in 2026 |
|---|---|
| Molecular CNS classification can be produced during surgery | **Strong, multicentre / peer-reviewed** |
| Result can be delivered in ~60–120 min | **Strong** |
| Methylation + genome-wide CNV can add information unavailable from morphology alone | **Strong** |
| Rapid molecular testing can correct frozen-section interpretation in adult diffuse glioma | **Strong prospective evidence** |
| Molecular subclass may modify the benefit expected from maximal GBM resection | **Retrospective multicentre association; biologically compelling, not yet treatment-selection standard** |
| Nanopore can change actual intraoperative surgical strategy | **Demonstrated in paediatric real-world care** |
| Adult nanopore-guided strategy change | **Not yet adequately demonstrated** |
| Reduction in adult neurological morbidity | **Not proven** |
| Improvement in survival from nanopore guidance | **Not proven** |
| Cost-effectiveness | **Not established** |

---

# Most defensible clinical framing

> **The innovation is not simply to shorten molecular diagnostic turnaround time. It is to move tumour biology from the postoperative period into the intraoperative decision window, when the balance between oncological benefit and neurological risk can still be modified.**

For an adult-focused programme:

> **Recent adult data show that rapid molecular information can correct intraoperative diagnostic uncertainty and that the survival benefit of maximal resection may differ across molecular glioblastoma subclasses. Nanopore sequencing can now generate methylation and genome-wide copy-number information within the surgical window, but its direct impact on adult neurosurgical decision-making remains insufficiently studied.**

Avoid claiming that nanopore has already been proven to prevent neurological morbidity or improve survival. The strongest current claim is that it provides **timely, biologically relevant decision support**, with a clear adult evidence gap for prospective clinical-impact evaluation.
