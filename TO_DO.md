# TO DO — AAP Jeunes Chercheurs Tremplin 2026

**Projet :** implémentation clinique accélérée du séquençage nanopore pour la classification moléculaire des tumeurs du SNC  
**Version :** 2026-09-09  

Ce fichier regroupe les éléments encore à obtenir ou à verrouiller avant finalisation du dossier.

> **Changement de cadrage — 9 septembre 2026**  
> Le projet ne doit plus être conçu par défaut comme une large cohorte de validation locale de 100–200 patients avant toute utilisation clinique. La trajectoire de travail devient : **benchmark/transfert depuis un centre expérimenté → qualification/vérification locale courte → évaluation clinique prospective → périopératoire si les critères analytiques, qualité et réglementaires sont remplis**. L'effectif de la phase locale doit être défini selon sa finalité réelle et non fixé a priori.

## 0. Benchmark opérationnel avec Toulouse — priorité immédiate

- [ ] Identifier l'équipe toulousaine qui réalise effectivement le workflow méthylome/Nanopore et les interlocuteurs biologiste/neuropathologiste/bioinformaticien.
- [ ] Organiser un échange avec le CHU/IUCT Toulouse avant de figer le protocole analytique et le budget.
- [ ] Confirmer la plateforme exacte : MinION / GridION / PromethION / autre.
- [ ] Confirmer le type de flow cell et sa référence.
- [ ] Confirmer le kit de librairie/barcoding et sa version.
- [ ] Confirmer la méthode d'extraction et les exigences de quantité/qualité d'ADN.
- [ ] Confirmer singleplex/multiplexage et nombre de patients par run.
- [ ] Documenter le pipeline : basecalling, methylation calling, classifieur, version, seuils, CNV, MGMT et autres sorties.
- [ ] Documenter le délai réel extraction → résultat et le délai jusqu'au premier résultat exploitable.
- [ ] Obtenir le taux de résultats non conclusifs et les principales causes d'échec.
- [ ] Obtenir le coût complet réel par patient : flow cell, kit, extraction/QC, consommables, calcul, temps technicien/biologiste.
- [ ] Comprendre le cadre qualité/réglementaire utilisé : validation analytique, LDT, ISO 15189, IVDR/article 5(5) si applicable.
- [ ] Comprendre le circuit clinique : prescription, interprétation neuropathologique, compte rendu, interaction avec extemporané et neurochirurgie.
- [ ] Demander les points qu'ils modifieraient s'ils redémarraient aujourd'hui le workflow.

**À reporter ensuite dans :** `project_manuscript_*`, `methodology_*` et `budget_previsionnel_AAP_JC2026.xlsx`.

---

## 1. Recrutement réel

- [ ] Récupérer le nombre annuel de patients opérés / pris en charge pour une tumeur du SNC au CHU Montpellier.
- [ ] Estimer le nombre annuel de cas disposant d’un prélèvement congelé exploitable.
- [ ] Documenter la répartition approximative des principales familles tumorales si disponible.
- [ ] Distinguer les cas potentiellement pertinents pour une phase de qualification locale des cas éligibles à une phase clinique prospective.
- [ ] Estimer le volume de cas permettant une utilisation périopératoire après qualification.

**À renseigner :**

- Nombre de cas/an : `........................................`
- Nombre avec congelé/an : `........................................`
- Nombre potentiellement éligible à une phase clinique prospective/an : `........................................`
- Commentaire : `........................................`

---

## 2. Design et effectif à redéfinir avec l’URCE

- [ ] Ne pas partir d'un effectif de 80–200 patients par défaut.
- [ ] Définir d'abord la finalité de chaque phase : qualification analytique, vérification locale d'une méthode transférée, performance clinique prospective, puis impact périopératoire.
- [ ] Déterminer avec qualité/URCE le nombre de cas nécessaire à la phase locale de qualification.
- [ ] Définir séparément l'effectif de la phase clinique prospective.
- [ ] Définir séparément, si elle est incluse dans l'AAP, l'effectif de la phase périopératoire.
- [ ] Choisir le critère principal correspondant au design final : concordance, diagnostic yield, délai, proportion de diagnostics résolus, ou autre critère clinique.
- [ ] Définir les critères de passage entre phases avant le début du projet.

