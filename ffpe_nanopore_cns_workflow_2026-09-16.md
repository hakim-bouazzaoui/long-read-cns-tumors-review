# Nanopore methylation sur tumeurs du SNC FFPE — état de l’art, wet-lab, bioinformatique et classifieurs

**Date de revue : 16 septembre 2026**  
**Projet : AAP Jeunes Chercheurs Tremplin 2026 — classification moléculaire rapide des tumeurs du SNC par Oxford Nanopore**

## 1. Objet de ce document

Ce document rassemble les éléments nécessaires à une implémentation pratique de la classification méthylationnelle de tumeurs du système nerveux central (SNC) à partir d’ADN FFPE séquencé par Oxford Nanopore Technologies (ONT).

Il distingue volontairement quatre niveaux :

1. **pré-analytique et wet-lab FFPE** : fixation, sélection histologique, extraction, quantité/qualité d’ADN, préparation de librairie, flow cells et matériel ;
2. **traitement bioinformatique ONT** : basecalling, appel des bases modifiées, alignement, extraction des appels CpG, CNV et orchestration ;
3. **classifieurs de méthylation** : Sturgeon, Rapid-CNS², nanoDx/crossNN et MethyLYZR, avec leurs modèles, données d’entraînement et fichiers nécessaires ;
4. **niveau de preuve FFPE** : analyse détaillée des études Afflerbach 2024 et Feinberg-Gorenshtein 2025, puis confirmation par Kerbs 2025 et extension multicentrique ROBIN en 2026.

Le document ne suppose pas qu’un pipeline utilisé dans une publication soit directement transférable en diagnostic clinique. Pour chaque composant, il faut figer une version, un modèle, une référence génomique, des paramètres, des contrôles qualité et les conditions de licence avant validation locale.

---

# 2. Conclusion opérationnelle

La classification méthylationnelle ONT à partir de FFPE est aujourd’hui **démontrée sur plusieurs cohortes indépendantes**. Les publications ne reposent pas sur une seule approche technique : elles couvrent MinION, GridION et PromethION, plusieurs méthodes d’extraction FFPE, des profondeurs allant d’environ 0,03× à 0,83×, et plusieurs classifieurs.

Pour une première implémentation locale, il n’est pas nécessaire de réentraîner un modèle à partir de milliers de profils de méthylation. **Sturgeon et MethyLYZR distribuent des modèles préentraînés.** Les versions modernes de nanoDx incluent également crossNN préentraîné. Rapid-CNS² dispose d’un pipeline Nextflow public et de ressources de classification intégrées. ROBIN constitue un orchestrateur temps réel, et non un classifieur unique.

En revanche, il est nécessaire de :

- conserver l’ADN **non amplifié**, puisque l’information de méthylation est lue directement sur les molécules natives ;
- choisir et figer la méthode d’extraction FFPE ;
- mesurer la quantité et si possible l’intégrité de l’ADN ;
- utiliser un modèle Dorado compatible avec la chimie de flow cell et le calling 5mC/5hmC ;
- conserver les tags MM/ML dans le BAM ;
- ne pas mélanger des coordonnées hg38/GRCh38 et T2T-CHM13v2 sans conversion explicite ;
- figer le classifieur et son artefact de modèle avec checksum ;
- comparer la classification ONT à une référence indépendante, idéalement EPIC/Heidelberg et diagnostic neuropathologique intégré, pendant la phase de qualification locale.

---

# 3. Études utilisant directement des tumeurs SNC FFPE

## 3.1 Études principales analysées en détail

### Afflerbach et al., Acta Neuropathologica, 2024

**Référence**  
Afflerbach AK, Albers A, Appelt A, et al. *Nanopore sequencing from formalin-fixed paraffin-embedded specimens for copy-number profiling and methylation-based CNS tumor classification.* Acta Neuropathol. 2024;147:74. DOI: `10.1007/s00401-024-02731-z`. PMID: `38642165`.

**Cohorte**

- 40 tumeurs du SNC FFPE provenant de trois centres allemands ;
- données Illumina EPIC disponibles pour les 40 cas ;
- entités incluant glioblastomes IDH-WT, oligodendrogliomes, épendymomes de fosse postérieure, médulloblastomes, astrocytomes pilocytiques et méningiome ;
- stockage FFPE moyen : 19 mois, intervalle 1–84 mois ;
- 16/40 échantillons avaient un DIN <5.

**Extraction**

- `Maxwell 16 FFPE Plus LEV DNA Purification Kit`, Promega ; ou
- `RSC FFPE Plus DNA Kit`, Promega.

La publication principale ne donne pas toutes les quantités de réactifs et tous les temps d’incubation : elle renvoie aux Supplementary Methods. Ces paramètres ne doivent donc pas être inventés à partir d’un autre protocole.

**Librairie ONT**

- échantillon seul : `SQK-LSK114` — Ligation Sequencing Kit ;
- multiplexage : `SQK-NBD114` — Native Barcoding Kit ;
- jusqu’à cinq échantillons multiplexés dans leurs expériences.

**Séquençage**

- MinION Mk1B ou Mk1C, ou GridION ;
- flow cell MinION R10.4.1 `FLO-MIN114` ;
- sous-expérience de six échantillons sur Flongle R10.4.1 `FLO-FLG114`.

**Production de données**

- moyenne : 205 000 reads/run ;
- moyenne : 201 Mb/run, intervalle 42–672 Mb ;
- couverture moyenne génomique : ~0,06× ;
- N50 médian des reads alignés : 541 bp, intervalle 279–974 bp.

Ces valeurs sont importantes : cette étude montre que la classification FFPE ne nécessite pas nécessairement une couverture WGS élevée.

**Classifieurs**

- nanoDx, Random Forest dans la génération utilisée ;
- Sturgeon, réseau neuronal.

**Résultats**

- top class correcte nanoDx : 25/40, soit 63 % ;
- top class correcte Sturgeon : 37/40, soit 93 % ;
- avec seuil nanoDx ≥0,15 : 20/40 correctement classés ;
- avec seuil Sturgeon ≥0,8 : 34/40 correctement classés ;
- **tous les 34 cas avec score Sturgeon ≥0,8 étaient correctement classés** ;
- parmi les 16 cas DIN <5, 14 étaient correctement classés par Sturgeon.

