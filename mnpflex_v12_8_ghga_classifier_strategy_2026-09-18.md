# Heidelberg CNS classifier v12.8, MNP-Flex et dataset GHGA — stratégie pour le projet ONT

**Date de mise à jour : 18 septembre 2026**  
**Projet :** long-read / Oxford Nanopore pour la classification moléculaire des tumeurs du SNC  
**Statut :** mise à jour technique à intégrer à la stratégie de qualification locale

## 1. Question pratique

Le jeu de données GHGA associé à la publication du Heidelberg CNS Tumor Methylation Classifier v12.8 est-il nécessaire pour utiliser le classifieur sur nos propres échantillons, notamment des données Oxford Nanopore ?

**Réponse : non pour l’inférence standard.**

Le dataset GHGA `GHGAD19671623325581` correspond au jeu de référence utilisé pour le développement/entraînement du classifieur v12.8. Il devient pertinent si l’objectif est de reproduire l’entraînement, de développer un nouveau modèle, d’auditer en profondeur la construction du classifieur ou d’entraîner un classifieur sparse/ONT dérivé de la taxonomie v12.8. Il n’est pas nécessaire pour appliquer un modèle ou un service préentraîné aux échantillons du projet.

Cette distinction est importante pour le projet Montpellier : la première phase doit rester une **validation externe de classifieurs publiés et figés**, sans réentraînement sur la cohorte locale.

---

# 2. Heidelberg CNS Tumor Methylation Classifier v12.8

## Publication

Sill M, Schrimpf D, Patel A, et al. **Advancing CNS tumor diagnostics with expanded DNA methylation-based classification.** *Cancer Cell*. 2026;44(2):340-354.e2.  
DOI : `10.1016/j.ccell.2025.11.002`  
Publication électronique : 4 décembre 2025 ; numéro de revue : 9 février 2026.

Article :  
`https://www.cell.com/cancer-cell/fulltext/S1535-6108(25)00495-7`

## Caractéristiques principales

Le classifieur v12.8 :

- est entraîné sur **7 495 profils de méthylation** ;
- utilise une approche **Random Forest** ;
- étend la taxonomie du précédent v11, qui couvrait 91 classes, à **184 sous-classes** ;
- produit une sortie hiérarchique : **subclass → class → family → superfamily** ;
- atteint environ **95 % d’accuracy au niveau subclass** dans la validation décrite par les auteurs ;
- utilise des scores probabilistes calibrés ;
- constitue la taxonomie de référence moderne à considérer pour le projet.

La version actuelle d’Epignostix documente :

- **184 subclasses** ;
- **142 classes** ;
- **75 families** ;
- cohorte de référence de **7 495 profils** ;
- classification, QC, CNV et statut MGMT selon le produit utilisé.

Le seuil de score ≥0,9 est documenté par Epignostix comme seuil de classification positive dans l’implémentation actuelle du classifieur. Pour notre étude locale, ce seuil doit être conservé comme référence publiée mais ne doit pas être transformé sans qualification en seuil diagnostique local universel.

---

# 3. Dataset GHGA `GHGAD19671623325581`

Portail :  
`https://data.ghga.de/dataset/GHGAD19671623325581`

Le portail GHGA décrit :

- **7 495 expériences** ;
- **7 495 échantillons** ;
- **14 990 fichiers** ;
- environ **131,01 GiB** ;
- données de méthylation issues d’arrays ;
- accès contrôlé.

## Faut-il demander ce dataset maintenant ?

### Non pour la phase de validation externe

Il n’est pas nécessaire pour :

- utiliser le classifieur Heidelberg/Epignostix v12.8 comme service ou installation licenciée ;
- utiliser MNP-Flex ;
- utiliser Sturgeon avec son modèle préentraîné ;
- utiliser MethyLYZR avec ses artefacts de modèle préentraînés ;
- utiliser crossNN/nanoDx avec un modèle préentraîné ;
- exécuter le workflow Rapid-CNS² avec ses ressources distribuées ;
- comparer plusieurs classifieurs sur nos BAM/modBAM ONT.

### Oui ou potentiellement utile dans une phase méthodologique distincte

Le dataset devient pertinent si nous voulons :

1. reproduire l’entraînement de v12.8 ;
2. entraîner un modèle local ou expérimental sur les 184 sous-classes ;
3. tester de nouvelles familles de modèles ;
4. simuler systématiquement différents niveaux de sparsité/couverture ONT ;
5. développer un classifieur explicitement optimisé pour shallow ONT ou FFPE ;
6. étudier l’effet de la sélection de CpG, du bruit et du missingness ;
7. auditer en détail la taxonomie et les distributions du jeu d’entraînement.

