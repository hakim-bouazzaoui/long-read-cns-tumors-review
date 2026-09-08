# Projet JC 2026 — validation du séquençage nanopore sur tumeurs du SNC

**Version :** v0.1 — 2026-09-08  
**Statut :** premier manuscrit scientifique de travail  
**AAP :** Jeunes Chercheurs Tremplin 2026 — CHU Montpellier  
**Références de travail :** `references.bib`, `references.md`, `clinical_impact_perioperative.md`, `methodology_AAP_JC2026_2026-09-08.md`, `montpellier_landscape_2026-09-07.md`, `budget_previsionnel.md`, `budget_previsionnel_AAP_JC2026.xlsx`, `TO_DO.md`

> **IMPORTANT — VERSION NON FINALISÉE**  
> Les éléments signalés `TO DO` doivent être complétés avant soumission. Ils concernent principalement le recrutement réel, le calcul d’effectif définitif avec l’URCE, la qualification réglementaire, les coûts institutionnels et la composition de l’équipe.

---

## 1. Titre provisoire

**Validation prospective du séquençage nanopore sur tissu tumoral congelé pour la classification moléculaire des tumeurs du système nerveux central**

> **TO DO — TITRE / ACRONYME**  
> Définir un acronyme court, mémorisable et non artificiel après stabilisation du périmètre final.

---

## 2. Résumé scientifique

Le diagnostic des tumeurs du système nerveux central (SNC) repose aujourd’hui sur une approche intégrée associant morphologie, immunohistochimie et analyses moléculaires. Au CHU de Montpellier, ce diagnostic de référence est établi en routine sur tissu fixé et inclus en paraffine (FFPE). Les approches de classification fondées sur la méthylation de l’ADN ont profondément modifié la nosologie des tumeurs du SNC et sont désormais intégrées aux recommandations diagnostiques contemporaines. Toutefois, les méthodes de référence reposent encore le plus souvent sur des circuits analytiques différés.

Le séquençage Oxford Nanopore permet l’analyse directe de l’ADN natif, y compris de sa méthylation, et plusieurs classifieurs pré-entraînés ont récemment démontré qu’une classification fiable des tumeurs du SNC pouvait être obtenue à partir de profils de méthylation très parcimonieux. Parmi les approches les mieux documentées figurent notamment crossNN/nanoDx, Sturgeon, MethyLYZR et MNP-Flex. Ces outils diffèrent par leur architecture, leurs jeux de référence et leurs stratégies de classification, mais permettent tous d’envisager une classification moléculaire rapide à partir de données nanopore.

L’objectif principal de ce projet est d’évaluer, dans les conditions réelles de prise en charge au CHU de Montpellier, si le séquençage nanopore d’un prélèvement tumoral congelé provenant de la même intervention permet d’obtenir une classification diagnostique concordante avec le diagnostic intégré final établi en routine sur FFPE.

Il s’agira d’une étude prospective, monocentrique, comparative et appariée de performance diagnostique. Le résultat nanopore constituera le test index et le diagnostic intégré final sur FFPE le standard de référence. La cohorte principale sera analysée en multiplexage de six échantillons par flow cell afin d’évaluer la performance diagnostique dans une configuration économiquement soutenable. Une sous-cohorte prédéfinie sera séquencée en singleplex ou en faible multiplexage afin de caractériser la cinétique réelle d’acquisition de l’information moléculaire et d’estimer la transposabilité future du workflow à une utilisation peropératoire.

Les mêmes données nanopore seront analysées par plusieurs classifieurs publiés et pré-entraînés. Aucun modèle ne sera entraîné ou optimisé sur la cohorte locale pour l’analyse principale. Le critère principal sera le taux de diagnostics nanopore concordants avec le diagnostic intégré de référence dans une approche en intention-to-diagnose, les échecs techniques et résultats non conclusifs étant intégrés comme échecs du workflow. Les analyses secondaires porteront sur la performance propre à chaque classifieur, leur concordance, les causes d’échec, l’influence des caractéristiques du prélèvement, ainsi que le temps et la quantité minimale de données nécessaires à l’obtention d’une classification correcte et stable.

Le projet s’appuie sur une infrastructure déjà disponible au CHU Montpellier : séquenceurs nanopore, expertise en biologie moléculaire, expérience locale du long-read et compétences bioinformatiques au PMMG/MOBIDIC. Une expérience scientifique directe existe également dans le domaine des tumeurs du SNC, avec la participation d’équipes montpelliéraines à une étude récente de classification nanopore des médulloblastomes.