**CNV**

Les profils chromosomiques larges étaient exploitables :

- signature +7/−10 des glioblastomes ;
- codélétion 1p/19q retrouvée dans les oligodendrogliomes.

À cette faible profondeur, les altérations focales telles que les amplifications `EGFR`, `MDM4`, `PDGFRA`, `TERT`, `CDK6` ou les délétions homozygotes `CDKN2A/B` n’étaient pas détectées de manière fiable.

**Flongle**

Six oligodendrogliomes ont été testés individuellement sur Flongle : moyenne d’environ 18 Mb/échantillon ; 5/6 correctement classés par Sturgeon et 1p/19q identifiable dans les six cas.

**Interprétation pour Montpellier**

Cette étude est la première preuve directe forte que de l’ADN FFPE très fragmenté peut fournir suffisamment de CpG informatifs pour une classification SNC par ONT. Elle soutient particulièrement Sturgeon dans une stratégie de faible profondeur. Elle ne définit cependant pas à elle seule le protocole wet-lab optimal, et son espace de classes correspond à la génération des modèles disponible au moment de l’étude.

---

### Feinberg-Gorenshtein et al., NAR Cancer, 2025

**Référence**  
Feinberg-Gorenshtein G, Grunwald A, Vermeulen C, et al. *Brain tumor classification from FFPE samples using nanopore methylation sequencing.* NAR Cancer. 2025;7(4):zcaf038. DOI: `10.1093/narcan/zcaf038`. PMID: `41180011`.

Cette publication est particulièrement utile pour une implémentation pratique car elle décrit un protocole FFPE modifié en détail et teste des faibles quantités d’ADN.

### Pré-analytique FFPE

- fixation dans du formol tamponné à 4 % immédiatement après prélèvement ;
- durée habituelle dans l’étude : 1–5 jours ;
- traitement automatisé : `Tissue-Tek VIP 6`, modèle `VIP 6-E2` ;
- coupes FFPE : 4–5 µm ;
- sélection par le neuropathologiste de régions enrichies en cellules tumorales après H&E.

Cette sélection histologique est un avantage important du FFPE : la fraction tumorale peut être estimée et la zone analysée peut être sélectionnée avant extraction.

### Extraction FFPE

Deux solutions ont été utilisées :

- `QIAamp DNA FFPE Tissue Kit`, Qiagen ;
- `RecoverAll Multi-Sample RNA/DNA Kit`, composante DNA, Invitrogen/Thermo Fisher.

Modification de déparaffinisation :

1. sections provenant de 7–17 lames regroupées dans un tube 1,5 mL ;
2. ajout de 400 µL de tampon de digestion ;
3. 90 °C pendant 3 min ;
4. centrifugation à 14 000 × g pendant 1 min ;
5. courte incubation sur glace ;
6. retrait manuel de l’anneau de paraffine solidifié.

Le protocole évite ainsi le xylène.

### Contrôle de quantité/qualité

- concentration : Qubit Flex + `dsDNA HS Assay Kit` ;
- pureté : NanoDrop, ratio 260/280.

Pour les tissus fresh-frozen de comparaison : `QIAamp DNA Micro Kit`.

### Préparation de librairie

Kit : `SQK-LSK114`, Ligation Sequencing Kit V14.

Modifications FFPE décrites :

- DNA repair/end-prep : **30 min à 20 °C puis 30 min à 65 °C** ;
- purification après repair/end-prep : **180 µL de billes** ;
- purification après ligation/adaptor clean-up : **120 µL de billes** ;
- ligation : **40 min** ;
- élution finale : **12 µL**.

Le protocole a été utilisé sur des blocs conservés à −20 °C jusqu’à 72 mois.

### Quantité d’ADN

Des dilutions de 1 000 ng à 25 ng ont été testées sur trois FFPE déjà classés. Une classification correcte a été obtenue jusqu’à **25 ng d’ADN** dans cette série.

Cela ne signifie pas qu’un seuil analytique de routine de 25 ng est déjà établi. Il s’agit d’une démonstration de faisabilité qu’il faudra vérifier localement avec notre extraction, notre chimie et notre classifieur.

### Pipeline Sturgeon de la publication

```text
POD5
  ↓
Guppy v6.4.6
model: dna_r10.4.1_e8.2_400bps_modbases_5mc_cg_hac_mk1c.cfg
  ↓
minimap2 v2.24
  ↓
T2T-CHM13
  ↓
samtools v1.16.1 — merge/sort/index
  ↓
Sturgeon v0.3.4 — paramètres par défaut
  ↓
classe SNC + calibrated score
```

Guppy est aujourd’hui un composant historique. Une nouvelle implémentation en 2026 doit être construite autour de Dorado puis validée en bridging contre le pipeline publié ou contre une référence orthogonale ; il ne faut pas simplement remplacer le basecaller et déclarer la méthode identique.

### Pipeline nanoDx de la publication

```text
POD5
  ↓
Dorado v0.3.4
model: dna_r10.4.1_e8.2_400bps_hac@v4.2.0
--modified-bases 5mCG_5hmCG
  ↓
minimap2 v2.24
  ↓
hg38
  ↓
modkit v0.1.12 pileup
  ↓
CpG methylation table
  ↓
nanoDx v0.6.2
```

Machine indiquée : Ubuntu 22.04.3, NVIDIA GeForce RTX 3060.

### Cohorte et résultats

- 30 FFPE ;
- 13 patients pédiatriques et 17 adultes ;
- 20 sous-groupes moléculaires ;
- Sturgeon utilisé comme méthode principale car plus performant que nanoDx dans cette série.

Pour Sturgeon :

- 13 cas, ~44 %, score ≥0,95 ; tous concordants avec le diagnostic intégré ;
- 6 cas, 20 %, score 0,90–0,95 ; tous concordants ;
- 7 cas, 23 %, score 0,80–0,90 ; 5 concordants ;
- 4 cas, 13 %, score <0,80 ; trois avaient néanmoins une top class concordante mais le score était sous le seuil.

