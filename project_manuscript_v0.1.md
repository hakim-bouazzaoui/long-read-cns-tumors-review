# Projet JC 2026 — validation du séquençage nanopore sur tumeurs du SNC

**Version :** v0.1 — mise à jour du rationnel clinique du 2026-09-08  
**Statut :** manuscrit scientifique de travail — non finalisé  
**AAP :** Jeunes Chercheurs Tremplin 2026 — CHU Montpellier  
**Références de travail :** `references.bib`, `references.md`, `clinical_impact_perioperative.md`, `methodology_AAP_JC2026_2026-09-08.md`, `montpellier_landscape_2026-09-07.md`, `budget_previsionnel.md`, `budget_previsionnel_AAP_JC2026.xlsx`, `TO_DO.md`

> **IMPORTANT — VERSION NON FINALISÉE**  
> Les éléments signalés `TO DO` doivent être complétés avant soumission. Ils concernent principalement le recrutement réel, le calcul d’effectif définitif avec l’URCE, la qualification réglementaire, les coûts institutionnels et la composition de l’équipe.

---

## 1. Titre provisoire

**Validation prospective du séquençage nanopore sur tissu tumoral congelé pour la classification moléculaire des tumeurs du système nerveux central**

> **TO DO — TITRE / ACRONYME**  
> Définir un acronyme court et mémorisable après stabilisation du périmètre final.

---

## 2. Résumé scientifique

La chirurgie constitue un temps majeur de la prise en charge de nombreuses tumeurs du système nerveux central (SNC). L’objectif opératoire doit cependant être adapté à une double contrainte : maximiser le bénéfice oncologique de la résection tout en préservant la fonction neurologique. Or, au moment de l’intervention, cette décision repose encore largement sur l’imagerie, l’exploration chirurgicale, le monitoring fonctionnel et l’examen extemporané, alors que le diagnostic intégré définitif — incluant les données moléculaires — n’est disponible qu’après coup sur tissu fixé et inclus en paraffine (FFPE).

Cette temporalité constitue une limite clinique. Plusieurs travaux montrent qu’une information moléculaire disponible pendant l’intervention peut réduire l’incertitude diagnostique et contribuer à orienter la stratégie chirurgicale. Dans l’étude de Djirackor et al., une classification moléculaire peropératoire aurait soutenu une modification de stratégie dans **12 des 20 cas intraopératoires (60 %)**. Plus récemment, dans une cohorte pédiatrique prospective de 94 patients, l’utilisation clinique de Sturgeon a **modifié la stratégie chirurgicale dans 14,3 % des cas informatifs**, vers une résection plus ou moins étendue selon la situation. Les auteurs rapportent également une faible morbidité et moins de chirurgies de second look, sans que ces associations permettent à elles seules d’établir un bénéfice causal. Chez l’adulte, une étude prospective multicentrique de 296 patients atteints de gliome diffus a montré qu’un diagnostic moléculaire rapide pouvait corriger en temps réel des interprétations extemporanées erronées, notamment des lésions initialement considérées comme gliomes de bas grade ou glioses.

L’intérêt d’une caractérisation moléculaire rapide ne se limite donc pas à « gagner du temps ». Il est de fournir, pendant la fenêtre décisionnelle chirurgicale, une information plus précise sur l’identité et la biologie tumorales susceptible d’aider à arbitrer entre poursuite de la résection, préservation fonctionnelle et nécessité éventuelle d’une nouvelle intervention. Les données rétrospectives disponibles dans le glioblastome suggèrent en outre que le bénéfice d’une résection maximale pourrait différer selon les sous-classes de méthylation, renforçant le rationnel d’une chirurgie informée par la biologie tumorale, tout en nécessitant encore une validation prospective.

Le séquençage Oxford Nanopore est particulièrement adapté à cette perspective : il permet l’analyse directe de l’ADN natif et de sa méthylation, génère les données en temps réel et peut fournir, à faible couverture, une classification moléculaire accompagnée d’informations de nombre de copies. Des workflows récents tels que Sturgeon, Rapid-CNS2, iSCORED ou ROBIN ont montré qu’une information de méthylation et/ou de CNV pouvait être obtenue dans une fenêtre compatible avec l’intervention chirurgicale. Plusieurs classifieurs pré-entraînés — crossNN/nanoDx, Sturgeon, MethyLYZR et MNP-Flex — permettent désormais d’exploiter ces données sans devoir constituer localement une cohorte d’entraînement de plusieurs milliers de tumeurs.

Avant d’envisager une utilisation clinique peropératoire au CHU de Montpellier, une étape préalable est néanmoins indispensable : démontrer que le workflow nanopore réalisé localement sur tissu tumoral congelé reproduit de manière fiable le diagnostic intégré de référence établi en routine sur FFPE.

L’objectif principal de ce projet est donc d’évaluer, dans les conditions réelles de prise en charge au CHU de Montpellier, la concordance diagnostique entre le séquençage nanopore d’un prélèvement tumoral congelé et le diagnostic intégré final établi en routine sur FFPE.

