# Budget prévisionnel — validation nanopore des tumeurs du SNC

**Projet :** AAP Jeunes Chercheurs Tremplin 2026 — CHU Montpellier  
**Version :** 2026-09-08 — v1  
**Statut :** budget technique provisoire, à remplacer par les prix marché CHU Montpellier et le devis CRB/tumorothèque  

> **Important.** Ce document ne constitue pas encore le budget en coût complet de l’AAP. Il estime le coût technique incrémental lié au prélèvement congelé et au workflow nanopore. Les coûts de promotion, méthodologie/URCE, personnel, gestion des données et autres coûts institutionnels obligatoires devront être ajoutés avec la DRI/URCE. Le plafond AAP est de 60 k€ par projet.

---

## 1. Périmètre budgétaire

Le diagnostic de référence anatomopathologique et moléculaire sur FFPE est réalisé dans le cadre du soin courant et n’est donc pas imputé au coût expérimental nanopore dans cette estimation.

Les équipements déjà disponibles localement ne sont pas budgétés :

- séquenceur(s) Oxford Nanopore ;
- infrastructure informatique et stockage de calcul déjà disponibles ;
- matériel courant de laboratoire déjà disponible.

Le budget technique additionnel comprend :

1. constitution/prise en charge du fragment tumoral congelé ;
2. extraction d’ADN ;
3. quantification/QC de l’ADN ;
4. préparation de librairie nanopore ;
5. flow cells ;
6. petits consommables ;
7. marge pour échec/perte technique.

---

## 2. Stratégie de séquençage retenue pour le chiffrage

La méthodologie distingue deux groupes :

### Cohorte principale

**6 patients par flow cell (6-plex)** pour la validation diagnostique.

Cette stratégie limite le coût par patient et correspond à la question principale de concordance diagnostique avec le diagnostic intégré sur FFPE.

### Sous-cohorte cinétique

Une sous-cohorte prédéfinie sera séquencée en **singleplex ou faible multiplexage** afin de mesurer une cinétique de classification réellement compatible avec une future transposition peropératoire.

L’effectif définitif de cette sous-cohorte sera fixé avec l’URCE et selon le budget disponible.

Pour la planification financière uniquement, les tableaux ci-dessous utilisent un **scénario de travail de 12 patients** dans cette sous-cohorte et présentent deux possibilités :

- scénario A : 12 patients en **singleplex** = 12 flow cells ;
- scénario B : 12 patients en **2-plex** = 6 flow cells.

Le nombre 12 n’est pas un effectif méthodologique définitivement retenu.

---

## 3. Prix unitaires de référence au 8 septembre 2026

### 3.1. Oxford Nanopore

| Référence | Produit | Prix catalogue EU utilisé | Hypothèse budgétaire |
|---|---|---:|---|
| `FLO-MIN114` | MinION/GridION Flow Cell, R10.4.1 | **740 € / flow cell** | 1 flow cell par run |
| `SQK-RBK114.24` | Rapid Barcoding Kit 24 V14 | **730 € / kit** | 6 réactions complètes par kit |

Le Rapid Barcoding Kit permet jusqu’à 24 échantillons barcodés par réaction, est PCR-free, nécessite 200 ng de gDNA par échantillon et préserve l’information de modifications de bases. Pour le présent projet, une réaction sera utilisée pour préparer chaque run 6-plex, 2-plex ou singleplex.

Ainsi :

- coût du kit par réaction/run = `730 / 6` = **121,67 €** ;
- en 6-plex, contribution du kit = **20,28 €/patient** ;
- en 2-plex = **60,83 €/patient** ;
- en singleplex = **121,67 €/patient**.

**Sources :**

- Oxford Nanopore EU price list : https://store.nanoporetech.com/eu/priceList.html
- Rapid Barcoding Kit 24 V14 : https://store.nanoporetech.com/rapid-barcoding-sequencing-kit-24-v14.html