L’étude illustre donc pourquoi la **classe prédite et le niveau de confiance doivent être conservés séparément** dans la base de validation.

### Effet spécifique du FFPE sur la méthylation

Huit tumeurs avaient un matériel apparié FF et FFPE :

- méthylation moyenne FF : 71,5 % ;
- méthylation moyenne FFPE : 64,5 % ;
- différence significative, p = 0,002 ;
- diminution associée à la durée de fixation.

Les auteurs recommandent de limiter l’exposition au formol à **≤3–4 jours lorsque cela est possible** pour des échantillons destinés à l’analyse de méthylation.

Ils ne retrouvent pas de biais séquence-spécifique majeur suffisant pour empêcher la classification, malgré la diminution globale de méthylation.

### Temps indicatifs rapportés

- extraction FFPE adaptée : ~4 h ;
- préparation de librairie : ~90 min ;
- séquençage nécessaire pour leur workflow : ~120 min ;
- Sturgeon local : ~20 min ;
- environ **7 h entre extraction et classification**, sans compter les 1–2 jours nécessaires en amont pour produire le bloc/coupes FFPE.

### Interprétation pour Montpellier

Cette publication fournit la meilleure base pour développer un SOP FFPE à faible input : sélection histologique, extraction ciblée, adaptation du LSK114 et mesure explicite de l’effet de la fixation. La partie bioinformatique doit en revanche être modernisée avec prudence car les versions Guppy/Dorado/modkit utilisées sont anciennes par rapport à 2026.

---

# 4. Études confirmatoires à intégrer obligatoirement

## 4.1 Kerbs et al., Acta Neuropathologica Communications, 2025

**Référence**  
Kerbs P, Brehm M, Haag D, et al. *Employing nanopore sequencing on FFPE-derived DNA for CNS tumor diagnostics.* Acta Neuropathol Commun. 2025;13:226. DOI: `10.1186/s40478-025-02172-z`. PMID: `41199349`.

Cette étude est particulièrement informative parce qu’elle compare **trois classifieurs sur les mêmes 40 FFPE** avec un EPIC apparié.

### Wet-lab

- extraction principale : `Maxwell RSC FFPE DNA Purification Kit`, Promega, réf. `AS1720` ;
- comparaison sur trois échantillons avec :
  - `QIAamp DNA FFPE Tissue Kit`, Qiagen, réf. `56404` ;
  - protocole non commercial `IARCp` ;
- input librairie : **2–3 µg d’ADN** ;
- kit ONT : `SQK-LSK114` ;
- flow cell : PromethION `FLO-PRO114M` ;
- séquençage principal : 24 h.

Le protocole IARCp produisait parfois davantage d’ADN, mais l’extraction Maxwell donnait le plus grand nombre de CpG couverts dans les comparaisons de séquençage. Cela montre qu’un rendement total supérieur n’est pas nécessairement le meilleur critère pour choisir une extraction destinée à la classification de méthylation.

### Bioinformatique

- Dorado `v0.6.3` ;
- basecall model `v4.3.0` ;
- référence `T2T-CHM13v2.0` ;
- modkit `v0.2.4` ;
- seuil de probabilité : `0.85` ;
- CNV : CNVkit `v0.9.10`, binsize `200,000`.

### Classifieurs comparés

- Rapid-CNS² — Random Forest ;
- nanoDx — réseau neuronal/crossNN dans cette génération ;
- MethyLYZR — Naive Bayes pondéré.

### Résultats à 24 h

- Rapid-CNS² : **39/40** concordants avec EPIC ;
- MethyLYZR : **35/40** ;
- nanoDx : **35/40**.

Définition de classification robuste : premier temps à partir duquel la prédiction reste stable et concordante avec EPIC.

75 % des échantillons étaient robustement classés après :

- Rapid-CNS² : **60 min** ;
- MethyLYZR : **40 min** ;
- nanoDx : **20 min**.

Un cas mal classé par les trois méthodes avait un DIN = 1,6 et une couverture CpG insuffisante.

### Rendement

- 2,99 Gb en moyenne par échantillon ;
- ~0,83× de couverture génomique moyenne ;
- ~10,7 millions de CpG couverts en moyenne.

Cette profondeur est très supérieure à Afflerbach 2024. Les performances des deux études ne doivent donc pas être comparées sans tenir compte du volume de données produit.

---

## 4.2 Hu et al., Acta Neuropathologica Communications, 2026 — extension multicentrique ROBIN

**Référence**  
Hu W, Zhu J, Li H, et al. *Nanopore-based DNA methylation profiling for rapid molecular classification of NOS/NEC CNS tumors: multi-institutional evaluation using FFPE archives and frozen tissues.* Acta Neuropathol Commun. 2026. DOI: `10.1186/s40478-026-02359-y`. PMID: `42380942`.

- 34 tumeurs NOS/NEC consécutives ;
- 16 blocs FFPE de routine ;
- 18 matériels congelés, dont 9 fresh-frozen et 9 ADN pré-extraits ;
- trois centres ;
- PromethION R10.4.1 ;
- pipeline **ROBIN** ;
- objectif : rapport de classification méthylationnelle <24 h.

Résultats :

- classe de méthylation confiante : 28/34, soit 82,4 % ;
- FFPE : **14/16**, soit 87,5 %, avec couverture cible médiane ~0,03× ;
- concordance ONT/EPIC disponible : **11/13**, soit 84,6 % ;
- les CNV ont permis de soutenir deux diagnostics intégrés de glioblastome via la signature 7+/10− lorsque la méthylation n’était pas classable ;
- les SNV étaient récupérables dans les cas à forte couverture, mais pas de manière fiable dans les FFPE à faible couverture.

Cette étude est importante pour la transposition hospitalière car elle teste un pipeline intégré sur des FFPE de routine, mais elle ne remplace pas une qualification analytique locale.

---

# 5. Comparaison wet-lab des études FFPE