Si la performance diagnostique, le taux de succès technique et la cinétique observée sont compatibles avec les objectifs prédéfinis, cette étude constituera le socle méthodologique d’une seconde phase prospective évaluant le workflow en situation peropératoire avec les équipes de neuropathologie et de neurochirurgie.

---

## 3. Contexte scientifique et médical

### 3.1. Une classification désormais intégrée et moléculaire

La classification des tumeurs du SNC a évolué d’une approche essentiellement morphologique vers une nosologie intégrée combinant histologie et caractéristiques moléculaires. La classification par méthylation de l’ADN est devenue un outil diagnostique majeur, notamment depuis les travaux fondateurs de Capper et al., puis son intégration progressive dans les pratiques diagnostiques et les recommandations de l’OMS, de l’EANO et de cIMPACT-NOW.

Cette approche peut confirmer un diagnostic, résoudre des cas morphologiquement ambigus, identifier des entités non reconnues initialement et fournir des informations complémentaires par l’analyse des profils de nombre de copies. Son intérêt est particulièrement marqué dans les tumeurs rares ou difficiles à classifier.

Dans le circuit diagnostique actuel du CHU Montpellier, l’analyse de référence repose sur le matériel FFPE et associe anatomopathologie, immunohistochimie et analyses moléculaires ciblées ou plus larges selon le contexte clinique.

### 3.2. Limites du circuit diagnostique conventionnel

Le diagnostic intégré conventionnel est robuste mais nécessite plusieurs étapes successives : fixation, inclusion, préparation histologique, analyses immunohistochimiques puis analyses moléculaires complémentaires. Ce circuit est adapté au diagnostic final mais n’est pas conçu pour produire une information moléculaire à très court délai.

Cette temporalité limite l’utilisation des informations moléculaires au moment où certaines décisions pourraient encore être modifiées, en particulier pendant ou immédiatement après la chirurgie.

Le présent projet ne vise cependant pas à introduire immédiatement le nanopore dans la décision peropératoire. Il vise d’abord à répondre à une question préalable : **le résultat obtenu sur un prélèvement congelé local est-il suffisamment concordant avec le diagnostic intégré FFPE pour justifier une étude ultérieure en temps réel ?**

### 3.3. Nanopore et classification des tumeurs du SNC

Le séquençage nanopore présente plusieurs propriétés particulièrement adaptées à cette question : analyse d’ADN natif, détection directe de la méthylation, production des données en temps réel et possibilité d’analyse à faible couverture.

Plusieurs travaux ont montré la faisabilité d’une classification moléculaire des tumeurs cérébrales par nanopore, depuis les premières démonstrations de classification peropératoire jusqu’aux approches récentes intégrant méthylation, CNV et parfois d’autres altérations moléculaires.

Parmi les outils actuellement les plus pertinents :

- **crossNN / nanoDx**, classifier sparse et cross-platform disposant d’un modèle CNS pré-entraîné et d’un code reproductible ;
- **Sturgeon**, classifieur deep-learning développé spécifiquement pour la classification peropératoire à partir de profils nanopore extrêmement parcimonieux ;
- **MethyLYZR**, approche probabiliste légère adaptée à la classification rapide de données de méthylation sparse ;
- **MNP-Flex**, approche récente dérivée d’une référence CNS plus large et compatible avec plusieurs plateformes, sous réserve de son accessibilité dans le cadre du projet.

Ces outils ont été développés sur de grandes références externes et ne nécessitent pas de constituer localement une cohorte de plusieurs milliers de tumeurs pour être évalués.

### 3.4. Positionnement du projet

L’objectif n’est pas de développer une « IA locale » ni de réentraîner un classifieur sur une cohorte de taille insuffisante.

Le projet repose au contraire sur une logique de **validation externe comparative** : appliquer plusieurs classifieurs indépendants, déjà entraînés et publiés, aux mêmes données nanopore produites localement, puis mesurer leur concordance avec le diagnostic intégré réel des patients.

Cette stratégie permet de répondre à trois questions directement utiles :

1. le nanopore permet-il de reproduire le diagnostic intégré conventionnel dans notre population ?
2. quels classifieurs sont les plus robustes, et dans quelles situations échouent-ils ?
3. quelle quantité de données est nécessaire avant que la classification devienne correcte et stable ?

---

## 4. Données disponibles et faisabilité locale

Le projet sera conduit dans l’environnement du Plateau de Médecine Moléculaire et de Génomique (PMMG), où les compétences nécessaires à sa réalisation sont déjà présentes.

