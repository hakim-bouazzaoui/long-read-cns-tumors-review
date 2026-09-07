# Perioperative clinical impact of rapid nanopore CNS tumour classification

**Question:** is the value proposition limited to faster diagnosis, or is there evidence that intraoperative molecular classification can change neurosurgical management?

## Executive conclusion

Yes. The literature has moved beyond analytical feasibility. The strongest published evidence shows that **obtaining molecular tumour identity while surgery is still ongoing can change the intended extent of resection**. However, the evidence hierarchy remains important:

- **decision impact:** demonstrated;
- **actual reduction in second-look surgery:** promising, but the strongest quantitative dataset remains a preprint as of September 2026;
- **reduction in neurological morbidity, quality-of-life benefit or survival benefit:** not yet proven in a controlled prospective trial.

The most defensible clinical framing is therefore **“biologically informed intraoperative decision support”**, not a claim that nanopore sequencing has already been proven to improve survival.

---

## 1. Djirackor et al., Neuro-Oncology Advances 2021 — strongest peer-reviewed decision-impact paper

**Intraoperative DNA methylation classification of brain tumors impacts neurosurgical strategy**  
DOI: `10.1093/noajnl/vdab149`

- 105 patients overall.
- Nanopore methylation classification concordant with final diagnosis in **93/105 (89%)**.
- Correct diagnosis in **6/6** cases where frozen section was inconclusive.
- Result returned to the operating room at a median of **97 min** (range 91–161 min).
- In the **20 intraoperative cases**, precise molecular classification **would have supported modification of the surgical strategy in 12/20 (60%)**.

### Clinically important examples

The paper describes both directions of potential benefit:

1. **Avoiding under-resection / unnecessary second surgery**  
   In several cases resection had been stopped because imaging/frozen section remained uncertain. Nanopore classification correctly identified a resectable tumour and would have supported continuation of resection. One case was considered a possible lymphoma intraoperatively, surgery was stopped, and final diagnosis was medulloblastoma; the patient required reoperation.

2. **Avoiding unnecessary additional resection and neurological risk**  
   A patient was taken back for removal of a small medulloblastoma remnant, whereas the nanopore result identified a **WNT-activated medulloblastoma**, a context in which further high-risk resection was considered unnecessary by the authors.

### Interpretation

This is the clearest peer-reviewed evidence that the assay can alter the **risk-versus-benefit calculation of extent of resection**, rather than merely accelerate the final pathology report.

**Important nuance:** the wording in the study is “would have supported modification”; this was not a randomized intervention trial measuring postoperative morbidity.

---

## 2. Vermeulen et al., Nature 2023 — Sturgeon

**Ultra-fast deep-learned CNS tumour classification during surgery**  
DOI: `10.1038/s41586-023-06615-2`

- 50 retrospective nanopore samples: **45/50** correctly classified within 20–40 min sequencing; 5 abstentions.
- **25 real surgeries**.
- **<90 min** diagnostic turnaround.
- **18/25 (72%)** correct diagnoses; 7 did not cross the confidence threshold.

The paper explicitly frames the use case as assistance to neurosurgical decision-making, with the potential to avoid neurological comorbidity and additional surgery.

### Interpretation

This is a landmark proof that an AI methylation classifier can deliver molecular information **within the operative window**. It is much stronger on real-time feasibility than on quantified changes in management; the paper does not provide a controlled estimate of morbidity or reoperation reduction.

---

## 3. Patel et al., Nature Medicine 2025 — Rapid-CNS2

**Prospective, multicenter validation of a platform for rapid molecular profiling of central nervous system tumors**  
DOI: `10.1038/s41591-025-03562-5`

- 301 samples overall; two-centre validation.
- 18 samples sequenced in actual real-time intraoperative workflows.
- Methylation + CNV information within a 30-min sequencing window; overall intraoperative report within ~90 min from sample receipt.
- In **13/18 (72.2%)** intraoperative cases, integration of methylation and CNV provided clinically relevant additional information on tumour type/subtype or risk profile compared with morphology alone.

Examples included distinguishing **IDH-mutant astrocytoma from IDH-wildtype glioblastoma**, subtyping ependymoma and defining copy-number risk information in meningioma.

### Critical limitation

The authors state explicitly that the results were **not yet used for surgical decision-making**. A prospective outcome study was being prepared.

### Interpretation

Excellent evidence that the information required for surgical stratification can be generated in time; not yet evidence that acting on it improves patient outcomes.

---

## 4. Deacon et al., Neuro-Oncology 2025 — ROBIN

**ROBIN: A unified nanopore-based assay integrating intraoperative methylome classification and next-day comprehensive profiling for ultra-rapid tumor diagnosis**  
DOI: `10.1093/neuonc/noaf103`

- 50 prospective intraoperative cases.
- Diagnostic turnaround **<2 h**.
- **90% concordance** with final integrated diagnosis after the complete sequencing run.
- Single assay can continue after the intraoperative result to provide CNV, SNV and SV information by the next day.