Cette phase serait un projet de développement ML distinct de la validation analytique initiale et nécessiterait une séparation stricte entraînement/validation/test.

**Décision actuelle : ne pas faire du téléchargement GHGA un prérequis du pilote.**

---

# 4. MNP-Flex : accès à la granularité v12.8 depuis des données de séquençage

MNP-Flex est particulièrement important pour le projet car il permet d’exploiter la taxonomie moderne de **184 catégories/sous-classes** avec des profils de méthylation provenant de plusieurs plateformes, notamment du séquençage Nanopore.

Publication/validation principale à considérer avec Rapid-CNS² :

Patel A, Göbel K, Ille S, et al. **Prospective, multicenter validation of a platform for rapid molecular profiling of central nervous system tumors.** *Nature Medicine*. 2025;31:1567–1577.  
DOI : `10.1038/s41591-025-03562-5`.

La publication décrit MNP-Flex comme un classifieur platform-agnostic destiné à fournir la granularité de la taxonomie MNP/Heidelberg moderne à partir de données issues de technologies différentes.

## Modèle

MNP-Flex repose sur un modèle **gradient-boosted** entraîné sur les **7 495 profils** de la taxonomie v12.x/v12.8 et sur plusieurs niveaux de sparsité.

La validation publiée/rapportée comprend des données provenant de :

- methylation arrays ;
- Nanopore shallow WGS ;
- Nanopore deep WGS ;
- tissus cryoconservés ;
- FFPE ;
- données Rapid-CNS² intraopératoires et post-hoc ;
- WGBS ;
- panels de méthylation.

L’objectif est précisément de réduire la dépendance à la plateforme et de permettre la classification de profils incomplets ou sparse.

## Conséquence pour notre projet

MNP-Flex permet de viser une classification compatible avec la granularité v12.8 **sans reconstruire localement le jeu d’entraînement de 7 495 patients**.

Il doit donc être ajouté au benchmark comme composant majeur, sous réserve de documenter précisément :

- la version du service/modèle ;
- le format exact d’entrée ;
- les règles de score ;
- les conditions de licence et de traitement des données ;
- la possibilité d’usage RUO versus diagnostic ;
- la politique de versioning du modèle ;
- la conservation des résultats et des métadonnées nécessaires à la reproductibilité.

---

# 5. Intégration MNP-Flex dans Rapid-CNS² Nextflow

Dépôt :  
`https://github.com/areebapatel/Rapid-CNS2_nf`

Le workflow Rapid-CNS² actuel intègre explicitement MNP-Flex.

Le pipeline :

1. prépare le profil de méthylation attendu par MNP-Flex ;
2. génère notamment :

```text
mnpflex/<sample_id>.MNPFlex.input.bed
```

3. permet un upload manuel sur la plateforme Epignostix ;
4. permet, si un compte et les credentials sont disponibles, une soumission par API ;
5. peut récupérer les prédictions et les intégrer au rapport Rapid-CNS².

Le README courant documente notamment :

```text
--mnpFlex
--mnpFlexUpload
--mnpFlexApi
--mnpFlexWorkflowId
```

et produit, selon le mode d’exécution, des sorties telles que :

```text
<sample_id>_mnpflex_predictions.tsv
<sample_id>_bundle_summary.json
<sample_id>_qc_*.json
```

Cette intégration est importante : **Rapid-CNS² n’est plus seulement un pipeline associé à son ancien classifieur 91 classes ; il peut aussi servir de chaîne de préparation et d’orchestration vers MNP-Flex/v12.8.**

## Point de sécurité informatique

Le README de Rapid-CNS² recommande de fournir les identifiants Epignostix via variables d’environnement et de ne pas les écrire dans `nextflow.config` ni dans des fichiers de configuration copiés dans le répertoire de travail.

Pour une implémentation hospitalière, toute soumission externe de données doit être revue avec les règles locales de sécurité, DPO, qualité et gouvernance des données avant utilisation sur des données patients.

---

# 6. Epignostix v12.8

Site :  
`https://epignostix.com/products/cns-tumour-classifier/`

État vérifié en septembre 2026 :

- CNS Tumour Methylation Classifier **v12.8** ;
- 184 subclasses ;
- 142 classes ;
- 75 families ;
- référence de 7 495 profils ;
- support annoncé des données issues d’arrays **et de sequencing** dans l’offre actuelle ;
- plateforme RUO disponible pour la recherche ;
- possibilité d’installation locale sous licence pour les usages correspondants.