Il s’agira d’une étude prospective, monocentrique, comparative et appariée de performance diagnostique. La cohorte principale sera analysée en multiplexage de six échantillons par flow cell afin d’évaluer la performance diagnostique dans une configuration économiquement soutenable. Une sous-cohorte prédéfinie sera séquencée en singleplex ou faible multiplexage afin de caractériser la cinétique réelle d’acquisition de l’information moléculaire et d’estimer la transposabilité future du workflow à une utilisation peropératoire.

Après audit des réactifs disponibles et des protocoles actuels, le **Rapid Barcoding Kit V14 (`SQK-RBK114.24`) sur flow cell R10.4.1 (`FLO-MIN114`)** est retenu comme workflow de référence pour la planification du projet. Les mêmes données nanopore seront analysées par plusieurs classifieurs publiés et pré-entraînés, sans réentraînement ni optimisation sur la cohorte locale pour l’analyse principale. Le critère principal sera le taux de diagnostics nanopore concordants avec le diagnostic intégré de référence dans une approche en intention-to-diagnose, intégrant les échecs techniques et résultats non conclusifs.

Le projet s’appuie sur une infrastructure déjà disponible au CHU Montpellier : séquenceurs nanopore, expertise en biologie moléculaire, expérience locale du long-read et compétences bioinformatiques au PMMG/MOBIDIC. Si les performances diagnostiques et la cinétique observée sont compatibles avec les objectifs prédéfinis, cette étude constituera le socle méthodologique d’une seconde phase prospective évaluant l’impact clinique d’un diagnostic moléculaire peropératoire sur la stratégie chirurgicale.

---

## 3. Contexte scientifique et médical

### 3.1. La décision chirurgicale est prise avant le diagnostic intégré définitif

Pour de nombreuses tumeurs du SNC, la chirurgie constitue à la fois un temps diagnostique et thérapeutique. L’étendue de résection est associée au pronostic dans plusieurs entités, mais toute résection supplémentaire doit être mise en balance avec le risque de déficit neurologique. Les recommandations contemporaines de chirurgie des gliomes insistent ainsi sur une approche individualisée combinant bénéfice oncologique attendu, localisation fonctionnelle, monitoring peropératoire et caractéristiques propres au patient et à la tumeur.

Cette décision est cependant prise alors que le diagnostic intégré définitif n’est pas encore disponible. L’examen extemporané apporte une information morphologique rapide mais peut rester indéterminé ou être discordant avec le diagnostic final, en particulier dans certaines tumeurs diffuses, rares ou morphologiquement ambiguës. Les données moléculaires nécessaires à la classification actuelle — mutations, altérations de nombre de copies et profils de méthylation — sont généralement obtenues secondairement sur FFPE.

La conséquence clinique potentielle est double : une chirurgie peut être arrêtée alors qu’une résection plus complète aurait été souhaitable, ou au contraire être poursuivie alors que le bénéfice oncologique attendu d’une résection supplémentaire est incertain au regard du risque fonctionnel. Dans certaines situations, une caractérisation diagnostique tardive peut également conduire à discuter une chirurgie secondaire.

### 3.2. Pourquoi une caractérisation moléculaire précise peut modifier la stratégie opératoire

L’intérêt d’une analyse tumorale précise pendant l’intervention ne réside pas uniquement dans l’accélération du diagnostic. Il réside dans la possibilité de fournir une information biologique supplémentaire au moment où la stratégie chirurgicale est encore modifiable.

Djirackor et al. ont montré dès 2021 qu’une classification peropératoire de la méthylation pouvait être obtenue avec un résultat médian transmis au bloc en 97 minutes. Dans les 20 cas évalués spécifiquement pour l’impact décisionnel, le résultat moléculaire **aurait soutenu une modification de la stratégie chirurgicale dans 12 cas (60 %)**. Les exemples rapportés illustrent les deux directions possibles : éviter une sous-résection et potentiellement une seconde intervention lorsque l’examen extemporané est trompeur, mais aussi éviter une résection additionnelle à haut risque lorsque le bénéfice oncologique attendu paraît limité.

La preuve clinique la plus directe provient actuellement de la population pédiatrique. Dans l’étude de Sie et al. publiée en 2026, 94 patients consécutifs ont bénéficié d’une classification nanopore Sturgeon intégrée au circuit peropératoire. Lorsqu’il était informatif, le résultat soutenait la stratégie prévue dans 85,7 % des cas et **modifiait effectivement la stratégie chirurgicale dans 14,3 % des cas**, vers une résection plus ou moins agressive. Les auteurs rapportent également une faible complication et moins de procédures de second look. Ces résultats constituent une preuve de principe forte de l’utilité clinique possible, mais ne doivent pas être extrapolés directement à l’adulte.

Chez l’adulte, Wu et al. ont apporté une démonstration complémentaire dans une cohorte prospective multicentrique de 296 patients atteints de gliome diffus. Un test moléculaire rapide `IDH1/2`/`TERTp` obtenu en environ 35 minutes a permis de reclasser **40 tumeurs initialement interprétées comme gliomes de bas grade** en faveur d’un glioblastome IDH-wildtype et d’identifier **20 lésions interprétées comme glioses** comme de véritables gliomes diffus. Cette étude, bien que fondée sur une méthode PCR et non nanopore, montre directement qu’une information moléculaire disponible pendant l’intervention peut corriger une interprétation morphologique et influencer la décision opératoire.