Des équipes du CHU Montpellier ont une expérience publiée du séquençage long-read et de l’utilisation d’Oxford Nanopore. Une étude portant sur une duplication intragénique de `PALB2` a notamment utilisé MinION/Flongle avec basecalling, alignement long-read, visualisation et détection de variants structuraux, avec implication de MOBIDIC/PMMG. Cette expérience démontre l’existence locale des compétences wet-lab et bioinformatiques nécessaires à l’exploitation de données ONT.

Le CHU Montpellier dispose également d’une connexion scientifique directe avec la classification nanopore des tumeurs du SNC. Dans l’étude de Filser et al. publiée dans *Neuro-Oncology* en 2025 sur la classification des médulloblastomes par nanopore, Valérie Rigau et Gilles Palenzuela figurent parmi les co-auteurs. Cette étude a montré une forte concordance avec la classification de référence, y compris avec des configurations de séquençage à faible capacité.

Le projet ne nécessite donc pas l’acquisition d’un nouveau séquenceur ni la création d’une infrastructure bioinformatique dédiée. Les principales dépenses spécifiques concernent les flow cells, les kits de préparation de librairie, l’extraction/quantification de l’ADN et la prise en charge du prélèvement congelé.

> **TO DO — RECRUTEMENT RÉEL**  
> - Nombre annuel de patients opérés / pris en charge pour une tumeur du SNC : `....................`  
> - Nombre annuel disposant d’un fragment congelé exploitable : `....................`  
> - Durée réaliste d’inclusion : `....................`  
> - Répartition approximative des principales familles tumorales : `....................`

---

## 5. Hypothèse et objectifs

### 5.1. Hypothèse principale

Nous faisons l’hypothèse que le séquençage nanopore sur tissu tumoral congelé permet d’obtenir, avec un taux élevé de succès technique, une classification diagnostique concordante avec le diagnostic intégré final établi en routine sur FFPE.

### 5.2. Objectif principal

Évaluer la concordance diagnostique entre le workflow nanopore appliqué à un prélèvement tumoral congelé et le diagnostic intégré final établi en routine sur FFPE.

### 5.3. Objectifs secondaires

Les objectifs secondaires seront de :

1. comparer les performances de plusieurs classifieurs pré-entraînés appliqués aux mêmes données nanopore ;
2. mesurer le taux de résultats techniquement exploitables et le taux de classifications conclusives ;
3. caractériser les erreurs, discordances et situations de non-classification ;
4. étudier l’influence de la cellularité tumorale, de la nécrose, de la qualité de l’ADN et des paramètres pré-analytiques sur la performance ;
5. déterminer la quantité de données nécessaire à l’obtention d’une classification correcte et stable ;
6. mesurer, dans une sous-cohorte dédiée, la cinétique réelle de classification en singleplex ou faible multiplexage ;
7. documenter le délai analytique, la consommation de réactifs et le coût par prélèvement ;
8. explorer, selon la qualité des données obtenues, les informations additionnelles accessibles par nanopore, notamment CNV et méthylation de `MGMT`, et éventuellement certaines altérations structurales ou de séquence selon le workflow retenu.

---

## 6. Méthodologie

### 6.1. Schéma de l’étude

Il s’agira d’une **étude prospective, monocentrique, comparative et appariée de performance diagnostique**.

Pour chaque patient inclus :

- le **standard de référence** sera le diagnostic intégré final établi dans le circuit diagnostique habituel sur tissu FFPE ;
- le **test index** sera l’analyse nanopore réalisée sur un fragment tumoral congelé provenant de la même intervention.

Chaque patient constituera son propre comparateur.

Le résultat nanopore restera expérimental et ne sera pas utilisé pour établir le diagnostic clinique ni modifier la prise en charge au cours de cette première phase.

### 6.2. Population

Les patients éligibles seront inclus consécutivement afin de limiter le biais de sélection et de refléter la population réellement prise en charge.

Seront considérés comme éligibles les patients :

- pris en charge pour une lésion tumorale du SNC ;
- disposant d’un prélèvement permettant l’établissement du diagnostic de routine sur FFPE ;
- pour lesquels un fragment tumoral congelé correspondant à la même intervention est disponible sans compromettre les analyses nécessaires aux soins ;
- pour lesquels un diagnostic intégré final peut être établi selon les procédures diagnostiques habituelles.

La cohorte principale ne sera pas enrichie artificiellement en tumeurs facilement classifiables. Les cas rares, difficiles ou discordants pourront faire l’objet d’analyses secondaires spécifiques.

### 6.3. Standard diagnostique de référence