| Élément | Afflerbach 2024 | Feinberg-Gorenshtein 2025 | Kerbs 2025 | Hu 2026 |
|---|---|---|---|---|
| FFPE | 40 | 30 + 8 paires FF/FFPE | 40 | 16/34 |
| Sélection histologique ciblée | non détaillée dans l’article principal | oui, zones H&E enrichies | cohorte FFPE archivistique | routine, détails à reprendre du protocole complet |
| Fixation | non détaillée dans texte principal | formol tamponné 4 %, 1–5 j | routine archivistique | routine |
| Extraction principale | Maxwell 16 FFPE Plus LEV / RSC FFPE Plus | QIAamp FFPE ou RecoverAll DNA | Maxwell RSC FFPE AS1720 | à documenter depuis le protocole complet avant SOP |
| Comparaison d’extractions | non | deux kits utilisés | Maxwell vs QIAamp 56404 vs IARCp | non retenu ici |
| Input | non spécifié dans article principal | jusqu’à 25 ng testés avec succès | 2–3 µg | variable |
| Kit ONT | SQK-LSK114 / SQK-NBD114 | SQK-LSK114 | SQK-LSK114 | à confirmer depuis méthodes complètes |
| Plateforme | MinION/GridION ; Flongle test | MinION | PromethION | PromethION |
| Flow cell | FLO-MIN114 ; FLO-FLG114 | chimie R10.4.1 indiquée par le modèle ; SKU non explicitement donné dans le texte principal vérifié | FLO-PRO114M | PromethION R10.4.1 |
| Profondeur | ~0,06× | low-pass ; variable | ~0,83× | FFPE médiane ~0,03× |
| Référence orthogonale | EPIC | diagnostic intégré ± EPIC/autres tests | EPIC | EPIC sur sous-ensemble + diagnostic intégré |

### Ce qui doit être testé localement

Les publications ne permettent pas encore de choisir automatiquement entre Maxwell et QIAamp/RecoverAll pour Montpellier. Le choix doit être basé sur un petit comparatif local mesurant au minimum :

- ADN total récupéré ;
- concentration ;
- pureté ;
- DIN ou autre mesure d’intégrité ;
- longueur des reads après séquençage ;
- rendement par heure ;
- nombre de CpG informatifs pour le classifieur ;
- score de classification ;
- concordance avec EPIC/diagnostic intégré.

Le résultat de Kerbs 2025 indique que le **nombre de CpG utilisables** peut être plus pertinent que le rendement d’ADN seul.

---

# 6. Bioinformatique — composants et versions

## 6.1 Deux objectifs différents : reproductibilité des publications et pipeline 2026

Il faut conserver deux environnements conceptuellement séparés :

### A. Reproductibilité historique

Utiliser les versions exactes publiées pour vérifier que l’on peut reproduire une analyse donnée.

### B. Pipeline de production/qualification 2026

Utiliser une pile moderne, figée et testée, mais démontrer par un bridging qu’elle fournit des résultats comparables ou meilleurs que le pipeline de référence.

Le changement de version de Dorado ou modkit peut modifier les probabilités de modification et donc les features présentées au classifieur. Un changement de logiciel n’est pas neutre dans un test diagnostique.

---

## 6.2 Dorado

Dépôt officiel : `https://github.com/nanoporetech/dorado`

Rôle :

- basecalling ;
- modified-base calling ;
- production de BAM avec tags de modifications MM/ML ;
- possibilité d’alignement selon workflow.

Versions des publications FFPE :

- Feinberg-Gorenshtein, branche nanoDx : Dorado `0.3.4` ;
- Kerbs : Dorado `0.6.3`, modèle `v4.3.0`.

État au 16 septembre 2026 :

- dernière release générale visible : Dorado `2.1.2`, publiée le 26 août 2026 ;
- `1.3.3` est indiquée comme version incluse dans MinKNOW 26.01 LTS et ajoute notamment le support de FLO-PRO114P ;
- l’existence de versions plus récentes ne signifie pas qu’il faille les adopter sans validation analytique.

Pour notre validation, le **nom exact du modèle** Dorado doit être figé, pas seulement la version du binaire.

---

## 6.3 modkit

Dépôt officiel : `https://github.com/nanoporetech/modkit`

Rôle :

- extraction des appels 5mC/5hmC depuis modBAM ;
- `extract` pour données par read ;
- `pileup` pour agrégation par locus ;
- génération bedMethyl ;
- QC des tags et des probabilités.

Versions publiées :

- Feinberg-Gorenshtein : `0.1.12` ;
- Kerbs : `0.2.4` ;
- Rapid-CNS2_nf actuel : container modkit `0.6.4`.

Dernière release vérifiée au 16 septembre 2026 : `0.6.4`.

---

## 6.4 minimap2 et samtools

Dépôts :

- minimap2 : `https://github.com/lh3/minimap2`
- samtools : `https://github.com/samtools/samtools`

Feinberg-Gorenshtein 2025 :

- minimap2 `2.24` ;
- samtools `1.16.1`.

Ces outils ne constituent pas le classifieur. Leur rôle est néanmoins critique parce que les coordonnées des CpG doivent correspondre exactement à la référence attendue par le modèle.

---

# 7. Référence génomique : point critique

Les outils n’utilisent pas tous la même référence par défaut.

| Outil/pipeline | Référence documentée |
|---|---|
| Sturgeon standalone | T2T-CHM13v2 recommandé ; hg38 supporté mais moins testé |
| Feinberg 2025 / Sturgeon | T2T-CHM13 |
| Feinberg 2025 / nanoDx v0.6.2 | hg38 |
| Kerbs 2025 | T2T-CHM13v2.0 |
| Rapid-CNS2_nf actuel | UCSC hg38 |

Le README Sturgeon précise que son travail a été réalisé sur T2T-CHM13v2 et qu’un liftover hg38 entraîne la perte de 26 probes sur 427 680.

**Règle de pipeline : chaque fichier intermédiaire doit porter explicitement son genome build.** Un bedMethyl hg38 ne doit jamais être fourni à une étape CHM13 sans conversion contrôlée.

---

# 8. Workflows publics disponibles

## 8.1 Il n’existe pas de nf-core CNS methylation classifier dédié identifié

`nf-core/nanoseq` est un pipeline Nanopore général. Il n’est pas équivalent à un pipeline de classification SNC par méthylation et n’intègre pas directement Sturgeon/Rapid-CNS²/MethyLYZR comme workflow diagnostique.