### 3.3. La biologie tumorale peut conditionner le bénéfice attendu de la résection

L’intérêt potentiel d’une information moléculaire peropératoire dépasse la seule correction du diagnostic extemporané. Dans une série multicentrique de 430 glioblastomes IDH-wildtype, Drexler et al. ont observé que l’association entre étendue de résection et survie différait selon la sous-classe de méthylation : un bénéfice de résection maximale était observé dans les sous-classes RTK I et RTK II, mais pas de manière significative dans la sous-classe mésenchymateuse. Ces données sont rétrospectives et ne constituent pas une règle de décision validée, mais elles soutiennent l’idée qu’une stratégie chirurgicale uniforme ne reflète pas nécessairement la diversité biologique des glioblastomes.

Les travaux de synthèse récents sur la chirurgie de précision du glioblastome et les recommandations PIONEER/RANO resect convergent vers un modèle dans lequel l’étendue de résection doit être individualisée en tenant compte du bénéfice oncologique attendu, du risque fonctionnel et, à terme, d’informations biologiques obtenues pendant l’intervention. Dans ce contexte, une classification moléculaire rapide n’est pas un simple outil de laboratoire : elle peut devenir une variable supplémentaire de décision chirurgicale.

### 3.4. Le nanopore permet d’apporter une information moléculaire riche dans la fenêtre opératoire

Le séquençage nanopore présente plusieurs propriétés adaptées à cette question : analyse d’ADN natif, détection directe de la méthylation, production des données en temps réel et possibilité d’analyse à faible couverture.

Vermeulen et al. ont montré avec Sturgeon qu’une classification sparse de la méthylation pouvait être délivrée en moins de 90 minutes pendant de vraies interventions. Rapid-CNS2 a ensuite été validé prospectivement et multicentriquement : dans 18 workflows réellement réalisés en peropératoire, les informations combinant méthylation et CNV apportaient une information cliniquement pertinente au-delà de la morphologie dans **13 cas sur 18 (72,2 %)**, même si ces résultats n’étaient pas encore utilisés pour modifier la chirurgie. iSCORED a démontré qu’une combinaison méthylation + CNV pouvait être obtenue en environ 105 minutes dans des tumeurs diagnostiquement difficiles, et ROBIN a montré la faisabilité d’un assay unique fournissant classification, CNV et autres altérations moléculaires dans une fenêtre de moins de deux heures.

L’intérêt du nanopore est donc de dépasser une stratégie de quelques hotspots. Chez l’adulte, une classification intégrée peut nécessiter des informations telles que `+7/-10`, `1p/19q`, `CDKN2A/B`, amplifications oncogéniques ou profil de méthylation. Une approche genome-wide à faible couverture permet d’envisager une information plus riche et plus directement transposable au diagnostic intégré moderne.

Parmi les classifieurs actuellement les plus pertinents figurent :

- **crossNN / nanoDx**, classifieur sparse et cross-platform disposant d’un modèle CNS pré-entraîné et d’un code reproductible ;
- **Sturgeon**, développé pour la classification peropératoire à partir de profils nanopore très parcimonieux ;
- **MethyLYZR**, approche probabiliste légère adaptée à la classification rapide de données de méthylation sparse ;
- **MNP-Flex**, approche récente dérivée d’une référence CNS plus large et compatible avec plusieurs plateformes, sous réserve de son accessibilité dans le cadre du projet.

Ces outils reposent sur de grandes références externes et peuvent être évalués localement sans entraîner une nouvelle « IA maison » sur une cohorte insuffisante.

### 3.5. Positionnement du projet : une étape de validation avant l’étude d’impact clinique

La littérature établit désormais trois éléments : la classification moléculaire rapide est techniquement possible pendant une intervention ; une information moléculaire peropératoire peut corriger le diagnostic extemporané et modifier la stratégie chirurgicale ; et la biologie tumorale pourrait contribuer à déterminer le bénéfice attendu d’une résection plus extensive.

En revanche, chez l’adulte, il manque encore une démonstration prospective robuste qu’un workflow nanopore intégré améliore effectivement des critères cliniques tels que la stratégie opératoire, l’étendue de résection, le taux de seconde chirurgie, la morbidité neurologique ou la qualité de vie. Il serait donc prématuré d’utiliser directement cette information pour guider la chirurgie sans validation locale préalable.

Le présent projet constitue cette étape préalable. Il ne cherche pas encore à démontrer un bénéfice chirurgical. Il vise à établir si un workflow nanopore réalisé au CHU de Montpellier sur tissu congelé est suffisamment fiable, reproductible, rapide et économiquement soutenable pour justifier ensuite une étude prospective peropératoire.

La stratégie repose sur une **validation externe comparative** : appliquer plusieurs classifieurs indépendants, déjà entraînés et publiés, aux mêmes données nanopore produites localement, puis mesurer leur concordance avec le diagnostic intégré réel des patients.

Cette stratégie doit répondre à trois questions :

1. le nanopore permet-il de reproduire le diagnostic intégré conventionnel dans notre population ?
2. quels classifieurs sont les plus robustes, et dans quelles situations échouent-ils ?
3. quelle quantité de données est nécessaire avant que la classification devienne correcte et stable, dans une perspective de future utilisation peropératoire ?