Le diagnostic intégré final sur FFPE constituera le standard de référence. Il reposera sur l’examen histologique, l’immunohistochimie, les analyses moléculaires indiquées dans le contexte clinique et l’ensemble des informations nécessaires à l’établissement du diagnostic intégré selon la classification des tumeurs du SNC en vigueur.

Les équipes réalisant le diagnostic conventionnel ne disposeront pas du résultat nanopore expérimental.

### 6.4. Prélèvement congelé

Un fragment tumoral congelé provenant de la même intervention que le matériel FFPE sera utilisé pour le test index.

Lorsque cela sera possible, les fragments FFPE et congelé seront issus de territoires anatomiquement proches. Une évaluation anatomopathologique du fragment destiné au nanopore ou d’une section adjacente documentera la représentativité tumorale.

Seront notamment enregistrés :

- pourcentage estimé de cellules tumorales ;
- présence et importance de la nécrose ;
- proportion de tissu non tumoral ;
- quantité et qualité de l’ADN ;
- principales variables pré-analytiques.

### 6.5. Séquençage nanopore

L’ADN natif extrait du prélèvement congelé sera séquencé sur une plateforme Oxford Nanopore disponible localement.

La préparation de librairie de référence retenue pour le chiffrage actuel est le **Rapid Barcoding Kit V14 (`SQK-RBK114.24`)** sur flow cell **R10.4.1 (`FLO-MIN114`)**. Ce choix reste à confirmer avant la version finale du protocole.

La chaîne bioinformatique comprendra a minima :

1. basecalling ;
2. alignement sur le génome de référence ;
3. appel de méthylation ;
4. génération des formats nécessaires aux différents classifieurs ;
5. application des modèles pré-entraînés ;
6. enregistrement des prédictions et scores de confiance ;
7. collecte des métriques de séquençage nécessaires aux analyses de cinétique.

Les versions exactes des logiciels, modèles, paramètres et seuils seront gelées avant l’analyse de la cohorte principale.

### 6.6. Stratégie de séquençage en deux modalités

#### Cohorte principale — validation diagnostique

La majorité des prélèvements sera séquencée en **6-plex**, soit six échantillons par flow cell.

Cette modalité vise à obtenir un compromis entre coût et quantité de données par patient. La question principale dans cette cohorte sera la concordance diagnostique finale avec le standard de référence FFPE.

Les données de cette cohorte permettront également d’étudier la relation entre quantité de données et performance. En revanche, le temps chronologique de classification observé en 6-plex ne sera pas interprété comme une estimation directe du délai peropératoire, les six bibliothèques partageant la capacité de séquençage.

#### Sous-cohorte cinétique — transposabilité peropératoire

Une sous-cohorte prédéfinie sera séquencée en **singleplex ou faible multiplexage**, afin d’estimer la cinétique réelle d’acquisition de l’information dans une configuration plus proche d’une future utilisation peropératoire.

Elle permettra de mesurer :

- le temps jusqu’à la première classification correcte ;
- le temps jusqu’à une classification correcte et stable ;
- le nombre de reads, de bases et de CpG nécessaires ;
- la variation de cette cinétique selon le classifieur.

> **TO DO — SOUS-COHORTE CINÉTIQUE**  
> - Effectif : `....................`  
> - Modalité : `singleplex / 2-plex / autre : ....................`  
> - Critères d’arrêt du run : `....................`

### 6.7. Classifieurs

Les mêmes données nanopore seront analysées indépendamment par plusieurs classifieurs déjà publiés et pré-entraînés.

La liste envisagée comprend :

- crossNN / nanoDx ;
- MethyLYZR ;
- Sturgeon ;
- MNP-Flex, sous réserve d’accessibilité.

L’étude est conçue comme une **validation externe**. Aucun modèle ne sera entraîné, fine-tuné, recalibré ou optimisé sur la cohorte locale avant l’analyse principale. Il n’est donc pas prévu de séparation locale training/test pour le critère principal.

> **TO DO — PARAMÈTRES TECHNIQUES**  
> - Liste définitive des classifieurs : `....................`  
> - Versions exactes : `....................`  
> - Seuils de confiance : `....................`  
> - Règles de mapping methylation family/class/subclass → diagnostic clinique : `....................`

### 6.8. Analyse en aveugle

Les prédictions nanopore seront générées sans connaissance du diagnostic intégré final. Les résultats de chaque classifieur seront enregistrés avant levée de l’aveugle.

Les correspondances entre les sorties des modèles et les catégories diagnostiques utilisées pour la comparaison clinique seront définies a priori et gelées avant l’analyse principale.

---

## 7. Critères de jugement

### 7.1. Critère principal