Pour notre usage, les solutions directement pertinentes sont :

- Sturgeon : CLI Python + modèle ONNX ;
- nanoDx : workflow historique Snakemake, puis versions incluant crossNN ;
- Rapid-CNS2_nf : **Nextflow** ;
- MethyLYZR : Python ;
- ROBIN : orchestrateur Python temps réel.

---

## 8.2 Rapid-CNS2_nf

Dépôt : `https://github.com/areebapatel/Rapid-CNS2_nf`

Licence : Apache 2.0.

Pipeline Nextflow actuel. Le changelog du dépôt décrit la génération `3.0.0`.

Caractéristiques :

- BAM aligné ou non aligné en entrée ;
- basecalling réalisé en amont par Dorado ou `epi2me-labs/wf-basecalling` ;
- modkit pour méthylation ;
- Rapid-CNS² pour classification ;
- MGMT ;
- CNVpytor et SAVANA pour CNV ;
- Clair3 pour SNV ;
- Sniffles2, Severus et SAVANA pour SV ;
- AnnotSV ;
- rapport HTML.

Containers actuellement documentés :

- `areebapatel/rapid_cns:3.0.2` ;
- modkit `0.6.4` ;
- Clair3 `v2.0.2` ;
- Severus `1.7` ;
- SAVANA `1.3.8`.

Le dépôt contient un workflow spécifique :

- `methylationOnly.nf` ;
- documentation `METHYLATION_ONLY.md`.

Ce workflow est particulièrement intéressant pour notre phase de validation parce qu’il permet d’isoler méthylation/MGMT/classification sans imposer immédiatement tout le pipeline de variants.

Attention : le pipeline complet est développé autour des données d’adaptive sampling Rapid-CNS²/NPHD. Son usage sur un shallow WGS FFPE non ciblé doit être validé et ne doit pas être considéré comme automatiquement équivalent à la publication.

---

## 8.3 ROBIN

Dépôt canonique : `https://github.com/LooseLab/ROBIN`

ROBIN signifie *Rapid nanopOre Brain intraoperatIve classificatioN*. Il s’agit d’un **orchestrateur**, pas d’un classifieur unique.

État du dépôt au 16 septembre 2026 :

- release/model assets `v0.5` ;
- changelog du code : `0.5.1` daté du 30 avril 2026 ;
- usage indiqué : research use only.

Entrée attendue actuellement :

- BAM ONT déjà alignés ;
- HAC suffisant, SUP non requis ;
- calling 5mC/5hmC en contexte CpG ;
- alignement réalisé en temps réel dans MinKNOW ;
- fichiers BAM ≤50 000 reads ; le dépôt recommande une rotation des BAM par nombre de reads et non par durée.

ROBIN ne consomme pas directement les POD5 ou FASTQ dans son workflow temps réel actuel.

### Modèles distribués par ROBIN v0.5

Le manifest `src/robin/resources/assets.json` fournit des artefacts versionnés avec SHA256 :

- `general.zip` — 1 777 245 358 octets — SHA256 `706e043f3b9f248e51e9e57b0a01085efb93ae01d8a52fcff53418c7b39bbe26` ;
- `Capper_et_al_NN_v2.pkl` — 138 089 704 octets — SHA256 `00b05dc5ad2c6f617d95517422ef47181f891d60a0c87fbe91af542d574cbbd5` ;
- `pancan_devel_v5i_NN_v2.pkl` — 203 907 710 octets — SHA256 `4d4193ff98c5bc066a5eaf480924aeecf91d61dd85dbe6ad649419b596236806`.

La présence d’un fichier de modèle avec checksum est très utile pour un dossier de validation : elle permet d’identifier exactement l’artefact utilisé pour chaque analyse.

---

# 9. Classifieurs

## 9.1 Sturgeon

Dépôt : `https://github.com/UMCUGenetics/sturgeon`

Publication : Vermeulen et al., Nature 2023, DOI `10.1038/s41586-023-06615-2`.

Version publiée dans Feinberg FFPE 2025 : `v0.3.4`.

Dernière release publique identifiée : `v0.4.4`.

### Type de modèle

Réseau neuronal préentraîné pour des profils de méthylation extrêmement sparse.

### Référence d’entraînement

Le classifieur repose sur le jeu de référence CNS de Capper et al. 2018. Dans la publication Sturgeon, le modèle est entraîné à partir de **2 801 profils 450K** puis exposé à de très nombreux profils sparse simulant des runs Nanopore de faible profondeur.

### Modèle distribué

`general.zip` contient notamment :

- le modèle ONNX ;
- les classes ;
- les paramètres nécessaires à la calibration.

Le modèle général actuel décrit dans le README couvre **87 classes : 78 tumorales et 9 contrôles**, certaines classes historiques étant fusionnées.

### Faut-il télécharger la cohorte Capper pour classifier nos patients ?

**Non.**

Pour l’inférence, le modèle préentraîné `general.zip` suffit avec les appels CpG au bon format. Le jeu de données complet est nécessaire uniquement pour réentraîner, auditer ou développer un nouveau modèle.

### Prétraitement actuel recommandé

Le README Sturgeon recommande modkit pour les BAM produits par Dorado/Guppy.

Si 5mC et 5hmC sont appelés séparément, Sturgeon recommande de convertir/agréger 5hmC vers 5mC avant classification :

```bash
modkit adjust-mods --convert h m INPUT.bam OUTPUT.bam
```

puis :

```bash
modkit extract full OUTPUT.bam OUTPUT.txt
sturgeon inputtobed -i MODKIT_OUTPUT_DIR -o OUTPUT_DIR -s modkit
```

ou utilisation de `modkit pileup` puis `sturgeon inputtobed -s modkit_pileup`.

Raison : les arrays bisulfite utilisés comme référence d’entraînement ne séparent pas 5mC et 5hmC de la même manière qu’ONT.

### Seuils du modèle général

- score <0,8 : inconclusif ;
- 0,8–0,95 : classification confiante ;
- ≥0,95 : forte confiance.

### Licence