> **À remplacer dès disponibilité :** prix marché CHU Montpellier de `FLO-MIN114` et `SQK-RBK114.24`.

---

### 3.2. Extraction d’ADN

Référence de travail : **QIAGEN QIAamp Fast DNA Tissue Kit, réf. 51404**.

- prix catalogue France : **296 € / 50 préparations** ;
- coût théorique : **5,92 €/patient**.

Source : https://www.qiagen.com/fr-fr/products/discovery-and-translational-research/dna-rna-purification/dna-purification/genomic-dna/qiaamp-fast-dna-tissue-kit

Ce choix est provisoire. Si le PMMG utilise en routine une extraction automatisée disponible via un marché existant, le tarif réel devra remplacer cette estimation.

---

### 3.3. Quantification de l’ADN

Référence de travail : **Qubit dsDNA HS Assay Kit, réf. Q32851**.

- prix catalogue France observé : **135,65 € / 100 dosages** ;
- coût théorique : **1,36 €/patient**.

Source : https://www.thermofisher.com/order/catalog/product/fr/en/Q32851

---

### 3.4. Petits consommables

Provision de travail : **4 €/patient** pour les consommables non intégrés ou non valorisés séparément : tubes LoBind, tubes PCR, pointes, plaques/films, etc.

Cette valeur devra être affinée avec le laboratoire.

---

## 4. CRB / tumorothèque — poste encore incertain

La grille publique du CRB du CHU de Montpellier fournit des tarifs collaboratifs utiles comme **proxy**, mais ces tarifs correspondent à des coûts de cession/ressources et ne remplacent pas le devis à établir pour une constitution prospective dans le cadre du protocole.

Tarifs collaboratifs publiés, hors frais de gestion et hors taxes :

| Ressource | Tarif collaboratif publié |
|---|---:|
| Coupe / fragment congelé ≤30 mg | **55 € HFG HT** |
| Fragment tumoral congelé 100 mg | **110 € HFG HT** |
| Hébergement -20/-80 °C, 100 échantillons ≤2 mL | **300 €/an HFG HT** |

La grille précise des **frais de gestion de 12 %**.

Pour les calculs provisoires, deux hypothèses sont donc utilisées :

- **hypothèse CRB basse :** 55 × 1,12 = **61,60 €/patient** ;
- **hypothèse CRB haute :** 110 × 1,12 = **123,20 €/patient**.

Le stockage, s’il est facturé séparément, représente à titre indicatif :

`300 × 1,12 / 100 = 3,36 €/échantillon/an`.

Il n’est **pas ajouté une seconde fois aux totaux** ci-dessous, afin d’éviter un double comptage avant de connaître le contenu du devis prospectif CRB.

Source : https://www.chu-montpellier.fr/fileadmin/medias/Pages/Recherche/plateformes-recherche/CRB/MAJ-2024/RB-9-DX-002-Grille-tarifaire-des-co%C3%BBts-de-fon.pdf

> **À obtenir :** devis CRB/tumorothèque pour constitution prospective et mise à disposition d’un fragment tumoral congelé d’environ 20–30 mg par patient, incluant explicitement réception, contrôle, congélation, traçabilité et stockage.

---

## 5. Coût théorique d’un patient selon le multiplexage

En raisonnant au coût marginal moyen et avant effet d’arrondi lié à l’achat de kits entiers :

| Modalité | Flow cell / patient | Rapid Barcoding / patient | Extraction + Qubit + petits consommables | Total hors CRB | Total avec CRB bas | Total avec CRB haut |
|---|---:|---:|---:|---:|---:|---:|
| Singleplex | 740,00 € | 121,67 € | ~11,28 € | **~873 €** | **~934 €** | **~996 €** |
| 2-plex | 370,00 € | 60,83 € | ~11,28 € | **~442 €** | **~504 €** | **~565 €** |
| 4-plex | 185,00 € | 30,42 € | ~11,28 € | **~227 €** | **~288 €** | **~350 €** |
| **6-plex** | **123,33 €** | **20,28 €** | **~11,28 €** | **~155 €** | **~216 €** | **~278 €** |
| 8-plex | 92,50 € | 15,21 € | ~11,28 € | **~119 €** | **~181 €** | **~243 €** |