---

## 4. Données disponibles et faisabilité locale

Le projet sera conduit dans l’environnement du Plateau de Médecine Moléculaire et de Génomique (PMMG), où les compétences nécessaires à sa réalisation sont déjà présentes.

Des équipes du CHU Montpellier ont une expérience publiée du séquençage long-read et de l’utilisation d’Oxford Nanopore. Une étude portant sur une duplication intragénique de `PALB2` a notamment utilisé MinION/Flongle avec basecalling, alignement long-read, visualisation et détection de variants structuraux, avec implication de MOBIDIC/PMMG.

Le CHU Montpellier dispose également d’une connexion scientifique directe avec la classification nanopore des tumeurs du SNC. Dans l’étude de Filser et al. publiée dans *Neuro-Oncology* en 2025 sur la classification des médulloblastomes par nanopore, Valérie Rigau et Gilles Palenzuela figurent parmi les co-auteurs. Cette étude a montré une forte concordance avec la classification de référence et a utilisé un multiplexage de six tumeurs sur MinION dans une partie du travail, ce qui soutient la faisabilité de la stratégie proposée pour la cohorte principale.

Le projet ne nécessite donc pas l’acquisition d’un nouveau séquenceur ni la création d’une infrastructure bioinformatique dédiée.

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

Chaque patient constituera son propre comparateur. Le résultat nanopore restera expérimental et ne sera pas utilisé pour établir le diagnostic clinique ni modifier la prise en charge au cours de cette première phase.

### 6.2. Population

Les patients éligibles seront inclus consécutivement afin de limiter le biais de sélection et de refléter la population réellement prise en charge.

Seront considérés comme éligibles les patients :

- pris en charge pour une lésion tumorale du SNC ;
- disposant d’un prélèvement permettant l’établissement du diagnostic de routine sur FFPE ;
- pour lesquels un fragment tumoral congelé correspondant à la même intervention est disponible sans compromettre les analyses nécessaires aux soins ;
- pour lesquels un diagnostic intégré final peut être établi selon les procédures diagnostiques habituelles.

La cohorte principale ne sera pas enrichie artificiellement en tumeurs facilement classifiables.

### 6.3. Standard diagnostique de référence

Le diagnostic intégré final sur FFPE constituera le standard de référence. Il reposera sur l’examen histologique, l’immunohistochimie, les analyses moléculaires indiquées dans le contexte clinique et l’ensemble des informations nécessaires à l’établissement du diagnostic intégré selon la classification des tumeurs du SNC en vigueur.

Les équipes réalisant le diagnostic conventionnel ne disposeront pas du résultat nanopore expérimental.

### 6.4. Prélèvement congelé

Un fragment tumoral congelé provenant de la même intervention que le matériel FFPE sera utilisé pour le test index. Lorsque cela sera possible, les fragments FFPE et congelé seront issus de territoires anatomiquement proches. Une évaluation anatomopathologique du fragment destiné au nanopore ou d’une section adjacente documentera la représentativité tumorale.

Seront notamment enregistrés : pourcentage de cellules tumorales, nécrose, proportion de tissu non tumoral, quantité et qualité de l’ADN et principales variables pré-analytiques.

### 6.5. Séquençage nanopore et choix du workflow

L’ADN natif extrait du prélèvement congelé sera séquencé sur une plateforme Oxford Nanopore disponible localement.

#### Workflow de référence

Après audit des listes de réactifs disponibles et confrontation aux protocoles actuels, le workflow de référence pour la cohorte principale est le **Rapid Barcoding Kit 24 V14 (`SQK-RBK114.24`) sur flow cell R10.4.1 (`FLO-MIN114`)**.

Ce choix repose sur plusieurs éléments :

- préparation rapide et PCR-free ;
- compatibilité avec la détection des modifications de bases ;
- nombre limité de réactifs externes ;
- possibilité de multiplexage ;
- cohérence avec les workflows publiés de classification rapide de tumeurs du SNC, notamment les travaux utilisant Rapid Barcoding dans les études de médulloblastome et dans l’adaptation R10 de Sturgeon.

Le contrôle de quantité d’ADN sera réalisé avant préparation de librairie. Le budget inclut par prudence un contrôle d’intégrité par Genomic DNA ScreenTape/TapeStation. Ce contrôle pourra être retiré ou adapté si le circuit local définitif utilise une méthode différente.

La fragmentation mécanique par **g-TUBE n’est pas prévue par défaut** dans le workflow Rapid Barcoding. Elle restera une option technique, notamment pour une éventuelle optimisation de la taille des fragments dans une sous-cohorte, et ne sera utilisée que si elle est justifiée avant le gel du protocole.

#### Alternatives auditées

**Native Barcoding V14 (`SQK-NBD114.24`).** Ce workflow est techniquement compatible avec MinION/GridION, mais nécessite des modules externes de réparation/end-prep et de ligation (`M6630`, `E7546`, `M0367`, `E6056`). Il est donc plus complexe que Rapid Barcoding et n’apporte pas, à ce stade, d’avantage évident pour la question principale.

