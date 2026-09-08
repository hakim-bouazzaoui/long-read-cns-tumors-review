# TO DO — AAP Jeunes Chercheurs Tremplin 2026

**Projet :** validation du séquençage nanopore sur prélèvements tumoraux congelés du SNC  
**Version :** 2026-09-08  

Ce fichier regroupe les éléments encore à obtenir ou à verrouiller avant finalisation du dossier.

## 1. Recrutement réel

- [ ] Récupérer le nombre annuel de patients opérés / pris en charge pour une tumeur du SNC au CHU Montpellier.
- [ ] Estimer le nombre annuel de cas disposant d’un prélèvement congelé exploitable.
- [ ] Vérifier la faisabilité d’un recrutement de l’ordre de 80–200 patients sur la durée du projet.
- [ ] Documenter la répartition approximative des principales familles tumorales si disponible.

**À renseigner :**

- Nombre de cas/an : `........................................`
- Nombre avec congelé/an : `........................................`
- Durée réaliste d’inclusion : `........................................`
- Commentaire : `........................................`

---

## 2. Calcul d’effectif définitif avec l’URCE

- [ ] Discuter avec l’URCE de l’objectif statistique principal.
- [ ] Choisir entre :
  - estimation de la concordance avec précision prédéfinie ;
  - démonstration que la concordance dépasse un seuil minimal cliniquement acceptable.
- [ ] Définir le seuil minimal de performance acceptable si une approche avec hypothèse nulle est retenue.
- [ ] Fixer le risque alpha, la puissance et le taux attendu de non-évaluables.
- [ ] Valider l’effectif final de la cohorte principale.
- [ ] Valider l’effectif de la sous-cohorte cinétique.

**À renseigner :**

- Approche statistique retenue : `........................................`
- Concordance attendue : `........................................`
- Seuil minimal acceptable : `........................................`
- Alpha : `........................................`
- Puissance : `........................................`
- Effectif final : `........................................`
- Sous-cohorte cinétique : `........................................`

---

## 3. Statut réglementaire exact

- [ ] Faire qualifier le projet par l’URCE / DRI.
- [ ] Confirmer si le projet relève d’une **HLJ**, d’une **RIPH3**, ou d’un autre cadre compatible avec l’AAP.
- [ ] Vérifier les modalités de constitution / utilisation prospective du prélèvement congelé.
- [ ] Vérifier les obligations relatives à l’information / consentement / non-opposition.
- [ ] Vérifier le cadre de conservation et d’utilisation des données génomiques.

**À renseigner :**

- Qualification réglementaire : `........................................`
- Procédure d’information / consentement : `........................................`
- Interlocuteur URCE/DRI : `........................................`
- Commentaire : `........................................`

---

## 4. Coûts institutionnels et prix marché réels

### Oxford Nanopore

- [ ] Obtenir le prix marché CHU Montpellier de `FLO-MIN114`.
- [ ] Obtenir le prix marché CHU Montpellier de `SQK-RBK114.24`.
- [ ] Vérifier les éventuels tarifs dégressifs / remises volume.

### CRB / tumorothèque

- [ ] Obtenir un devis spécifique pour la constitution prospective et la prise en charge d’un fragment congelé d’environ 20–30 mg par patient.
- [ ] Clarifier les frais de gestion applicables.
- [ ] Clarifier si le stockage doit être budgété séparément.

### Autres coûts complets AAP

- [ ] Frais de promotion CHU.
- [ ] Coût méthodologie / biostatistiques / URCE.
- [ ] Éventuel coût de personnel spécifique au projet.
- [ ] Plateformes / prestations internes complémentaires.
- [ ] Stockage / gestion de données si valorisé.
- [ ] Autres coûts obligatoires identifiés par la DRI.

**À reporter ensuite dans :** `budget_previsionnel_AAP_JC2026.xlsx`

**À renseigner :**

- FLO-MIN114 : `........................................ € HT`
- SQK-RBK114.24 : `........................................ € HT`
- CRB / patient : `........................................ € HT`
- Promotion : `........................................ €`
- Méthodologie / URCE : `........................................ €`
- Personnel : `........................................ €`
- Autres : `........................................ €`

---

## 5. Composition de l’équipe et responsabilités

- [ ] Identifier le porteur principal.
- [ ] Identifier le(s) neuropathologiste(s) impliqué(s).
- [ ] Identifier les responsables du workflow moléculaire / PMMG.
- [ ] Identifier les responsables bioinformatiques.
- [ ] Identifier l’interlocuteur CRB / tumorothèque.
- [ ] Identifier, si pertinent à ce stade, les interlocuteurs neurochirurgie.
- [ ] Identifier le méthodologiste / biostatisticien URCE.
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

---

## 6. Choix techniques à verrouiller avant protocole final

Ces points ne bloquent pas la rédaction de la première version du manuscrit mais devront être préspécifiés avant démarrage de l’étude.

- [ ] Séquenceur / configuration exacte retenue.
- [ ] Méthode d’extraction d’ADN définitive.
- [ ] Durée et critères d’arrêt des runs.
- [ ] Nombre exact de patients par flow cell dans la cohorte principale.
- [ ] Singleplex ou 2-plex pour la sous-cohorte cinétique.
- [ ] Liste définitive des classifieurs : crossNN / nanoDx, MethyLYZR, Sturgeon, MNP-Flex ± autres.
- [ ] Versions exactes des modèles.
- [ ] Seuils de confiance prédéfinis.
- [ ] Règles de mapping methylation family/class/subclass vers le diagnostic clinique de référence.
- [ ] Définition finale d’une classification « correcte et stable ».

---

## Statut global

### Déjà disponible

- [x] Revue bibliographique récente et structurée.
- [x] Justification clinique et translationnelle.
- [x] Faisabilité locale CHU Montpellier / PMMG / MOBIDIC.
- [x] Méthodologie générale.
- [x] Plan statistique de principe.
- [x] Comparaison multi-classifieurs pré-entraînés.
- [x] Stratégie cohorte principale 6-plex + sous-cohorte cinétique.
- [x] Budget technique prévisionnel Markdown.
- [x] Budget Excel paramétrable.
- [x] Bibliographie BibTeX.

### À verrouiller avant version finale

- [ ] Recrutement réel.
- [ ] Effectif définitif.
- [ ] Qualification réglementaire.
- [ ] Prix marché / devis institutionnels.
- [ ] Équipe et responsabilités.
- [ ] Paramètres techniques définitifs.