Ces valeurs sont destinées à comprendre la structure des coûts. Le budget de commande doit utiliser les nombres entiers de flow cells et de kits, comme dans les sections suivantes.

---

## 6. Cohorte entièrement 6-plex — scénario de référence sans sous-cohorte cinétique dédiée

Ce scénario montre le coût minimal du design si tous les patients étaient séquencés en 6-plex.

Les montants incluent :

- flow cells ;
- Rapid Barcoding kits ;
- extraction ;
- Qubit ;
- 4 €/patient de petits consommables ;
- CRB selon hypothèse basse ou haute ;
- **marge technique de 10 %**.

| Patients | Flow cells | RBK kits | Budget technique + CRB bas + 10 % | Budget technique + CRB haut + 10 % |
|---:|---:|---:|---:|---:|
| 80 | 14 | 3 | **20 378 €** | **25 799 €** |
| 100 | 17 | 3 | **24 263 €** | **31 039 €** |
| 120 | 20 | 4 | **29 426 €** | **37 558 €** |
| 150 | 25 | 5 | **36 464 €** | **46 628 €** |
| 180 | 30 | 5 | **43 025 €** | **55 221 €** |

Ce scénario ne permet cependant pas de mesurer honnêtement un délai chronologique directement transposable au peropératoire.

---

## 7. Scénario A — cohorte principale 6-plex + 12 patients singleplex

Pour `N` patients au total :

- 12 sont séquencés individuellement ;
- `N - 12` sont séquencés en 6-plex.

| Patients totaux | Flow cells totales | RBK kits | Budget + CRB bas + 10 % | Budget + CRB haut + 10 % |
|---:|---:|---:|---:|---:|
| 80 | 24 | 4 | **29 321 €** | **34 742 €** |
| 100 | 27 | 5 | **34 009 €** | **40 785 €** |
| 120 | 30 | 5 | **38 369 €** | **46 501 €** |
| 150 | 35 | 6 | **45 407 €** | **55 571 €** |
| 180 | 40 | 7 | **52 771 €** | **64 967 €** |

### Détail pour 150 patients

- 138 patients en 6-plex = **23 flow cells** ;
- 12 patients en singleplex = **12 flow cells** ;
- total = **35 flow cells** ;
- 35 réactions Rapid Barcoding = **6 kits** ;
- 3 kits d’extraction de 50 préparations ;
- 2 kits Qubit de 100 dosages.

| Poste | Quantité | Montant de référence |
|---|---:|---:|
| FLO-MIN114 | 35 | **25 900 €** |
| SQK-RBK114.24 | 6 | **4 380 €** |
| QIAamp Fast DNA Tissue | 3 | **888 €** |
| Qubit dsDNA HS | 2 | **271,30 €** |
| Petits consommables | 150 × 4 € | **600 €** |
| **Sous-total wet-lab** | | **32 039,30 €** |
| CRB hypothèse basse | 150 × 61,60 € | **9 240 €** |
| CRB hypothèse haute | 150 × 123,20 € | **18 480 €** |

Après marge technique de 10 % :

- **CRB bas : ~45 407 €** ;
- **CRB haut : ~55 571 €**.

Sur une enveloppe maximale de 60 k€, il resterait respectivement environ **14,6 k€** ou **4,4 k€** pour les autres coûts. Le scénario CRB haut est donc probablement trop serré une fois les coûts institutionnels obligatoires ajoutés.

---

## 8. Scénario B — cohorte principale 6-plex + 12 patients en 2-plex

Cette option conserve une acquisition beaucoup plus rapide que le 6-plex tout en divisant par deux le nombre de flow cells de la sous-cohorte cinétique par rapport au singleplex.