**Ligation Sequencing Kit V14 (`SQK-LSK114`).** Il constitue une alternative pour des analyses singleplex ou une question spécifique nécessitant un workflow ligation. L’audit confirme que le module NEB actuel à utiliser est le **NEBNext Companion Module v2 `E7672`**. Les anciens modules `E7180` ne seront pas utilisés pour un protocole LSK114 actuel. Le kit `SQK-LSK114-XL` doit être budgété sur sa capacité commerciale de **48 librairies** ; le calcul antérieur fondé sur 52 réactions théoriques de réactif surestimait sa capacité.

**RRMS (Reduced Representation Methylation Sequencing).** Cette approche n’est pas retenue pour le protocole principal. Le protocole ONT RRMS actuel est conçu pour PromethION, avec quatre échantillons, environ 2 µg d’ADN par échantillon, fragmentation g-TUBE, adaptive sampling et séquençage prolongé jusqu’à 96 h avec lavages de flow cell. L’extrapolation à huit échantillons présente dans la feuille de réactifs initiale n’est pas considérée comme une hypothèse validée pour ce projet. Au-delà de son inadéquation avec l’objectif de rapidité, le budget recalculé pour 150 patients est supérieur au plafond de l’AAP avant même ajout des coûts institutionnels.

> **TO DO — WORKFLOW FINAL**  
> - Confirmer définitivement `SQK-RBK114.24` comme kit de référence : `....................`  
> - Confirmer la plateforme/configuration exacte : `....................`  
> - Confirmer la méthode d’extraction : `....................`  
> - Confirmer le QC d’intégrité ADN : `TapeStation / autre / non requis : ....................`  
> - Confirmer l’absence ou l’usage ciblé de g-TUBE : `....................`

### 6.6. Traitement bioinformatique

La chaîne bioinformatique comprendra a minima :

1. basecalling ;
2. alignement sur le génome de référence ;
3. appel de méthylation ;
4. génération des formats nécessaires aux différents classifieurs ;
5. application des modèles pré-entraînés ;
6. enregistrement des prédictions et scores de confiance ;
7. collecte des métriques de séquençage nécessaires aux analyses de cinétique.

Les versions exactes des logiciels, modèles, paramètres et seuils seront gelées avant l’analyse de la cohorte principale.

### 6.7. Stratégie de séquençage en deux modalités

#### Cohorte principale — validation diagnostique

La majorité des prélèvements sera séquencée en **6-plex**, soit six échantillons par flow cell. Cette modalité vise à obtenir un compromis entre coût et quantité de données par patient. La question principale dans cette cohorte sera la concordance diagnostique finale avec le standard de référence FFPE.

Le temps chronologique de classification observé en 6-plex ne sera pas interprété comme une estimation directe du délai peropératoire, les six bibliothèques partageant la capacité de séquençage.

#### Sous-cohorte cinétique — transposabilité peropératoire

Une sous-cohorte prédéfinie sera séquencée en **singleplex ou faible multiplexage**, afin d’estimer la cinétique réelle d’acquisition de l’information dans une configuration plus proche d’une future utilisation peropératoire.

Elle permettra de mesurer le temps jusqu’à la première classification correcte, le temps jusqu’à une classification correcte et stable et le nombre de reads, bases et CpG nécessaires.

> **TO DO — SOUS-COHORTE CINÉTIQUE**  
> - Effectif : `....................`  
> - Modalité : `singleplex / 2-plex / autre : ....................`  
> - Critères d’arrêt du run : `....................`

### 6.8. Classifieurs

Les mêmes données nanopore seront analysées indépendamment par plusieurs classifieurs publiés et pré-entraînés : crossNN/nanoDx, MethyLYZR, Sturgeon et MNP-Flex sous réserve d’accessibilité.

L’étude est conçue comme une **validation externe**. Aucun modèle ne sera entraîné, fine-tuné, recalibré ou optimisé sur la cohorte locale avant l’analyse principale. Il n’est donc pas prévu de séparation locale training/test pour le critère principal.

> **TO DO — PARAMÈTRES TECHNIQUES**  
> - Liste définitive des classifieurs : `....................`  
> - Versions exactes : `....................`  
> - Seuils de confiance : `....................`  
> - Règles de mapping methylation family/class/subclass → diagnostic clinique : `....................`

### 6.9. Analyse en aveugle

Les prédictions nanopore seront générées sans connaissance du diagnostic intégré final. Les résultats de chaque classifieur seront enregistrés avant levée de l’aveugle. Les correspondances entre les sorties des modèles et les catégories diagnostiques utilisées pour la comparaison clinique seront définies a priori et gelées avant l’analyse principale.

---

## 7. Critères de jugement

### 7.1. Critère principal

Le critère principal sera le **taux de diagnostics nanopore concordants avec le diagnostic intégré de référence**, calculé sur l’ensemble des patients pour lesquels l’analyse nanopore a été initiée.

L’analyse suivra une approche **intention-to-diagnose**. Seront considérés comme échecs pour le critère principal : échec d’extraction empêchant l’analyse, échec de séquençage, quantité de données insuffisante, absence de prédiction, prédiction sous le seuil de confiance prédéfini ou autre résultat non conclusif.

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