Le critère principal sera le **taux de diagnostics nanopore concordants avec le diagnostic intégré de référence**, calculé sur l’ensemble des patients pour lesquels l’analyse nanopore a été initiée.

L’analyse suivra une approche **intention-to-diagnose**.

Seront considérés comme échecs pour le critère principal :

- échec d’extraction empêchant l’analyse ;
- échec de séquençage ;
- quantité de données insuffisante ;
- absence de prédiction ;
- prédiction sous le seuil de confiance prédéfini ;
- autre résultat non conclusif.

La concordance sera évaluée à un niveau diagnostique prédéfini et cliniquement pertinent, distinct de la seule identité d’une methylation subclass.

### 7.2. Critères secondaires

Seront notamment évalués :

- diagnostic yield : proportion de patients avec un résultat nanopore conclusif ;
- conditional accuracy : proportion de diagnostics corrects parmi les résultats conclusifs ;
- performance globale en intention-to-diagnose ;
- performance propre à chaque classifieur ;
- concordance entre classifieurs ;
- performances par grande famille tumorale ;
- nature et importance clinique des discordances ;
- délai jusqu’à la première classification correcte ;
- délai jusqu’à une classification correcte et stable ;
- nombre de reads, bases et CpG nécessaires ;
- taux d’échec technique ;
- délai extraction → résultat ;
- coût analytique par patient.

---

## 8. Analyse de la cinétique

Les données nanopore seront analysées de manière cumulative à plusieurs temps préspécifiés. Une grille indicative est : **5, 10, 15, 30, 45 et 60 minutes**, puis fin de run.

À chaque temps seront enregistrés :

- nombre de reads ;
- quantité de bases ;
- nombre de CpG informatifs ;
- prédiction ;
- score de confiance ;
- concordance avec le diagnostic de référence.

Une **classification correcte et stable** sera définie comme la première prédiction concordante avec le diagnostic de référence qui reste concordante à l’ensemble des temps ultérieurs préspécifiés.

> **TO DO — DÉFINITION FINALE DE LA CINÉTIQUE**  
> Valider les temps d’analyse et la définition de stabilité avec l’URCE et après choix final du workflow.

---

## 9. Analyse statistique

Les analyses seront conduites au niveau du patient. Les estimations seront accompagnées d’intervalles de confiance à 95 %.

### 9.1. Analyse descriptive

Les variables quantitatives seront décrites par moyenne et écart-type ou médiane et intervalle interquartile selon leur distribution. Les variables qualitatives seront décrites par effectifs et pourcentages.

La distribution des diagnostics et les paramètres pré-analytiques seront décrits pour caractériser la population et évaluer sa représentativité.

### 9.2. Critère principal

Le taux de concordance diagnostique sera estimé avec un **intervalle de confiance binomial à 95 %**.

Seront rapportés séparément :

1. le diagnostic yield ;
2. la conditional accuracy ;
3. la performance globale en intention-to-diagnose, qui constituera l’analyse principale.

### 9.3. Comparaison des classifieurs

Les différents modèles étant appliqués aux mêmes patients, les comparaisons seront appariées.

Les différences de proportions de diagnostics corrects entre deux modèles pourront être testées par **test de McNemar**. Une correction de multiplicité, par exemple selon Holm, sera appliquée lorsque plusieurs comparaisons seront réalisées.

Les matrices de confusion et le coefficient kappa de Cohen seront utilisés comme mesures descriptives complémentaires de concordance.

Lorsque les effectifs le permettront, les performances par grande famille tumorale seront décrites, notamment par sensibilité/rappel, valeur prédictive positive et balanced accuracy.

### 9.4. Effet du temps et de la quantité de données

La probabilité d’obtenir une classification correcte sera étudiée à différents temps de séquençage.

Les mesures répétées chez un même patient seront prises en compte à l’aide d’un **modèle de régression logistique à effets mixtes** ou d’une méthode équivalente pour données longitudinales. Le modèle pourra inclure le temps, le classifieur et leur interaction, avec un effet aléatoire patient.

Des analyses analogues pourront utiliser le nombre de reads, le nombre de bases ou le nombre de CpG comme variable d’exposition.

### 9.5. Facteurs associés aux échecs

Les facteurs associés à un résultat non conclusif, une discordance diagnostique ou un délai prolongé seront étudiés de façon exploratoire. Les variables candidates incluront notamment cellularité tumorale, nécrose, quantité/qualité de l’ADN, type tumoral et paramètres de séquençage.

Le nombre de variables introduites dans les modèles multivariés sera limité en fonction du nombre d’événements observés afin d’éviter le surajustement.