Sturgeon n’est pas distribué sous une licence open source standard pour tous les usages. Le dépôt contient un **Evaluation Software License Agreement**. Pour un usage commercial, clinique ou diagnostique, le texte demande de contacter Cyclomics.

Cette contrainte doit être évaluée avant un déploiement diagnostique de routine.

---

## 9.2 nanoDx : distinguer impérativement les générations

Dépôt : `https://gitlab.com/pesk/nanoDx`

Publication de référence : Kuschel et al. 2023, DOI `10.1111/nan.12856`.

### nanoDx historique

Les versions historiques, dont `v0.6.2` utilisée dans Feinberg-Gorenshtein 2025, reposent sur une stratégie Random Forest avec données de référence de méthylation et intersection des CpG observés.

Dans cette logique, des matrices de référence telles que celles dérivées de Capper sont nécessaires au workflow.

### nanoDx moderne / crossNN

À partir de la génération `v1.0rc2`, nanoDx a intégré crossNN. La release publique `v1.2`, publiée le 7 mai 2025, indique notamment :

- Dorado `0.9.6` ;
- sélection automatique du modèle Dorado ;
- prédictions crossNN sur CPU.

crossNN est un réseau neuronal préentraîné et modifie donc la logique de dépendance aux matrices de référence au moment de l’inférence.

**Règle de documentation : ne jamais écrire simplement “nanoDx”. Toujours conserver `version + moteur` : par exemple `nanoDx v0.6.2 / RF` ou `nanoDx v1.2 / crossNN`.**

---

## 9.3 Rapid-CNS²

Dépôts :

- historique : `https://github.com/areebapatel/RAPID-CNS2`
- actuel Nextflow : `https://github.com/areebapatel/Rapid-CNS2_nf`

Publication initiale : Patel et al., Acta Neuropathologica 2022, DOI `10.1007/s00401-022-02415-6`.

Validation multicentrique : Patel et al., Nature Medicine 2025, DOI `10.1038/s41591-025-03562-5`.

### Type de modèle de classification

Random Forest basé sur des CpG informatifs issus du référentiel CNS/Heidelberg.

Le travail initial a utilisé des données de référence 450K et une sélection de CpG informatifs. Les ressources nécessaires au classifieur sont intégrées au dépôt historique/au workflow ; il n’est pas nécessaire de reconstruire la cohorte Capper à partir de zéro pour lancer le pipeline publié.

### Intérêt pour notre projet

- très bonnes performances dans Kerbs 2025 sur FFPE : 39/40 à 24 h ;
- pipeline Nextflow maintenu ;
- module `methylationOnly.nf` ;
- possibilité d’étendre ensuite vers MGMT, CNV, SNV/SV et fusions.

### Réserve

Le workflow complet actuel est orienté vers le design Rapid-CNS²/adaptive sampling. Pour notre qualification FFPE, il faut tester explicitement le chemin shallow WGS et ne pas extrapoler les performances SNV/SV du pipeline à une couverture FFPE très faible.

---

## 9.4 MethyLYZR

Dépôt : `https://github.com/marasteiger/MethyLYZR`

Publication : Brändl et al., Nature Medicine 2025, DOI `10.1038/s41591-024-03435-3`.

### Type de modèle

Naive Bayes de Bernoulli pondéré, conçu pour les profils de méthylation sparse et le streaming.

### Données d’entraînement

Le modèle CNS a été entraîné sur **2 801 échantillons appartenant à 91 classes CNS/contrôles**, avec 428 201 CpG utilisés comme features dans l’étude. Les jeux publics de méthylation utilisés pour entraînement/évaluation incluent :

- CNS : `GSE90496` et `GSE109379` ;
- métastases : `GSE108576` ;
- sarcomes : `GSE140686`.

### Modèle préentraîné

Le dépôt documente trois fichiers principaux :

- `betas_mean.feather` — centroides/profils moyens de méthylation par classe ;
- `W_RELIEF.feather` — poids de features issus de ReliefF ;
- `class_priors.csv` — probabilités a priori des classes.

Le modèle distribué couvre **91 classes CNS + 3 classes de métastases**. La publication regroupe également les 91 classes CNS dans 44 classes MethyLYZR cliniquement orientées pour certaines analyses.

### Faut-il télécharger GSE90496/GSE109379 pour classifier nos patients ?

**Non**, pas pour l’inférence standard avec le modèle préentraîné. Ces cohortes sont nécessaires pour reproduire l’entraînement ou modifier le modèle.

### Entrée

Le dépôt utilise des fichiers Feather préparés à partir des appels Nanopore, avec scripts fournis pour le prétraitement.

### Ressources disponibles

La publication dépose aussi :

- données Nanopore/PacBio à l’EGA ;
- valeurs de méthylation en Feather sur Zenodo, DOI `10.5281/zenodo.13236096`.

Ces ressources sont utiles pour construire un test de non-régression avant d’introduire nos propres FFPE.

---

## 9.5 crossNN

Publication : Yuan et al., Nature Cancer 2025, DOI `10.1038/s43018-025-00976-5`.

crossNN est un framework de réseau neuronal destiné à la classification de méthylation cross-platform. Il est aujourd’hui intégré dans des workflows nanoDx/ROBIN modernes.

Pour une validation, il faut utiliser le modèle préentraîné exact et le checksum, et ne pas le confondre avec l’ancien Random Forest nanoDx.

---

# 10. Faut-il télécharger une banque complète de méthylation SNC ?

## Pour l’inférence : généralement non

| Classifieur | Modèle préentraîné utilisable | Banque 450K/EPIC complète nécessaire pour l’inférence ? |
|---|---:|---:|
| Sturgeon | oui, `general.zip` | non |
| MethyLYZR | oui, fichiers `model/` | non |
| nanoDx crossNN | oui | non, si utilisation du modèle préentraîné |
| nanoDx RF historique | dépend de matrices de référence | oui / ressources de référence nécessaires |
| Rapid-CNS² RF | ressources du pipeline | pas besoin de reconstruire les données brutes si les ressources distribuées sont utilisées |

## Pour réentraîner ou développer notre propre classifieur : oui