À chaque temps seront enregistrés : nombre de reads, quantité de bases, nombre de CpG informatifs, prédiction, score de confiance et concordance avec le diagnostic de référence.

Une **classification correcte et stable** sera définie comme la première prédiction concordante avec le diagnostic de référence qui reste concordante à l’ensemble des temps ultérieurs préspécifiés.

> **TO DO — DÉFINITION FINALE DE LA CINÉTIQUE**  
> Valider les temps d’analyse et la définition de stabilité avec l’URCE et après choix final du workflow.

---

## 9. Analyse statistique

Les analyses seront conduites au niveau du patient. Les estimations seront accompagnées d’intervalles de confiance à 95 %.

### 9.1. Analyse descriptive

Les variables quantitatives seront décrites par moyenne et écart-type ou médiane et intervalle interquartile selon leur distribution. Les variables qualitatives seront décrites par effectifs et pourcentages.

### 9.2. Critère principal

Le taux de concordance diagnostique sera estimé avec un **intervalle de confiance binomial à 95 %**. Seront rapportés séparément le diagnostic yield, la conditional accuracy et la performance globale en intention-to-diagnose, qui constituera l’analyse principale.

### 9.3. Comparaison des classifieurs

Les différents modèles étant appliqués aux mêmes patients, les comparaisons seront appariées. Les différences de proportions de diagnostics corrects entre deux modèles pourront être testées par **test de McNemar**. Une correction de multiplicité, par exemple selon Holm, sera appliquée lorsque plusieurs comparaisons seront réalisées.

Les matrices de confusion et le coefficient kappa de Cohen seront utilisés comme mesures descriptives complémentaires. Lorsque les effectifs le permettront, les performances par grande famille tumorale seront décrites, notamment par sensibilité/rappel, valeur prédictive positive et balanced accuracy.

### 9.4. Effet du temps et de la quantité de données

La probabilité d’obtenir une classification correcte sera étudiée à différents temps de séquençage. Les mesures répétées chez un même patient seront prises en compte à l’aide d’un **modèle de régression logistique à effets mixtes** ou d’une méthode équivalente pour données longitudinales. Le modèle pourra inclure le temps, le classifieur et leur interaction, avec un effet aléatoire patient.

Des analyses analogues pourront utiliser le nombre de reads, le nombre de bases ou le nombre de CpG comme variable d’exposition.

### 9.5. Facteurs associés aux échecs

Les facteurs associés à un résultat non conclusif, une discordance diagnostique ou un délai prolongé seront étudiés de façon exploratoire. Les variables candidates incluront notamment cellularité tumorale, nécrose, quantité/qualité de l’ADN, type tumoral et paramètres de séquençage. Le nombre de variables introduites dans les modèles multivariés sera limité en fonction du nombre d’événements observés afin d’éviter le surajustement.

### 9.6. Données manquantes

Aucune imputation ne sera réalisée pour le critère principal. Les résultats nanopore non conclusifs resteront intégrés comme échecs dans l’analyse principale. Une analyse de sensibilité sera réalisée parmi les seuls cas techniquement évaluables.

---

## 10. Taille de cohorte

La taille définitive de la cohorte sera déterminée avec l’URCE. Deux approches sont envisagées : une approche **estimative**, visant à estimer une concordance attendue élevée avec une précision prédéfinie, ou une approche **confirmatoire**, visant à démontrer que la concordance dépasse un seuil minimal cliniquement acceptable.

Les simulations budgétaires explorent des effectifs compris entre environ 80 et 200 patients. Une cohorte de l’ordre de 120–150 patients constitue actuellement un scénario de travail plausible mais **ne doit pas être considérée comme l’effectif statistique définitif**.

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

Les séquenceurs et l’infrastructure bioinformatique étant déjà disponibles localement, le budget incrémental repose principalement sur la prise en charge du fragment congelé/CRB, l’extraction et le QC de l’ADN, les kits de librairie, les flow cells, les consommables et les coûts institutionnels obligatoires.

### 13.1. Hypothèses de référence après audit des réactifs

Le modèle budgétaire utilise actuellement :

- `FLO-MIN114` : **740 € HT / flow cell** ;
- `SQK-RBK114.24` : **730 € HT / kit**, six réactions complètes par kit ;
- QIAamp Fast DNA Tissue Kit : **296 € / 50 extractions** ;
- Qubit dsDNA HS : **135,65 € / 100 dosages** ;
- Genomic DNA Reagents `5067-5366` : **186 € HT / 105 échantillons** ;
- Genomic DNA ScreenTape `5067-5365` : **270 € HT / 105 échantillons** si les QC sont regroupés efficacement ;
- petits consommables : **4 € / patient** ;
- CRB : scénario provisoire bas et haut fondé sur la grille publique, en attente d’un devis spécifique.

L’audit a corrigé plusieurs erreurs des tableaux de départ. Les coûts TapeStation « pool-8 » avaient notamment été sous-estimés. Le budget est désormais calculé sur le **nombre de packs réellement à acheter**, et non par extrapolation d’un coût proportionnel par pool. Pour 150 patients, deux packs de Genomic DNA Reagents et deux packs de Genomic DNA ScreenTape sont ainsi prévus, soit **912 € HT**.