### 9.6. Données manquantes

Aucune imputation ne sera réalisée pour le critère principal. Les résultats nanopore non conclusifs resteront intégrés comme échecs dans l’analyse principale. Une analyse de sensibilité sera réalisée parmi les seuls cas techniquement évaluables.

---

## 10. Taille de cohorte

La taille définitive de la cohorte sera déterminée avec l’URCE.

Deux approches sont actuellement envisagées :

1. une approche **estimative**, visant à estimer une concordance attendue élevée avec une précision prédéfinie ;
2. une approche **confirmatoire**, visant à démontrer que la concordance dépasse un seuil minimal cliniquement acceptable.

Les simulations budgétaires actuelles explorent des effectifs compris entre environ 80 et 200 patients. Une cohorte de l’ordre de 120–150 patients constitue actuellement un scénario de travail plausible mais **ne doit pas être considérée comme l’effectif statistique définitif**.

> **TO DO — CALCUL D’EFFECTIF URCE**  
> - Approche retenue : `....................`  
> - Concordance attendue : `....................`  
> - Seuil minimal acceptable : `....................`  
> - Alpha : `....................`  
> - Puissance : `....................`  
> - Taux de non-évaluables : `....................`  
> - Effectif final cohorte principale : `....................`  
> - Effectif sous-cohorte cinétique : `....................`

---

## 11. Aspects réglementaires et éthiques

Le résultat nanopore restera expérimental et ne modifiera pas la prise en charge clinique pendant cette première phase. Le projet utilisera un fragment tumoral congelé obtenu dans le contexte de l’intervention, sans compromettre le matériel nécessaire au diagnostic et aux soins.

La qualification réglementaire définitive dépendra des modalités exactes de constitution prospective de la collection, de l’information des patients et de l’utilisation des données moléculaires.

> **TO DO — QUALIFICATION RÉGLEMENTAIRE**  
> À valider avec URCE / DRI :  
> - cadre réglementaire : `HLJ / RIPH3 / autre cadre compatible : ....................`  
> - modalités d’information / consentement / non-opposition : `....................`  
> - modalités de constitution et conservation de la collection : `....................`  
> - cadre de conservation et utilisation des données génomiques : `....................`

---

## 12. Organisation du projet et responsabilités

Le projet repose sur l’articulation de plusieurs compétences déjà présentes au CHU Montpellier : neuropathologie, biologie moléculaire, séquençage long-read, bioinformatique clinique, tumorothèque/CRB et méthodologie/biostatistiques.

> **TO DO — ÉQUIPE ET RESPONSABILITÉS**
>
> | Rôle | Nom | Structure | Responsabilités principales |
> |---|---|---|---|
> | Porteur |  |  |  |
> | Neuropathologie |  |  |  |
> | PMMG / biologie moléculaire |  |  |  |
> | Bioinformatique |  |  |  |
> | CRB / tumorothèque |  |  |  |
> | Neurochirurgie |  |  |  |
> | Méthodologie / biostatistiques |  |  |  |

---

## 13. Budget prévisionnel

Les séquenceurs et l’infrastructure bioinformatique étant déjà disponibles localement, le budget incrémental repose principalement sur :

- prise en charge du fragment congelé / CRB ;
- extraction et quantification de l’ADN ;
- kits de préparation de librairie ;
- flow cells ;
- petits consommables ;
- coûts de promotion, méthodologie et autres coûts institutionnels obligatoires.

Le modèle budgétaire actuel utilise comme références provisoires :

- `FLO-MIN114` : **740 € HT / flow cell** ;
- `SQK-RBK114.24` : **730 € HT / kit**, six réactions complètes par kit ;
- QIAamp Fast DNA Tissue Kit : **296 € / 50 extractions** ;
- Qubit dsDNA HS : **135,65 € / 100 dosages** ;
- petits consommables : **4 € / patient** ;
- CRB : scénario provisoire bas et haut fondé sur la grille publique, en attente d’un devis prospectif spécifique.

Dans le scénario de travail actuel de **150 patients dont 12 en 2-plex et le reste en 6-plex**, le coût technique estimatif est d’environ :

- **39,7 k€** avec l’hypothèse CRB basse ;
- **49,9 k€** avec l’hypothèse CRB haute ;

marge technique de 10 % incluse et hors coûts institutionnels encore inconnus.

Le classeur `budget_previsionnel_AAP_JC2026.xlsx` permet de modifier directement l’effectif, les prix marché, le multiplexage et les coûts institutionnels.