| Patients totaux | Flow cells totales | RBK kits | Budget + CRB bas + 10 % | Budget + CRB haut + 10 % |
|---:|---:|---:|---:|---:|
| 80 | 18 | 3 | **23 634 €** | **29 055 €** |
| 100 | 21 | 4 | **28 322 €** | **35 098 €** |
| 120 | 24 | 4 | **32 682 €** | **40 814 €** |
| 150 | 29 | 5 | **39 720 €** | **49 884 €** |
| 180 | 34 | 6 | **47 084 €** | **59 280 €** |

### Détail pour 150 patients

- 138 patients en 6-plex = **23 flow cells** ;
- 12 patients en 2-plex = **6 flow cells** ;
- total = **29 flow cells** ;
- 29 réactions Rapid Barcoding = **5 kits**.

| Poste | Quantité | Montant de référence |
|---|---:|---:|
| FLO-MIN114 | 29 | **21 460 €** |
| SQK-RBK114.24 | 5 | **3 650 €** |
| QIAamp Fast DNA Tissue | 3 | **888 €** |
| Qubit dsDNA HS | 2 | **271,30 €** |
| Petits consommables | 150 × 4 € | **600 €** |
| **Sous-total wet-lab** | | **26 869,30 €** |
| CRB hypothèse basse | 150 × 61,60 € | **9 240 €** |
| CRB hypothèse haute | 150 × 123,20 € | **18 480 €** |

Après marge technique de 10 % :

- **CRB bas : ~39 720 €** ;
- **CRB haut : ~49 884 €**.

Il resterait environ **20,3 k€** ou **10,1 k€** sur l’enveloppe de 60 k€ pour promotion, méthodologie, éventuel personnel et autres coûts.

---

## 9. Lecture budgétaire actuelle

À prix catalogue et avant obtention des tarifs CHU :

- une cohorte de **120 patients** est financièrement confortable, même avec une sous-cohorte cinétique singleplex ;
- une cohorte de **150 patients** paraît compatible avec le budget si le coût CRB réel est proche de l’hypothèse basse ou si la sous-cohorte cinétique est réalisée en 2-plex ;
- **150 patients + 12 singleplex + CRB haut** consommerait presque toute l’enveloppe disponible avant les coûts de promotion/méthodologie ;
- **180 patients** paraît trop ambitieux en singleplex et devient très contraint même avec une sous-cohorte 2-plex lorsque le CRB est valorisé haut.

Le scénario qui offre actuellement le meilleur compromis entre puissance statistique, capacité à étudier la cinétique et marge budgétaire est donc, à titre provisoire :

> **environ 150 patients au total, cohorte principale en 6-plex, avec une sous-cohorte cinétique limitée en faible multiplexage (par exemple 2-plex), à réévaluer après obtention des vrais coûts CHU.**

Cette proposition n’est pas encore un choix méthodologique définitif.

---

## 10. Maximum théorique sous 60 k€ — à ne pas confondre avec l’effectif réellement finançable

Si l’intégralité des 60 k€ était consacrée aux seuls coûts techniques ci-dessus, avec 12 patients dans la sous-cohorte cinétique et une marge de 10 %, le plafond théorique serait approximativement :

| Sous-cohorte | CRB bas | CRB haut |
|---|---:|---:|
| 12 singleplex | **~206 patients** | **~161 patients** |
| 12 en 2-plex | **~228 patients** | **~180 patients** |

Ces nombres **ne doivent pas être utilisés comme effectif cible**, car le budget AAP doit être présenté en coût complet et inclure les coûts institutionnels de promotion, méthodologie et autres postes applicables.

---

## 11. Marché public français — éléments de contexte

Des appels d’offres hospitaliers français récents confirment que les consommables Oxford Nanopore MinION/GridION font l’objet d’achats publics structurés.

En 2026, l’Assistance Publique–Hôpitaux de Marseille a publié un accord-cadre à bons de commande pour la fourniture de réactifs et consommables pour GridION, avec prix unitaires. Les montants publiés dans l’avis sont des estimations de marché et **ne permettent pas de déduire un prix unitaire contractuel** pour nos références.