Le g-TUBE `520104` est valorisé à **3 150 € HT pour 100 unités**, soit 31,50 € HT par patient lorsqu’il est utilisé. Il reste toutefois **désactivé dans le scénario principal**, car une fragmentation mécanique n’est pas obligatoire pour le workflow Rapid Barcoding retenu.

### 13.2. Scénario de travail actuel

Dans le scénario actuel de **150 patients dont 12 en 2-plex et 138 en 6-plex**, le modèle nécessite :

- 29 flow cells `FLO-MIN114` ;
- 5 kits `SQK-RBK114.24` ;
- 3 kits d’extraction QIAamp ;
- 2 kits Qubit ;
- 2 packs Genomic DNA Reagents ;
- 2 packs Genomic DNA ScreenTape.

Le coût technique estimatif, marge technique de 10 % incluse et hors coûts institutionnels encore inconnus, est de :

- **40,7 k€** avec l’hypothèse CRB basse ;
- **50,9 k€** avec l’hypothèse CRB haute.

Le coût moyen technique correspondant est d’environ **271 € HT/patient** dans le scénario CRB bas et **339 € HT/patient** dans le scénario CRB haut.

### 13.3. Analyse des workflows alternatifs

L’audit confirme que le coût ne doit pas être évalué uniquement à partir du prix du kit ONT.

- **Native Barcoding V14** nécessite en plus des réactifs de réparation/end-prep et ligation. Il reste une alternative réaliste mais plus complexe.
- **LSK114** nécessite le NEB Companion Module v2 `E7672`; le coût du kit LSK standard est de 105 € HT par librairie avant flow cell et réactifs externes.
- **RRMS** implique PromethION, g-TUBE, réactifs NEB, extensions de buffer et lavages répétés. Pour 150 patients, un scénario conservateur recalculé atteint environ **74,4 k€ HT** avec l’hypothèse CRB basse et une marge de 10 %, avant promotion, méthodologie, personnel ou autres coûts institutionnels. Il n’est donc pas compatible avec le plafond de 60 k€ et n’est pas retenu.

Le classeur `budget_previsionnel_AAP_JC2026.xlsx` permet de modifier les hypothèses et de recalculer automatiquement les coûts.

> **TO DO — COÛTS INSTITUTIONNELS / MARCHÉ CHU**  
> - Prix marché `FLO-MIN114` : `.................... € HT`  
> - Prix marché `SQK-RBK114.24` : `.................... € HT`  
> - Devis CRB / patient, fragment prospectif ~20–30 mg : `.................... € HT`  
> - Prix/méthode définitive d’extraction et QC : `....................`  
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
- validation technique du workflow local.

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

Les échecs seront enregistrés prospectivement et inclus dans l’analyse principale en intention-to-diagnose.

### Déséquilibre entre classes tumorales

L’inclusion consécutive reflétera la distribution clinique réelle. Les analyses par classe seront considérées comme secondaires lorsque les effectifs sont faibles.

### Évolution des classifieurs

Les modèles et versions utilisés seront gelés avant l’analyse principale. Toute version ultérieure sera évaluée séparément comme analyse exploratoire.

### Risque de surapprentissage

Aucun réentraînement ni optimisation sur la cohorte locale ne sera autorisé pour l’analyse principale.

### Choix du workflow de librairie

Le choix Rapid Barcoding est justifié par la rapidité, la simplicité et le coût. Il sera néanmoins verrouillé avant l’ouverture de l’étude. Si une alternative Native Barcoding ou LSK est finalement préférée pour des raisons analytiques, le budget et les procédures seront recalculés avant inclusion.

### Budget

Le coût dépend fortement du prix réel des flow cells et du coût CRB. Avec les prix catalogue actuels, le scénario CRB haut laisse peu de marge sous le plafond de l’AAP une fois ajoutés les coûts institutionnels. L’obtention rapide des prix marché CHU et du devis CRB est donc un jalon critique.

---

## 16. Résultats attendus

L’étude doit permettre d’obtenir une réponse quantitative à la question principale : **dans quelle proportion des cas un workflow nanopore sur tissu congelé reproduit-il le diagnostic intégré établi en routine sur FFPE ?**

Elle permettra également de mesurer le taux réel de résultats non conclusifs, comparer plusieurs classifieurs indépendants, identifier les types d’erreurs et leurs déterminants, définir la quantité minimale de données nécessaire à une classification fiable, mesurer une cinétique réaliste dans une configuration compatible avec une future utilisation peropératoire et établir un coût par patient dans les conditions locales.

Ces résultats doivent permettre de déterminer si le niveau de fiabilité obtenu est suffisant pour passer à une étude d’impact clinique où le résultat moléculaire serait rendu pendant l’intervention et évalué comme aide à la décision chirurgicale.

---

## 17. Perspectives et effet levier

Le projet est conçu comme une étape de validation préalable à un changement potentiel de temporalité diagnostique et, à terme, de prise en charge chirurgicale.

Si la concordance diagnostique, le taux de succès technique et les délais sont compatibles avec les objectifs prédéfinis, une seconde étude prospective pourra tester le workflow en situation peropératoire, avec implication directe des équipes de neurochirurgie et de neuropathologie.