**À renseigner :**

- Design final : `........................................`
- Finalité phase A/transfert : `........................................`
- Finalité phase B/qualification : `........................................`
- Effectif phase B : `........................................`
- Finalité phase C/clinique prospective : `........................................`
- Effectif phase C : `........................................`
- Phase D/périopératoire incluse dans l'AAP : `oui / non / à discuter`
- Critère principal : `........................................`

---

## 3. Statut réglementaire exact et passage au rendu clinique

- [ ] Faire qualifier le projet par l’URCE / DRI.
- [ ] Déterminer le cadre de chaque phase plutôt qu'un statut unique supposé pour l'ensemble du projet.
- [ ] Confirmer si les phases de recherche relèvent d’une **HLJ**, d’une **RIPH3**, ou d’un autre cadre compatible avec l’AAP.
- [ ] Définir avec le laboratoire et la qualité les conditions permettant de passer d'un résultat expérimental à un résultat pouvant contribuer au diagnostic clinique.
- [ ] Vérifier les exigences IVDR applicables aux tests développés en laboratoire, notamment l'article 5(5), et l'articulation avec l'ISO 15189.
- [ ] Vérifier les modalités de constitution / utilisation prospective du prélèvement congelé.
- [ ] Vérifier les obligations relatives à l’information / consentement / non-opposition.
- [ ] Vérifier le cadre de conservation et d’utilisation des données génomiques.
- [ ] Définir le circuit de validation biologique/neuropathologique et de compte rendu du résultat si utilisation clinique.

**À renseigner :**

- Qualification réglementaire : `........................................`
- Cadre qualité / LDT : `........................................`
- Conditions de passage au rendu clinique : `........................................`
- Procédure d’information / consentement : `........................................`
- Interlocuteur URCE/DRI : `........................................`
- Interlocuteur qualité/accréditation : `........................................`
- Commentaire : `........................................`

---

## 4. Coûts institutionnels et prix marché réels

### Oxford Nanopore

- [ ] Obtenir le prix marché CHU Montpellier de `FLO-MIN114` si cette référence reste pertinente après le retour toulousain.
- [ ] Obtenir le prix marché CHU Montpellier de `SQK-RBK114.24` si ce kit reste pertinent après le retour toulousain.
- [ ] Vérifier les éventuels tarifs dégressifs / remises volume.
- [ ] Comparer le coût théorique actuel au coût réel du workflow toulousain.

### CRB / tumorothèque

- [ ] Obtenir un devis spécifique pour la constitution prospective et la prise en charge d’un fragment congelé d’environ 20–30 mg par patient.
- [ ] Clarifier les frais de gestion applicables.
- [ ] Clarifier si le stockage doit être budgété séparément.

### Autres coûts complets AAP

- [ ] Frais de promotion CHU.
- [ ] Coût méthodologie / biostatistiques / URCE.
- [ ] Coût qualité/accréditation/validation si applicable.
- [ ] Éventuel coût de personnel spécifique au projet.
- [ ] Plateformes / prestations internes complémentaires.
- [ ] Stockage / gestion de données si valorisé.
- [ ] Autres coûts obligatoires identifiés par la DRI.

**À reporter ensuite dans :** `budget_previsionnel_AAP_JC2026.xlsx`

**À renseigner :**

- Flow cell retenue : `........................................`
- Prix flow cell : `........................................ € HT`
- Kit retenu : `........................................`
- Prix kit : `........................................ € HT`
- CRB / patient : `........................................ € HT`
- Promotion : `........................................ €`
- Méthodologie / URCE : `........................................ €`
- Qualité / validation : `........................................ €`
- Personnel : `........................................ €`
- Autres : `........................................ €`

---

## 5. Composition de l’équipe et responsabilités

- [ ] Identifier le porteur principal.
- [ ] Identifier le(s) neuropathologiste(s) impliqué(s).
- [ ] Identifier les responsables du workflow moléculaire / PMMG.
- [ ] Identifier les responsables bioinformatiques.
- [ ] Identifier l’interlocuteur CRB / tumorothèque.
- [ ] Impliquer la neurochirurgie dès la conception de la phase clinique/périopératoire.
- [ ] Identifier le méthodologiste / biostatisticien URCE.
- [ ] Identifier un interlocuteur qualité/accréditation.
- [ ] Définir les responsabilités principales de chaque membre.