Référence : https://www.francemarches.com/files/BOAMP/26-34486.html

Un autre marché AP-HP 2026 comporte un lot dédié aux consommables Oxford Nanopore MinION/GridION, avec une quantité estimée de 422 flow cells sur la durée du marché, confirmant l’existence d’un marché hospitalier public significatif pour ces consommables.

Référence : https://www.francemarches.com/appel-offre/3boamp2651031-2026-fourniture-livraison-installation

Les prix catalogue ONT utilisés dans ce document doivent donc être considérés comme une **base prudente de chiffrage**, en attendant le prix réellement applicable au CHU Montpellier.

---

## 12. Informations à obtenir avant gel du budget

### Priorité 1 — achats / marché CHU Montpellier

- [ ] prix unitaire marché de `FLO-MIN114` ;
- [ ] prix marché de `SQK-RBK114.24` ;
- [ ] éventuelles remises quantitatives ;
- [ ] frais de livraison/chaîne du froid éventuels ;
- [ ] modalités de commande et durée de validité du prix.

### Priorité 2 — CRB / tumorothèque

Demander un devis spécifique pour :

- [ ] constitution prospective d’un fragment congelé d’environ 20–30 mg ;
- [ ] réception et traçabilité ;
- [ ] contrôle anatomopathologique si valorisé séparément ;
- [ ] congélation ;
- [ ] stockage pendant la durée du projet ;
- [ ] mise à disposition pour extraction ;
- [ ] frais de gestion applicables.

### Priorité 3 — PMMG

- [ ] méthode d’extraction réellement retenue ;
- [ ] prix marché des réactifs d’extraction ;
- [ ] coût Qubit réel ;
- [ ] petits consommables déjà couverts par le fonctionnement courant ou à budgéter ;
- [ ] besoin éventuel de personnel technique dédié.

### Priorité 4 — DRI / URCE

- [ ] frais de promotion ;
- [ ] coût méthodologique/statistique ;
- [ ] data management ;
- [ ] assurance/monitoring si applicable ;
- [ ] coût de personnel éventuel ;
- [ ] règles de TVA/frais de gestion à retenir dans le budget en coût complet.

---

## 13. Hypothèses à remplacer dès réception des devis

| Variable | Valeur provisoire | Valeur définitive |
|---|---:|---:|
| FLO-MIN114 | 740 € | **à renseigner** |
| SQK-RBK114.24 | 730 € / 6 réactions | **à renseigner** |
| Extraction ADN | 296 € / 50 | **à renseigner** |
| Qubit HS | 135,65 € / 100 | **à renseigner** |
| CRB ≤30 mg + FG | 61,60 €/patient | **à renseigner** |
| CRB 100 mg + FG | 123,20 €/patient | **à renseigner** |
| Petits consommables | 4 €/patient | **à affiner** |
| Marge technique | 10 % | **à valider** |
| Sous-cohorte cinétique | 12 cas pour simulation | **à définir** |
| Multiplexage sous-cohorte | singleplex ou 2-plex | **à définir** |

---

## 14. Conclusion budgétaire provisoire

Le coût de l’étude est principalement déterminé par **le nombre de flow cells** et par **le coût réel de prise en charge du tissu congelé par le CRB**.

Le multiplexage 6-plex de la cohorte principale réduit fortement le coût tout en conservant la possibilité d’une validation diagnostique de taille suffisante. Une sous-cohorte dédiée en singleplex ou faible multiplexage permet d’étudier séparément la cinétique peropératoire sans imposer le coût du singleplex à l’ensemble de la cohorte.

À ce stade, **120–150 patients apparaissent compatibles avec l’enveloppe de l’AAP**, mais le choix final devra être fait uniquement après remplacement des prix catalogue par les prix marché CHU, obtention du devis CRB et intégration des coûts de promotion/méthodologie dans le budget en coût complet.