Dans ce cas il faudrait reconstruire et versionner les données de référence, leur taxonomie et leur mapping vers WHO CNS5/CNS6 lorsque celle-ci sera finalisée. Cela n’est **pas** recommandé comme première étape du projet.

La première validation doit utiliser des modèles publiés et figés. Cela sépare proprement la validation analytique du développement de modèle.

---

# 11. Architecture proposée pour la phase pilote Montpellier

Cette architecture est une proposition de qualification, pas encore le SOP final.

```text
FFPE
  ↓
sélection neuropathologique de zone tumorale
  ↓
extraction ADN natif non amplifié
  ↓
Qubit + pureté + intégrité/DIN si disponible
  ↓
SQK-LSK114
  ↓
R10.4.1
  ↓
POD5 conservé comme donnée primaire
  ↓
Dorado version + modèle figés
5mC/5hmC CpG
  ↓
modBAM MM/ML
  ↓
branche T2T-CHM13v2       branche hg38 si exigée par le pipeline
  ↓                         ↓
modkit                    modkit
  ↓                         ↓
Sturgeon                  Rapid-CNS² / autres pipelines hg38
  ├───────────────┐         │
MethyLYZR         │         │
nanoDx/crossNN    │         │
                  └─────────┘
                        ↓
            comparaison inter-classifieurs
                        ↓
          EPIC/Heidelberg + diagnostic intégré
```

ROBIN doit être testé **en parallèle** comme pipeline intégré plutôt que comme substitut opaque aux analyses standalone.

---

# 12. Jeu pilote de qualification

Le meilleur jeu pilote n’est pas nécessairement une grande cohorte. Il doit être informatif analytiquement.

À privilégier :

- FFPE avec résultat EPIC existant ;
- représentation de plusieurs classes tumorales ;
- distribution de DIN/qualité ;
- fixation connue lorsque possible ;
- différents âges de blocs ;
- cas avec faible quantité d’ADN ;
- quelques paires congelé/FFPE du même prélèvement si disponibles ;
- cas connus pour 1p/19q et +7/−10 afin de vérifier aussi les CNV chromosomiques.

Variables minimales à enregistrer :

```text
sample_id
block_id
fixation_duration_hours_or_days
block_age_months
section_thickness_um
number_of_sections
tumor_fraction_estimate
macrodissection_or_marked_area
extraction_kit
extraction_lot
dna_ng
dna_concentration_ng_ul
A260_280
DIN
library_kit
library_kit_lot
barcode_kit
flowcell_type
flowcell_id
active_pores_start
sequencer
minknow_version
dorado_version
dorado_model
modified_base_model
reference_build
modkit_version
classifier
classifier_version
model_artifact
model_sha256
sequencing_minutes_at_prediction
bases_at_prediction
mapped_bases
CpG_count_used
classifier_top_class
classifier_score
classifier_top3
EPIC_class
EPIC_score
integrated_diagnosis
concordance_status
CNV_1p19q
CNV_7plus_10minus
failure_reason
```

---

# 13. QC à définir avant usage prospectif

Les seuils définitifs doivent être dérivés de la qualification locale. Les dimensions à suivre sont néanmoins déjà claires :

### Pré-analytique

- durée de fixation ;
- âge du bloc ;
- fraction tumorale ;
- quantité d’ADN ;
- DIN ;
- pureté.

### Run ONT

- pores actifs ;
- yield ;
- reads ;
- N50 ;
- taux d’alignement ;
- bases alignées ;
- couverture ;
- CpG informatifs obtenus au moment de la prédiction.

### Méthylation

- taux global 5mC ;
- distribution des probabilités ;
- nombre de loci correspondant aux features du classifieur ;
- stabilité du résultat au cours du temps.

### Classification

- top class ;
- score calibré/postérieur ;
- top 3 ;
- niveau hiérarchique de concordance ;
- concordance avec EPIC ;
- concordance avec diagnostic intégré ;
- classifiable/non classifiable selon seuil prédéfini.

### Versioning obligatoire

Tout rapport analytique doit permettre de reconstituer :

```text
software name
software version
Git commit/tag si pertinent
container digest
reference genome + checksum
Dorado model exact
modified-base model exact
classifier version
model filename
model SHA256
parameters
```

---

# 14. Points qui ne doivent pas encore être figés sans test local ou retour Toulouse

1. **Kit d’extraction FFPE définitif** : Maxwell et QIAamp/RecoverAll ont tous des données publiées ; comparaison locale souhaitable.
2. **Input minimal accepté en routine** : 25 ng est une faisabilité publiée, pas encore un seuil validé à Montpellier.
3. **MinION versus PromethION** : dépend du throughput attendu, multiplexage, nombre de dossiers et besoin de CNV/SNV complémentaires.
4. **Dorado version et modèle 2026** : une version moderne doit être sélectionnée puis figée après bridging.
5. **5mC seul versus 5mC+5hmC agrégé** : doit être cohérent avec le classifieur et documenté.
6. **classifieur primaire** : Sturgeon dispose de données FFPE fortes à très faible profondeur ; Rapid-CNS² a les meilleurs résultats dans Kerbs 2025 à profondeur plus élevée ; une comparaison locale est préférable.
7. **classifieurs secondaires** : MethyLYZR et crossNN/nanoDx sont utiles comme analyses indépendantes de concordance.
8. **seuil de reporting clinique** : ne doit pas être dérivé uniquement du seuil publié ; il doit être intégré à la qualification et au cadre qualité du laboratoire.
9. **licences** : en particulier Sturgeon et les composants Research Use Only doivent être clarifiés avant routine diagnostique.

---

# 15. Repositories et ressources à archiver dans le dossier de validation

| Ressource | URL | Usage |
|---|---|---|
| Sturgeon | https://github.com/UMCUGenetics/sturgeon | classifieur NN CNS |
| nanoDx | https://gitlab.com/pesk/nanoDx | RF historique / crossNN moderne |
| Rapid-CNS2 historique | https://github.com/areebapatel/RAPID-CNS2 | ressources historiques/classifieur |
| Rapid-CNS2 Nextflow | https://github.com/areebapatel/Rapid-CNS2_nf | pipeline actuel |
| MethyLYZR | https://github.com/marasteiger/MethyLYZR | classifieur Naive Bayes |
| ROBIN | https://github.com/LooseLab/ROBIN | orchestration temps réel |
| Dorado | https://github.com/nanoporetech/dorado | basecalling/modified bases |
| modkit | https://github.com/nanoporetech/modkit | extraction/QC des modifications |
| minimap2 | https://github.com/lh3/minimap2 | alignement |
| samtools | https://github.com/samtools/samtools | BAM processing |