Le site indique que le portefeuille RUO est disponible gratuitement pour la recherche académique/scientifique, tandis que l’installation locale et les usages de routine relèvent d’une logique de licence.

**À vérifier avant le gel du SOP :** conditions contractuelles exactes, traitement des données, version du modèle, compatibilité ONT/MNP-Flex, archivage des résultats et usage diagnostique.

---

# 7. Position des classifieurs dans notre benchmark

| Solution | Famille ML | Taxonomie / granularité | ONT | Modèle/référence requis pour inférence | Rôle proposé |
|---|---|---|---:|---|---|
| **MNP-Flex / Epignostix v12.8** | gradient boosting / service platform-agnostic | **184 subclasses** compatibles v12.8 | oui | service/modèle préentraîné ; pas besoin du GHGA brut | **référence moderne de haute granularité** |
| **Sturgeon** | réseau neuronal | modèle général actuel ≈87 classes | oui | `general.zip` préentraîné | faible profondeur, streaming, très pertinent FFPE |
| **MethyLYZR** | Naive Bayes pondéré | 91 CNS + 3 métastases dans le modèle distribué | oui | fichiers `model/` préentraînés | comparateur sparse indépendant |
| **crossNN / nanoDx moderne** | réseau neuronal cross-platform | dépend du modèle distribué, historiquement v11b4/CNS | oui | modèle préentraîné | comparateur neuronal indépendant |
| **Rapid-CNS² RF** | Random Forest | génération historique ≈91 classes | oui | ressources du pipeline | classification rapide + pipeline moléculaire intégré |
| **ROBIN** | orchestration | dépend des classifieurs embarqués | oui | assets versionnés | pipeline temps réel / orchestration, pas classifieur unique |

## Conséquence méthodologique

Il ne faut plus opposer simplement « Rapid-CNS² versus MNP-Flex ». Dans la version actuelle du workflow :

- Rapid-CNS² peut produire sa propre classification ;
- Rapid-CNS² peut aussi préparer/soumettre les données à MNP-Flex ;
- les deux sorties doivent être conservées séparément dans la base de validation.

---

# 8. Architecture révisée pour le pilote Montpellier

```text
ADN tumoral natif
    ↓
ONT R10.4.1
    ↓
POD5 conservé
    ↓
Dorado + modèle modified-base figé
    ↓
modBAM MM/ML
    ↓
modkit / preprocessing spécifique à chaque branche
    │
    ├── Sturgeon
    │
    ├── MethyLYZR
    │
    ├── nanoDx / crossNN
    │
    ├── Rapid-CNS² classifier
    │
    └── Rapid-CNS² → MNPFlex.input.bed
                       ↓
                MNP-Flex / Epignostix v12.8
                       ↓
                 184-subclass output

Toutes les sorties
    ↓
comparaison inter-classifieurs
    ↓
référence orthogonale : EPIC/Heidelberg + diagnostic intégré
```

ROBIN peut être exécuté en parallèle comme pipeline temps réel intégré, avec conservation de ses versions et assets exacts.

---

# 9. Benchmark recommandé

Pour la phase de qualification, conserver **au moins quatre analyses indépendantes** lorsque les formats permettent de les exécuter sur les mêmes données :

1. **MNP-Flex / Epignostix v12.8** — pour la granularité actuelle à 184 sous-classes ;
2. **Sturgeon** — pour les performances low-pass et la vitesse ;
3. **MethyLYZR** — pour une famille statistique indépendante et adaptée aux données sparse ;
4. **crossNN/nanoDx moderne** — pour une seconde approche neuronale cross-platform.

À côté de ces classifieurs :

- **Rapid-CNS²** doit être évalué comme pipeline intégré et conserver sa propre sortie de classification ;
- **ROBIN** doit être évalué comme orchestrateur temps réel, sans le considérer comme un classifieur unique.

## Analyses à enregistrer pour chaque modèle

```text
classifier_name
classifier_version
model_version
model_artifact
model_sha256_if_available
training_taxonomy_version
reference_genome
preprocessing_version
CpG_count_input
CpG_count_used
prediction_subclass
prediction_class
prediction_family
prediction_superfamily
raw_score
calibrated_score_if_available
classification_threshold
conclusive_status
runtime_seconds
sequencing_minutes_at_prediction
bases_available_at_prediction
concordance_with_reference
```

La comparaison principale doit être réalisée **sans tuning ni calibration à partir des diagnostics de la cohorte locale**.

---

# 10. Place du dataset GHGA dans la roadmap

## Phase 1 — maintenant

**Ne pas télécharger GHGA comme prérequis.**

Objectifs :