> **TO DO — COÛTS INSTITUTIONNELS / MARCHÉ CHU**  
> - Prix marché `FLO-MIN114` : `.................... € HT`  
> - Prix marché `SQK-RBK114.24` : `.................... € HT`  
> - Devis CRB / patient, fragment prospectif ~20–30 mg : `.................... € HT`  
> - Frais de promotion : `.................... €`  
> - Méthodologie / biostatistiques : `.................... €`  
> - Personnel spécifique : `.................... €`  
> - Autres coûts obligatoires : `.................... €`

---

## 14. Calendrier prévisionnel

Le projet devra être réalisé dans la durée maximale de trois ans prévue par l’AAP.

### Phase 1 — préparation et mise en place

- finalisation du protocole ;
- validation réglementaire ;
- ouverture de l’étude ;
- gel des versions de pipelines et classifieurs ;
- validation technique du workflow local ;
- formation/documentation opératoire si nécessaire.

### Phase 2 — inclusion et analyses nanopore

- inclusion consécutive des patients ;
- constitution du prélèvement congelé ;
- séquençage en 6-plex pour la cohorte principale ;
- séquençage singleplex/faible multiplexage pour la sous-cohorte cinétique ;
- contrôle qualité et archivage des données ;
- suivi prospectif des échecs techniques.

### Phase 3 — gel de base, analyses et valorisation

- gel de la base de données ;
- levée de l’aveugle ;
- analyses statistiques ;
- analyse des discordances ;
- rédaction du manuscrit scientifique ;
- préparation de la phase prospective peropératoire si les critères sont atteints.

> **TO DO — CALENDRIER**  
> Remplacer ce calendrier fonctionnel par un calendrier daté après obtention du recrutement annuel réel et de l’effectif définitif.

---

## 15. Risques, limites et mesures de contrôle

### Hétérogénéité tumorale

Le prélèvement congelé et le bloc FFPE peuvent ne pas représenter exactement le même territoire tumoral. Ce risque sera limité par la traçabilité anatomique des prélèvements et par l’évaluation histologique de la représentativité tumorale du fragment destiné au nanopore.

### Échec technique ou données insuffisantes

Les échecs seront enregistrés prospectivement et inclus dans l’analyse principale en intention-to-diagnose. La performance du workflow ne sera donc pas artificiellement surestimée en excluant les cas difficiles.

### Déséquilibre entre classes tumorales

L’inclusion consécutive reflétera la distribution clinique réelle. Les analyses par classe seront considérées comme secondaires lorsque les effectifs sont faibles. Le critère principal portera sur une concordance diagnostique globale cliniquement pertinente.

### Évolution des classifieurs

Les modèles et versions utilisés seront gelés avant l’analyse principale. Toute version ultérieure sera évaluée séparément comme analyse exploratoire.

### Risque de surapprentissage

Aucun réentraînement ni optimisation sur la cohorte locale ne sera autorisé pour l’analyse principale.

### Budget

Le coût dépend fortement du prix des flow cells et du coût CRB. La stratégie de multiplexage à six patients par flow cell vise à conserver un effectif suffisant tout en restant compatible avec l’enveloppe de l’AAP.

---

## 16. Résultats attendus

L’étude doit permettre d’obtenir une réponse quantitative à la question principale : **dans quelle proportion des cas un workflow nanopore sur tissu congelé reproduit-il le diagnostic intégré établi en routine sur FFPE ?**

Elle permettra également de :

- mesurer le taux réel de résultats non conclusifs ;
- comparer plusieurs classifieurs indépendants sur une même cohorte ;
- identifier les types d’erreurs et leurs déterminants ;
- définir la quantité minimale de données nécessaire à une classification fiable ;
- mesurer une cinétique réaliste dans une configuration compatible avec une future utilisation peropératoire ;
- établir un coût par patient dans les conditions locales.

---

## 17. Perspectives et effet levier

Le projet est conçu comme une étape de validation préalable à un changement potentiel de temporalité diagnostique.

Si la concordance diagnostique, le taux de succès technique et les délais sont compatibles avec les objectifs prédéfinis, une seconde étude prospective pourra tester le workflow en situation peropératoire, avec implication directe des équipes de neurochirurgie et de neuropathologie.

Cette seconde phase devra répondre à une question différente : non plus seulement « le diagnostic est-il correct ? », mais **« une information moléculaire disponible pendant l’intervention modifie-t-elle de manière pertinente la stratégie chirurgicale ou la prise en charge immédiate ? »**

La littérature récente apporte déjà des éléments en faveur de cette perspective : des workflows nanopore ont démontré une classification pendant la fenêtre opératoire et des études cliniques récentes ont montré que cette information pouvait soutenir ou modifier la stratégie chirurgicale dans certaines situations. Le présent projet fournira les données locales nécessaires pour décider si cette transposition est justifiée au CHU Montpellier.