**À renseigner :**

| Rôle | Nom | Structure | Responsabilités |
|---|---|---|---|
| Porteur |  |  |  |
| Neuropathologie |  |  |  |
| PMMG / biologie moléculaire |  |  |  |
| Bioinformatique |  |  |  |
| CRB / tumorothèque |  |  |  |
| Neurochirurgie |  |  |  |
| Méthodologie / biostatistiques |  |  |  |
| Qualité / accréditation |  |  |  |

---

## 6. Choix techniques à verrouiller après Toulouse et avant protocole final

- [ ] Séquenceur / configuration exacte retenue.
- [ ] Flow cell exacte.
- [ ] Kit de librairie/barcoding exact.
- [ ] Méthode d’extraction d’ADN définitive.
- [ ] Quantité/qualité minimale d'ADN.
- [ ] Durée et critères d’arrêt des runs.
- [ ] Singleplex/multiplexage par phase.
- [ ] Liste définitive des classifieurs : crossNN / nanoDx, MethyLYZR, Sturgeon, MNP-Flex ± autres.
- [ ] Versions exactes des modèles.
- [ ] Seuils de confiance prédéfinis.
- [ ] Règles de mapping methylation family/class/subclass vers le diagnostic clinique.
- [ ] Sorties additionnelles : CNV, `MGMT`, SNV/indels, SV/fusions selon la stratégie retenue.
- [ ] Définition finale d’une classification « correcte et stable » pour la phase rapide.
- [ ] Format du compte rendu et règle de validation par neuropathologie.

---

## 7. Recommandations et justification institutionnelle — désormais disponibles

- [x] WHO CNS5 2021 ajouté à la bibliographie comme classification officielle.
- [x] EANO 2023 : accès au profilage de méthylation recommandé pour tout établissement impliqué dans le diagnostic des tumeurs du SNC.
- [x] cIMPACT-NOW update 9 2025 : recommandations dédiées au profilage pangénomique de méthylation.
- [x] ICCR 2024 : methylome profiling intégré comme élément moléculaire core.
- [x] SIOPE/ERN PaedCan : accès à une plateforme de méthylation en neuropathologie pédiatrique ; Nanopore cité parmi les méthodes utilisées pour le médulloblastome.
- [x] cIMPACT-NOW update 11 2026 : exemple PFB où l'absence de méthylome conduit à rester NOS.
- [x] ANOCEF Glioblastome 2025 : méthylome utile dans les diagnostics difficiles et recommandation de congeler du tissu tumoral.
- [x] WHO CNS6 : volume CNS officiellement en cours d'élaboration ; ne pas anticiper sa formulation finale.
- [x] Document détaillé : `methylome_guidelines_and_clinical_implementation_rationale_2026-09-09.md`.

---

## Statut global

### Déjà disponible

- [x] Revue bibliographique récente et structurée.
- [x] Justification clinique et translationnelle.
- [x] Argumentaire international/européen/français sur le méthylome.
- [x] Faisabilité locale CHU Montpellier / PMMG / MOBIDIC.
- [x] Preuves publiées de faisabilité nanopore et périopératoire.
- [x] Plan initial de méthodologie et statistiques, à réviser selon le nouveau cadrage.
- [x] Budget technique prévisionnel Markdown.
- [x] Budget Excel paramétrable.
- [x] Bibliographie BibTeX enrichie des classifications et recommandations officielles.

### À verrouiller avant version finale

- [ ] Retour opérationnel Toulouse.
- [ ] Design final et séquençage des phases.
- [ ] Recrutement réel.
- [ ] Effectifs par phase.
- [ ] Qualification réglementaire et qualité du rendu clinique.
- [ ] Prix marché / devis institutionnels.
- [ ] Équipe et responsabilités.
- [ ] Paramètres techniques définitifs.
- [ ] Réécriture du manuscrit AAP et de la méthodologie selon ce cadrage.