Pour chaque dépôt utilisé en validation, conserver localement :

- release/tag ;
- commit SHA ;
- fichier d’environnement ou container ;
- licence ;
- README correspondant à la release ;
- modèle(s) et checksum(s).

---

# 16. Tableau comparatif des classifieurs à benchmarker

| Outil | Famille ML | Modèle fourni | Réentraînement patient par patient | Référence d’entraînement principale | FFPE direct | Point fort | Limite principale |
|---|---|---:|---:|---|---:|---|---|
| Sturgeon | réseau neuronal | oui, ONNX | non | Capper 2018, 2 801 profils CNS + simulations sparse | oui | très adapté au low-pass ; très bonnes données FFPE | licence clinique + taxonomie du modèle à versionner |
| Rapid-CNS² | Random Forest | ressources pipeline | non en routine du workflow | Heidelberg/Capper, CpG informatifs | oui | 39/40 dans Kerbs 2025 ; workflow Nextflow | workflow complet lié à adaptive sampling ; référence hg38 actuelle |
| MethyLYZR | Naive Bayes pondéré | oui | non | 2 801 CNS + extensions métastases | oui | très rapide, sparse, faible calcul | mapping 91 → classes MZ à interpréter correctement |
| nanoDx v0.6.2 RF | Random Forest | référence/matrices | oui/logique RF historique | Capper/Heidelberg | oui | historique bien documenté | plus lent et moins performant dans Afflerbach/Feinberg |
| nanoDx moderne / crossNN | réseau neuronal | oui | non | cross-platform reference methylation | oui dans Kerbs 2025 | rapide ; intégré à ROBIN/nanoDx moderne | ne pas confondre avec le nanoDx RF historique |

---

# 17. Choix méthodologique recommandé pour la première qualification

Pour éviter de dépendre d’un seul logiciel, la première série devrait être analysée avec **au moins trois approches de familles différentes** :

1. **Sturgeon** — réseau neuronal, principal candidat pour faible profondeur ;
2. **Rapid-CNS²** — Random Forest, excellente performance FFPE dans Kerbs 2025 ;
3. **MethyLYZR** — Naive Bayes, classifieur indépendant et rapide.

nanoDx/crossNN peut être ajouté comme quatrième analyse et ROBIN comme pipeline intégré parallèle.

La comparaison doit être faite sans réentraîner les modèles sur nos cas de validation. Toute adaptation locale de modèle doit constituer une phase distincte avec séparation stricte entraînement/validation.

---

# 18. Références principales

1. Afflerbach AK, Albers A, Appelt A, et al. Nanopore sequencing from formalin-fixed paraffin-embedded specimens for copy-number profiling and methylation-based CNS tumor classification. *Acta Neuropathol.* 2024;147:74. DOI: `10.1007/s00401-024-02731-z`.
2. Feinberg-Gorenshtein G, Grunwald A, Vermeulen C, et al. Brain tumor classification from FFPE samples using nanopore methylation sequencing. *NAR Cancer.* 2025;7(4):zcaf038. DOI: `10.1093/narcan/zcaf038`.
3. Kerbs P, Brehm M, Haag D, et al. Employing nanopore sequencing on FFPE-derived DNA for CNS tumor diagnostics. *Acta Neuropathol Commun.* 2025;13:226. DOI: `10.1186/s40478-025-02172-z`.
4. Hu W, Zhu J, Li H, et al. Nanopore-based DNA methylation profiling for rapid molecular classification of NOS/NEC CNS tumors: multi-institutional evaluation using FFPE archives and frozen tissues. *Acta Neuropathol Commun.* 2026. DOI: `10.1186/s40478-026-02359-y`.
5. Capper D, Jones DTW, Sill M, et al. DNA methylation-based classification of central nervous system tumours. *Nature.* 2018;555:469–474. DOI: `10.1038/nature26000`.
6. Vermeulen C, Pagès-Gallego M, Kester L, et al. Ultra-fast deep-learned CNS tumour classification during surgery. *Nature.* 2023;622:842–849. DOI: `10.1038/s41586-023-06615-2`.
7. Kuschel LP, Hench J, Frank S, et al. Robust methylation-based classification of brain tumours using nanopore sequencing. *Neuropathol Appl Neurobiol.* 2023;49:e12856. DOI: `10.1111/nan.12856`.
8. Patel A, et al. Rapid-CNS2: rapid comprehensive adaptive nanopore-sequencing of CNS tumors, a proof-of-concept study. *Acta Neuropathol.* 2022;143:609–612. DOI: `10.1007/s00401-022-02415-6`.
9. Patel A, Göbel K, Ille S, et al. Prospective, multicenter validation of a platform for rapid molecular profiling of central nervous system tumors. *Nat Med.* 2025;31:1567–1577. DOI: `10.1038/s41591-025-03562-5`.
10. Brändl B, Steiger M, Kubelt C, et al. Rapid brain tumor classification from sparse epigenomic data. *Nat Med.* 2025;31:840–848. DOI: `10.1038/s41591-024-03435-3`.
11. Yuan D, et al. crossNN is an explainable framework for cross-platform DNA methylation-based classification of tumors. *Nat Cancer.* 2025;6:1283–1294. DOI: `10.1038/s43018-025-00976-5`.
12. Deacon S, et al. ROBIN: A unified nanopore-based assay integrating intraoperative methylome classification and next-day comprehensive profiling for ultra-rapid tumor diagnosis. *Neuro-Oncology.* 2025;27:2035–2046. DOI: `10.1093/neuonc/noaf103`.

Le fichier `ffpe_nanopore_references.bib` du repository contient une bibliographie BibTeX ciblée correspondant à cette revue.