L’effet levier attendu comprend :

- une publication princeps portant sur la validation prospective du workflow nanopore local ;
- la constitution d’un pipeline reproductible et documenté ;
- une base méthodologique pour une étude prospective peropératoire ;
- la possibilité d’un futur projet multicentrique ou d’un AAP de plus grande envergure ;
- une structuration renforcée entre neuropathologie, PMMG, bioinformatique et neurochirurgie autour du diagnostic moléculaire rapide des tumeurs du SNC.

---

## 18. Valorisation scientifique

La publication principale devra privilégier une présentation transparente de l’ensemble du workflow, incluant les échecs techniques et les résultats non conclusifs.

Le manuscrit pourra être structuré comme une étude de validation diagnostique externe avec comparaison de plusieurs modèles pré-entraînés. La cohorte locale ne sera pas utilisée comme cohorte d’entraînement pour la publication principale.

Des analyses complémentaires pourront faire l’objet de travaux secondaires :

- comparaison approfondie des classifieurs ;
- analyse des cas discordants ;
- relation entre cellularité et performance ;
- métriques de temps-to-diagnosis ;
- CNV/MGMT/altérations additionnelles ;
- analyse médico-économique exploratoire.

Le porteur du projet devra être premier auteur de la publication princeps conformément aux exigences de l’AAP.

---

## 19. Bibliographie principale

La bibliographie complète et les références BibTeX sont disponibles dans :

- `references.md` ;
- `references.bib` ;
- `surgical_impact_references.bib` ;
- `montpellier_local_references.bib`.

Références particulièrement structurantes pour le projet :

1. Capper D, et al. *Nature*. 2018. DNA methylation-based classification of central nervous system tumours.
2. Louis DN, et al. *Neuro-Oncology*. 2021. WHO Classification of Tumors of the Central Nervous System.
3. Sahm F, et al. *Neuro-Oncology*. 2023. EANO guideline on molecular diagnostic tools for CNS tumours.
4. Djirackor L, et al. *Neuro-Oncology Advances*. 2021. Intraoperative DNA methylation classification of brain tumors impacts neurosurgical strategy.
5. Kuschel LP, et al. *Neuropathology and Applied Neurobiology*. 2023. Robust methylation-based classification of brain tumours using nanopore sequencing.
6. Vermeulen C, et al. *Nature*. 2023. Ultra-fast deep-learned CNS tumour classification during surgery.
7. Brändl B, et al. *Nature Medicine*. 2025. Rapid brain tumor classification from sparse epigenomic data.
8. Patel A, et al. *Nature Medicine*. 2025. Prospective multicenter validation of Rapid-CNS2.
9. Yuan D, et al. *Nature Cancer*. 2025. crossNN.
10. Deacon S, et al. *Neuro-Oncology*. 2025. ROBIN.
11. Filser M, et al. *Neuro-Oncology*. 2025. Nanopore sequencing as a cutting-edge technology for medulloblastoma classification.
12. Aldape K, et al. *Neuro-Oncology Advances*. 2025. cIMPACT-NOW update 9 on genome-wide DNA methylation profiling.
13. Sie M, et al. *Neuro-Oncology*. 2026. How “Sturgeon” guides the surgeon in pediatric neuro-oncology.

---

## 20. Éléments à verrouiller avant version v1.0

Voir `TO_DO.md` pour le suivi détaillé.

### Bloquants avant soumission

- [ ] Recrutement réel et durée d’inclusion.
- [ ] Calcul d’effectif définitif avec l’URCE.
- [ ] Qualification réglementaire.
- [ ] Prix marché CHU et devis CRB.
- [ ] Coûts institutionnels complets.
- [ ] Composition de l’équipe et responsabilités.

### À préspécifier avant démarrage

- [ ] Séquenceur/configuration exacte.
- [ ] Méthode d’extraction finale.
- [ ] Multiplexage définitif de la sous-cohorte cinétique.
- [ ] Classifieurs et versions.
- [ ] Seuils de confiance.
- [ ] Mapping classes → diagnostic clinique.
- [ ] Définition finale de classification correcte et stable.

---

## 21. Statut de la version v0.1

Cette version contient une trame scientifique suffisamment complète pour servir de base à la rédaction du dossier JC 2026. Les inconnues restantes sont principalement institutionnelles, réglementaires et quantitatives ; elles ne remettent pas en cause la question scientifique ni le design général du projet.