- installer/tester les classifieurs préentraînés ;
- préparer un petit jeu de non-régression public ;
- construire la chaîne modBAM → formats classifieurs ;
- tester MNP-Flex via Rapid-CNS² ;
- figer versions, paramètres, artefacts et checksums ;
- comparer ensuite les modèles sur les échantillons pilotes locaux.

## Phase 2 — recherche méthodologique optionnelle

Envisager une demande GHGA si le projet évolue vers :

- développement d’un classifieur ONT sparse v12.8 propre ;
- benchmark de familles ML/IA sur les 184 classes ;
- simulations de downsampling/sparsité ;
- adaptation spécifique aux FFPE ;
- étude de robustesse aux changements de basecaller / modbase model ;
- développement d’une solution entièrement locale sans service externe.

Cette phase doit être considérée comme **un projet de développement de modèle séparé** et ne doit pas retarder le pilote clinique/analytique.

---

# 11. Décisions pour le projet

1. **Le dataset `GHGAD19671623325581` n’est pas requis pour commencer.**
2. **Ne pas faire de l’obtention du GHGA un jalon bloquant de la qualification ONT.**
3. **Ajouter MNP-Flex/Epignostix v12.8 au benchmark principal.**
4. **Conserver Sturgeon, MethyLYZR et crossNN/nanoDx comme analyses indépendantes.**
5. **Traiter Rapid-CNS² comme pipeline intégré ET conserver séparément sa classification propre et sa branche MNP-Flex.**
6. **Documenter explicitement la taxonomie de chaque modèle**, car les anciens classifieurs n’ont pas la granularité v12.8.
7. **Ne pas comparer directement les scores numériques entre modèles** : leurs probabilités, calibrations et seuils ne sont pas interchangeables.
8. **Ne pas réentraîner sur la cohorte locale pour l’analyse principale.**
9. **Prévoir le GHGA uniquement pour une phase ML secondaire** si un développement de classifieur local devient un objectif scientifique.
10. **Vérifier licence, RUO/diagnostic, gouvernance des données et possibilité d’installation locale** avant toute routine clinique.

---

# 12. Modifications à répercuter dans les autres documents du dépôt

Les documents existants restent valides mais doivent être lus avec cette mise à jour :

- `ffpe_nanopore_cns_workflow_2026-09-16.md` : ajouter MNP-Flex/v12.8 comme branche majeure du benchmark et préciser que Rapid-CNS² prépare aujourd’hui directement l’input MNP-Flex ;
- `methodology_AAP_JC2026_2026-09-08.md` : la mention « MNP-Flex, sous réserve de son accessibilité » doit être réévaluée, car l’accès web/service et l’intégration Rapid-CNS² sont maintenant documentés ;
- `README.md` : considérer MNP-Flex/v12.8 comme composant central de la stratégie de classification moderne ;
- `ffpe_nanopore_references.bib` / `references.bib` : inclure la publication Cancer Cell v12.8 si elle n’est pas déjà présente.

Cette note sert de référence technique datée jusqu’à intégration complète dans ces documents.

---

# 13. Références et ressources

## Heidelberg v12.8

Sill M, Schrimpf D, Patel A, et al. Advancing CNS tumor diagnostics with expanded DNA methylation-based classification. *Cancer Cell*. 2026;44(2):340-354.e2. DOI: `10.1016/j.ccell.2025.11.002`.

- Article : `https://www.cell.com/cancer-cell/fulltext/S1535-6108(25)00495-7`
- PubMed : `https://pubmed.ncbi.nlm.nih.gov/41349541/`
- Epignostix : `https://epignostix.com/products/cns-tumour-classifier/`

## Dataset GHGA

- `https://data.ghga.de/dataset/GHGAD19671623325581`

## Rapid-CNS² / MNP-Flex

Patel A, Göbel K, Ille S, et al. Prospective, multicenter validation of a platform for rapid molecular profiling of central nervous system tumors. *Nature Medicine*. 2025;31:1567–1577. DOI: `10.1038/s41591-025-03562-5`.

- Rapid-CNS² Nextflow : `https://github.com/areebapatel/Rapid-CNS2_nf`
- MNP-Flex abstract/platform-agnostic validation : `https://academic.oup.com/neuro-oncology/article/26/Supplement_5/v21/7824893`

## Autres classifieurs du benchmark

- Sturgeon : `https://github.com/UMCUGenetics/sturgeon`
- MethyLYZR : `https://github.com/marasteiger/MethyLYZR`
- nanoDx : `https://gitlab.com/pesk/nanoDx`
- ROBIN : `https://github.com/LooseLab/ROBIN`