Cette seconde phase devra répondre à une question différente : **une information moléculaire disponible pendant l’intervention modifie-t-elle de manière pertinente la stratégie chirurgicale et améliore-t-elle la qualité de la prise en charge ?**

Les critères cliniques pertinents devront alors inclure notamment : modification de la stratégie opératoire prévue, étendue de résection obtenue, nécessité d’une chirurgie de second look, nouveaux déficits neurologiques, fonction, qualité de vie et, à plus long terme, résultats oncologiques.

L’effet levier attendu comprend :

- une publication princeps portant sur la validation prospective du workflow nanopore local ;
- la constitution d’un pipeline reproductible et documenté ;
- une base méthodologique pour une étude prospective peropératoire ;
- la possibilité d’un futur projet multicentrique ou d’un AAP de plus grande envergure ;
- une structuration renforcée entre neuropathologie, PMMG, bioinformatique et neurochirurgie.

---

## 18. Valorisation scientifique

La publication principale devra présenter de manière transparente l’ensemble du workflow, incluant les échecs techniques et les résultats non conclusifs. Le manuscrit pourra être structuré comme une étude de validation diagnostique externe avec comparaison de plusieurs modèles pré-entraînés.

Des analyses complémentaires pourront porter sur les classifieurs, les cas discordants, la relation entre cellularité et performance, les métriques de time-to-diagnosis, CNV/MGMT et une analyse médico-économique exploratoire.

Le porteur du projet devra être premier auteur de la publication princeps conformément aux exigences de l’AAP.

---

## 19. Bibliographie principale

La bibliographie complète et les références BibTeX sont disponibles dans `references.md`, `references.bib`, `surgical_impact_references.bib` et `montpellier_local_references.bib`.

Références particulièrement structurantes :

1. Capper D, et al. *Nature*. 2018. DNA methylation-based classification of central nervous system tumours.
2. Louis DN, et al. *Neuro-Oncology*. 2021. WHO Classification of Tumors of the Central Nervous System.
3. Sahm F, et al. *Neuro-Oncology*. 2023. EANO guideline on molecular diagnostic tools for CNS tumours.
4. Djirackor L, et al. *Neuro-Oncology Advances*. 2021. Intraoperative DNA methylation classification of brain tumors impacts neurosurgical strategy.
5. Kuschel LP, et al. *Neuropathology and Applied Neurobiology*. 2023. Robust methylation-based classification of brain tumours using nanopore sequencing.
6. Vermeulen C, et al. *Nature*. 2023. Ultra-fast deep-learned CNS tumour classification during surgery.
7. Drexler R, et al. *Neuro-Oncology*. 2023. DNA methylation subclasses predict the benefit from gross total tumor resection in IDH-wildtype glioblastoma patients.
8. Brändl B, et al. *Nature Medicine*. 2025. Rapid brain tumor classification from sparse epigenomic data.
9. Wu et al. *BMC Medicine*. 2025. Rapid diagnosis of adult-type diffuse glioma using a layered scheme.
10. Patel A, et al. *Nature Medicine*. 2025. Prospective multicenter validation of Rapid-CNS2.
11. Emiliani et al. *Genome Medicine*. 2025. Nanopore-based random genomic sampling for intraoperative molecular diagnosis.
12. Yuan D, et al. *Nature Cancer*. 2025. crossNN.
13. Deacon S, et al. *Neuro-Oncology*. 2025. ROBIN.
14. Drexler R, Lim M, Hervey-Jumper SL. *Neuro-Oncology*. 2025. Molecular-based decision-making in glioblastoma surgery.
15. Filser M, et al. *Neuro-Oncology*. 2025. Nanopore sequencing as a cutting-edge technology for medulloblastoma classification.
16. Aldape K, et al. *Neuro-Oncology Advances*. 2025. cIMPACT-NOW update 9 on genome-wide DNA methylation profiling.
17. PIONEER Consortium / RANO resect. *Lancet Oncology*. 2026. Comprehensive framework for glioma surgery, parts 1 and 2.
18. Sie M, et al. *Neuro-Oncology*. 2026. How “Sturgeon” guides the surgeon in pediatric neuro-oncology.

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

- [ ] Confirmation finale du workflow `SQK-RBK114.24` / `FLO-MIN114`.
- [ ] Méthode d’extraction finale.
- [ ] QC d’intégrité de l’ADN.
- [ ] Multiplexage définitif de la sous-cohorte cinétique.
- [ ] Classifieurs et versions.
- [ ] Seuils de confiance.
- [ ] Mapping classes → diagnostic clinique.
- [ ] Définition finale de classification correcte et stable.

---

## 21. Statut de la version v0.1

Cette version contient une trame scientifique suffisamment complète pour servir de base à la rédaction du dossier JC 2026. Le rationnel clinique est désormais centré sur l’objectif translationnel du projet : valider localement une classification moléculaire rapide susceptible, dans une phase ultérieure, d’être utilisée comme aide à la décision chirurgicale. L’audit des réactifs a consolidé le choix d’un workflow Rapid Barcoding pour la planification et amélioré le réalisme budgétaire. Les inconnues restantes sont principalement institutionnelles, réglementaires et quantitatives ; elles ne remettent pas en cause la question scientifique ni le design général du projet.