### Interpretation

Strong prospective workflow and diagnostic evidence. The authors describe the result as clinically actionable and suitable for tailoring the surgical approach, but the study was not designed to quantify changes in extent of resection, neurological morbidity or reoperation.

---

## 5. Eelkman Rooda et al., Child's Nervous System 2026 — clinical framing becomes explicit

**The emerging role of intraoperative nanopore sequencing on the neurosurgical strategy in paediatric embryonal brain tumours**  
DOI: `10.1007/s00381-026-07377-8`

This peer-reviewed 2026 review shifts the discussion from “can we classify the tumour rapidly?” to **“how should molecular identity alter surgical radicality?”**

The authors emphasize that:

- the oncological benefit of extent of resection is not uniform across tumour entities/subgroups;
- the relevant intraoperative timepoint is before the surgeon reaches functionally critical margins;
- a molecular diagnosis can support either **more aggressive** or **more conservative** resection depending on biology;
- future studies should prospectively measure **neurological morbidity, second-look surgery, extent of resection, time to treatment and patient-reported outcomes**.

They discuss examples such as:

- **WNT medulloblastoma:** rationale for avoiding high-risk pursuit of tiny residual disease once near-total resection is achieved;
- **AT/RT / ETMR:** aggressive biology may strengthen the rationale for maximal safe resection when technically feasible.

### Interpretation

This paper provides a recent, peer-reviewed conceptual framework for positioning intraoperative nanopore sequencing as a **neurosurgical decision-support technology**, while explicitly acknowledging that high-level outcome evidence is still missing.

---

## 6. Emerging but not yet core evidence

### “How Sturgeon guides the surgeon” — preprint, 2025

This is currently the most direct real-world care-evaluation dataset but remains a **medRxiv preprint**, so it should not be used as a core bibliographic reference until peer-reviewed publication.

Reported results:

- 94 consecutive paediatric patients;
- correct Sturgeon diagnosis in **82/94 (87.2%)** in <90 min;
- in the decision-impact subset, the result changed the surgical strategy in **14.3%** toward either more or less aggressive resection;
- reported second-look surgery rate **3.2%**.

This is highly encouraging but should be labelled as preliminary/non-peer-reviewed evidence.

### 2025 Neuro-Oncology conference abstract from Oslo

An oral-presentation abstract reported 87 intraoperative cases, mean sample-to-OR report time **76 min**, >90% diagnostic concordance and molecular information supporting modulation of resection strategy in >50% of surgeries. It is conference-level evidence only and should not be placed in the main peer-reviewed bibliography.

---

## 7. Why knowing the molecular diagnosis can matter during surgery

The clinical logic is entity-specific rather than “more resection is always better”.

### Medulloblastoma

A molecularly informed literature shows that the apparent prognostic benefit of more extensive resection is attenuated after accounting for molecular subgroup. A 2018 systematic review concluded that the prognostic importance of extent of resection remains uncertain and should be re-evaluated in the molecular era. This supports avoiding neurologically high-risk pursuit of small residual disease when the expected oncological gain is limited.

### Other CNS tumours

Conversely, for entities in which extent of resection has stronger prognostic importance, a confident molecular diagnosis can justify continuing maximal safe resection when imaging or frozen-section interpretation is equivocal.

The value proposition is therefore **not uniform de-escalation**. It is **better matching of surgical risk to tumour biology**.

---

## 8. Evidence hierarchy for a jury

| Claim | Evidence level in 2026 |
|---|---|
| Molecular CNS classification can be produced during surgery | **Strong, multicentre/peer-reviewed** |
| Result can be delivered in ~60–120 min | **Strong** |
| Methylation + genome-wide CNV can add information unavailable from morphology alone | **Strong** |
| Intraoperative molecular identity can change intended extent of resection | **Demonstrated, but still limited cohorts** |
| It can avoid unnecessary additional surgery | **Plausible + case-level/early implementation evidence** |
| It reduces neurological morbidity | **Not yet proven prospectively** |
| It improves survival | **Not proven** |
| It is cost-effective | **Not yet established** |

---

## 9. Most defensible clinical framing

> **The innovation is not simply to shorten the molecular diagnostic turnaround time. It is to move molecular tumour identity from the postoperative period into the intraoperative decision window, when the balance between oncological benefit and neurological risk can still be modified.**

A second useful formulation is:

> **Rapid nanopore profiling may enable biology-informed neurosurgery: avoiding unnecessary high-risk resection when the expected oncological gain is limited, while supporting further safe resection when tumour biology makes local control particularly important.**

Avoid claiming at this stage that the method “prevents neurological morbidity” as an established fact. The literature supports **potential reduction** and provides strong rationale for making morbidity and reoperation key clinical endpoints of future prospective evaluation.
