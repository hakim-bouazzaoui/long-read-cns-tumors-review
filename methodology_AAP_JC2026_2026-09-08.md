# Méthodologie scientifique — validation du séquençage nanopore pour le diagnostic des tumeurs du système nerveux central

**Projet :** AAP Jeunes Chercheurs Tremplin 2026 — CHU Montpellier  
**Version :** 2026-09-08  
**Statut :** document de travail méthodologique à discuter avec l’URCE

## 1. Objectif et hypothèse

Le diagnostic des tumeurs du système nerveux central (SNC) repose sur une intégration des données morphologiques, immunohistochimiques et moléculaires. Au CHU de Montpellier, ce diagnostic est établi en routine à partir de tissu fixé et inclus en paraffine (FFPE), selon les procédures diagnostiques en vigueur.

Le séquençage nanopore permet, à partir d’ADN natif, d’obtenir rapidement un profil de méthylation à l’échelle du génome, exploitable par plusieurs classifieurs de tumeurs du SNC déjà publiés et pré-entraînés.

L’objectif principal de cette étude est d’évaluer, dans les conditions réelles de prise en charge au CHU de Montpellier, si l’analyse nanopore d’un prélèvement tumoral congelé provenant de la même intervention permet d’obtenir une classification diagnostique concordante avec le diagnostic intégré final établi en routine sur FFPE.

### Hypothèse principale

Nous faisons l’hypothèse que l’analyse nanopore sur tissu congelé permet d’obtenir, avec un taux élevé de succès technique, un diagnostic concordant avec le diagnostic intégré de référence établi sur FFPE.

L’étude vise également à déterminer la quantité minimale de données et le temps minimal de séquençage nécessaires pour obtenir un résultat fiable et stable.

Cette étude constitue une étape préalable de validation avant toute évaluation du dispositif en situation peropératoire.

## 2. Schéma de l’étude

Il s’agira d’une **étude prospective, monocentrique, comparative et appariée de performance diagnostique**.

Pour chaque patient inclus, deux analyses seront considérées :

- le **test de référence**, correspondant au diagnostic intégré final établi dans le circuit diagnostique habituel sur tissu FFPE ;
- le **test index**, correspondant à l’analyse moléculaire par séquençage nanopore réalisée sur un fragment tumoral congelé issu de la même intervention.

Chaque patient constituera ainsi son propre comparateur.

Le résultat nanopore ne sera pas utilisé pour établir le diagnostic clinique ni pour modifier la prise en charge du patient au cours de cette première phase de validation.

L’analyse principale sera réalisée au niveau du patient. En cas de disponibilité de plusieurs prélèvements pour un même patient, les règles de sélection du prélèvement utilisé pour l’analyse principale seront définies avant le début de l’étude.

## 3. Population étudiée

Les patients éligibles seront inclus de manière consécutive afin de limiter le biais de sélection et de refléter la population effectivement prise en charge.

Seront considérés comme éligibles les patients :

- pris en charge pour une lésion tumorale du SNC ;
- disposant d’un prélèvement permettant l’établissement du diagnostic de routine sur FFPE ;
- pour lesquels un fragment tumoral congelé correspondant à la même intervention est disponible sans compromettre les analyses nécessaires aux soins ;
- pour lesquels un diagnostic intégré final peut être établi selon les procédures diagnostiques habituelles.

La cohorte ne sera pas constituée en sélectionnant préférentiellement les tumeurs facilement classifiables.

La distribution des différentes entités tumorales sera décrite afin d’évaluer la représentativité de la population étudiée.

Des analyses secondaires pourront être consacrées aux cas rares, difficiles ou discordants.

## 4. Standard diagnostique de référence

Le **diagnostic intégré final sur FFPE** constituera le standard de référence.

Il sera établi dans le cadre du soin courant à partir :

- de l’examen histologique ;
- de l’immunohistochimie ;
- des analyses moléculaires réalisées selon l’indication clinique ;
- et de l’ensemble des informations nécessaires à l’établissement du diagnostic intégré selon la classification des tumeurs du SNC en vigueur.

Le diagnostic de référence sera celui retenu à l’issue du processus diagnostique habituel.

Les équipes réalisant et interprétant le diagnostic conventionnel ne disposeront pas du résultat nanopore expérimental.

## 5. Prélèvement destiné à l’analyse nanopore

Un fragment tumoral congelé provenant de la même intervention que le matériel utilisé pour le diagnostic FFPE sera analysé.

Lorsque cela sera techniquement possible, les fragments congelé et FFPE seront issus de territoires tumoraux anatomiquement proches afin de limiter l’effet de l’hétérogénéité intratumorale.

La représentativité tumorale du prélèvement destiné au nanopore sera documentée à partir d’une évaluation anatomopathologique du fragment ou d’une section adjacente.

Seront notamment enregistrés :

- le pourcentage estimé de cellules tumorales ;
- la présence et l’étendue de la nécrose ;
- la proportion de tissu non tumoral ;
- la quantité d’ADN obtenue ;
- les paramètres de qualité de l’ADN ;
- les principales variables pré-analytiques susceptibles d’influencer le résultat.

Ces paramètres seront conservés pour les analyses des facteurs associés aux échecs ou aux discordances.

## 6. Séquençage nanopore et traitement bioinformatique

L’ADN natif extrait du prélèvement congelé sera séquencé par technologie Oxford Nanopore selon un protocole standardisé.

L’analyse bioinformatique comprendra :

1. le basecalling ;
2. l’alignement des lectures sur le génome de référence ;
3. l’identification des CpG couverts et l’estimation de leur état de méthylation ;
4. la génération des formats nécessaires aux différents classifieurs ;
5. l’application des modèles pré-entraînés ;
6. l’enregistrement des prédictions et des scores de confiance à différents temps de séquençage.

Les versions des logiciels, modèles, génome de référence, paramètres et seuils de décision seront documentés et **gelés avant l’analyse de la cohorte principale**.

La chaîne bioinformatique sera versionnée afin d’assurer la reproductibilité de l’analyse.

## 7. Classifieurs évalués

Plusieurs classifieurs de méthylation déjà publiés seront appliqués indépendamment aux mêmes données nanopore.

Les méthodes envisagées comprennent notamment :

- **crossNN**, notamment via l’écosystème nanoDx ;
- **MethyLYZR** ;
- **Sturgeon** ;
- **MNP-Flex**, sous réserve de son accessibilité dans le cadre du projet.

La liste définitive sera arrêtée avant le début des analyses comparatives.

### Absence d’entraînement sur la cohorte étudiée

L’étude est conçue comme une **validation externe de modèles pré-entraînés**.

Aucun modèle ne sera entraîné à partir de la cohorte locale pour l’analyse principale.

En particulier, aucune procédure de :

- réentraînement ;
- fine-tuning ;
- sélection de variables ;
- optimisation des seuils ;
- calibration sur les résultats de la cohorte ;
- ou modification des modèles en fonction du diagnostic de référence

ne sera réalisée avant l’analyse principale.

Il n’est donc pas nécessaire de séparer la cohorte en sous-ensembles d’entraînement et de test.

Cette stratégie permet d’évaluer directement la transférabilité des modèles publiés aux données produites localement.

## 8. Procédure d’analyse en aveugle

Les prédictions nanopore seront générées sans connaissance du diagnostic intégré final.

Pour chaque cas, les résultats des différents classifieurs seront enregistrés avant la levée de l’aveugle.

Les règles permettant de convertir les sorties propres à chaque modèle — methylation family, class ou subclass — vers les catégories diagnostiques utilisées pour la comparaison clinique seront définies **a priori**.

Ce dictionnaire de correspondance sera gelé avant l’analyse principale.

Les éventuelles discordances feront l’objet d’une revue secondaire après calcul des performances principales, sans modification rétrospective de la classification utilisée pour l’analyse primaire.

## 9. Critère de jugement principal

Le critère principal sera le :

**taux de diagnostics nanopore concordants avec le diagnostic intégré de référence, calculé sur l’ensemble des patients pour lesquels l’analyse nanopore a été initiée.**

La concordance principale sera évaluée à un niveau diagnostique prédéfini et cliniquement pertinent.

Le numérateur correspondra au nombre de patients pour lesquels le workflow nanopore fournit un diagnostic considéré comme concordant avec le diagnostic intégré final.

Le dénominateur correspondra à l’ensemble des patients inclus dans l’analyse principale.

Cette analyse suivra une approche **intention-to-diagnose**.

Ainsi, seront comptabilisés comme échecs pour le critère principal :

- les échecs d’extraction empêchant l’analyse ;
- les échecs de séquençage ;
- une quantité de données insuffisante ;
- l’absence de prédiction ;
- une prédiction dont le score est inférieur au seuil prédéfini ;
- tout autre résultat non conclusif.

Cette approche permet d’évaluer la performance réelle de l’ensemble du workflow et non uniquement celle du classifieur lorsque celui-ci produit un résultat.

## 10. Critères de jugement secondaires

Les critères secondaires comprendront notamment :

### Performance diagnostique

- taux de résultats techniquement exploitables ;
- taux de classifications conclusives ;
- concordance avec le diagnostic de référence parmi les seuls résultats conclusifs ;
- performance propre à chacun des classifieurs ;
- concordance entre les différents classifieurs ;
- performances selon les principales familles tumorales ;
- distribution et nature des erreurs diagnostiques.

### Performance temporelle

- temps jusqu’à la première classification correcte ;
- temps jusqu’à l’obtention d’une classification correcte et stable ;
- proportion de diagnostics corrects après différents temps de séquençage.

### Quantité minimale de données

- nombre de lectures nécessaires ;
- nombre de bases séquencées ;
- nombre de CpG informatifs ;
- couverture nécessaire à l’obtention d’une classification fiable.

### Faisabilité

- taux d’échec technique ;
- délai total entre extraction de l’ADN et résultat ;
- temps de calcul bioinformatique ;
- consommation de réactifs ;
- coût analytique par prélèvement.

## 11. Analyse de la cinétique de classification

L’une des particularités du séquençage nanopore est de produire les données en temps réel.

Les données de chaque run seront donc analysées de manière cumulative à plusieurs temps prédéfinis, par exemple :

**5, 10, 15, 30, 45 et 60 minutes**, puis au terme du séquençage.

Les temps définitifs seront fixés avant l’analyse.

Pour chaque temps seront enregistrés :

- le nombre de lectures disponibles ;
- le nombre de bases séquencées ;
- le nombre de CpG informatifs ;
- la prédiction de chaque classifieur ;
- son score de confiance ;
- la concordance ou non avec le diagnostic de référence.

Le **temps jusqu’à classification correcte et stable** sera défini comme le premier temps auquel le diagnostic obtenu est concordant avec le diagnostic de référence et reste concordant lors de l’ensemble des évaluations ultérieures prévues pour le même run.

Cette définition évitera de considérer comme succès une prédiction correcte mais transitoire.

## 12. Analyse des discordances

Toutes les discordances entre le résultat nanopore et le diagnostic intégré seront documentées.

Elles seront secondairement classées en plusieurs catégories :

- erreur de famille tumorale ;
- erreur de classe ou subclass de méthylation sans modification du diagnostic clinique principal ;
- discordance susceptible d’avoir un impact diagnostique ;
- résultat nanopore non conclusif ;
- discordance possiblement expliquée par la qualité ou la composition du prélèvement ;
- discordance pouvant évoquer une hétérogénéité tumorale.

Cette analyse aura un objectif explicatif et ne modifiera pas rétrospectivement le résultat de l’analyse principale.

## 13. Analyses statistiques

Les analyses seront réalisées principalement au niveau du patient.

Toutes les estimations seront accompagnées d’un **intervalle de confiance à 95 %**.

Un plan d’analyse statistique détaillé sera finalisé avant le gel de la base de données.

### 13.1. Description de la population

Les variables quantitatives seront décrites par moyenne et écart-type ou médiane et intervalle interquartile selon leur distribution.

Les variables qualitatives seront présentées sous forme d’effectifs et de pourcentages.

La distribution des diagnostics, la qualité des prélèvements et les principales variables pré-analytiques seront décrites.

### 13.2. Analyse du critère principal

Le taux de concordance diagnostique du workflow nanopore avec le diagnostic intégré de référence sera estimé avec son **intervalle de confiance binomial à 95 %**.

L’analyse principale inclura les résultats non conclusifs comme échecs diagnostiques.

Une analyse secondaire évaluera la concordance conditionnelle parmi les seuls cas ayant produit un résultat nanopore conclusif.

Seront donc rapportés séparément :

1. le **diagnostic yield**, correspondant à la proportion de patients ayant obtenu un résultat nanopore conclusif ;
2. la **conditional accuracy**, correspondant à la proportion de diagnostics corrects parmi les résultats conclusifs ;
3. la **performance globale en intention-to-diagnose**, qui constituera l’analyse principale.

Cette distinction permet de séparer la performance intrinsèque du classifieur de celle de l’ensemble du processus analytique.

### 13.3. Comparaison des classifieurs

Les différents classifieurs étant appliqués aux **mêmes patients**, toutes les comparaisons seront considérées comme appariées.

Les différences de taux de succès diagnostique entre deux classifieurs seront analysées à l’aide du **test de McNemar**.

En cas de comparaisons multiples entre plusieurs modèles, une correction adaptée, telle que la procédure de Holm, sera appliquée.

La concordance entre les prédictions catégorielles et le diagnostic de référence pourra également être décrite à l’aide du **coefficient kappa de Cohen** et de matrices de confusion.

Lorsque les effectifs par catégorie seront suffisants, seront également rapportées :

- sensibilité par classe ou famille tumorale ;
- valeur prédictive positive par classe ;
- rappel macro-moyenné ;
- exactitude équilibrée.

Ces analyses seront considérées comme secondaires compte tenu de la répartition nécessairement déséquilibrée des différentes entités tumorales.

### 13.4. Effet du temps et de la quantité de données

La probabilité d’obtenir une classification correcte sera étudiée à chaque temps de séquençage pour chacun des modèles.

Les données répétées provenant d’un même patient seront prises en compte à l’aide d’un **modèle de régression logistique à effets mixtes** ou d’une méthode équivalente pour données longitudinales.

Le modèle pourra comprendre :

- le temps de séquençage ;
- le classifieur ;
- l’interaction entre temps et classifieur ;

avec un effet aléatoire lié au patient.

Cette analyse permettra de déterminer si les performances augmentent significativement avec la quantité de données et si cette cinétique diffère selon les classifieurs.

Les mêmes analyses pourront être répétées en utilisant comme exposition :

- le nombre de lectures ;
- le nombre de bases ;
- ou le nombre de CpG informatifs

plutôt que le seul temps de séquençage.

### 13.5. Facteurs associés aux échecs diagnostiques

Les facteurs associés à :

- un résultat non conclusif ;
- une discordance diagnostique ;
- ou un délai prolongé avant classification correcte

seront étudiés de manière exploratoire.

Les variables candidates comprendront notamment :

- cellularité tumorale ;
- proportion de nécrose ;
- quantité d’ADN ;
- qualité de l’ADN ;
- nombre de CpG obtenus ;
- type tumoral ;
- caractéristiques pré-analytiques.

Compte tenu du nombre attendu d’échecs, le nombre de variables introduites simultanément dans les modèles multivariés sera limité afin d’éviter le surajustement.

Si nécessaire, des approches de régression pénalisée pourront être utilisées.

Ces analyses resteront exploratoires et ne serviront pas à modifier les modèles de classification évalués.

## 14. Taille de la cohorte

La taille définitive de la cohorte sera déterminée avec l’URCE à partir de l’objectif statistique retenu et du recrutement réalisable pendant la durée de l’étude.

Deux approches principales peuvent être envisagées.

### Approche fondée sur la précision

L’effectif peut être choisi afin d’estimer une concordance attendue élevée, par exemple proche de 95 %, avec une largeur d’intervalle de confiance jugée suffisamment précise.

Dans cette approche, des cohortes de l’ordre de **80 à 150 patients** permettent déjà une estimation informative de la performance globale, la précision augmentant avec l’effectif.

### Approche fondée sur un seuil minimal de performance

Une seconde possibilité consiste à définir avant l’étude un taux minimal de concordance considéré comme nécessaire pour poursuivre le développement clinique de la méthode.

L’hypothèse statistique pourrait alors prendre la forme :

**H0 : p ≤ p0**

contre

**H1 : p > p0**

où `p0` représente le niveau minimal de performance jugé acceptable.

L’effectif serait alors calculé en fonction :

- du seuil minimal `p0` ;
- de la performance attendue ;
- du risque alpha ;
- de la puissance souhaitée ;
- et du taux anticipé de prélèvements non évaluables.

Une cohorte plus importante, potentiellement de l’ordre de **150 à 200 patients**, pourrait être nécessaire si l’objectif retenu est de démontrer formellement que la performance dépasse un seuil élevé.

Le choix entre une étude principalement **estimative** et une étude reposant sur un **seuil décisionnel prédéfini** sera arrêté avec l’URCE avant le dépôt définitif.

## 15. Gestion des données manquantes et analyses de sensibilité

Aucune imputation ne sera réalisée pour le critère diagnostique principal.

Les résultats nanopore non conclusifs seront intégrés comme échecs conformément à l’analyse intention-to-diagnose.

Le nombre et les causes des données manquantes concernant les variables secondaires seront décrits.

Une analyse de sensibilité limitée aux cas techniquement évaluables sera réalisée afin de distinguer :

- les performances de l’ensemble du workflow ;
- et les performances conditionnelles des classifieurs lorsqu’une donnée exploitable est disponible.

## 16. Reproductibilité et traçabilité

Afin de garantir la reproductibilité des résultats :

- les versions exactes des modèles seront conservées ;
- le code utilisé pour la préparation et l’analyse des données sera versionné ;
- les paramètres de chaque pipeline seront enregistrés ;
- les règles de correspondance entre classes moléculaires et diagnostics seront définies avant l’analyse ;
- les sorties brutes et intermédiaires nécessaires à la vérification des résultats seront conservées selon les règles applicables aux données de recherche.

La cohorte ne sera pas utilisée pour optimiser rétrospectivement les modèles évalués.

Toute analyse exploratoire réalisée après l’analyse principale sera explicitement identifiée comme telle.

## 17. Perspectives translationnelles

Cette étude ne vise pas à démontrer directement l’intérêt clinique d’une classification peropératoire.

Elle vise d’abord à établir trois éléments nécessaires avant une telle évaluation :

1. **la concordance diagnostique du nanopore avec le diagnostic intégré conventionnel sur FFPE ;**
2. **la robustesse comparative de plusieurs classifieurs pré-entraînés sur les prélèvements locaux ;**
3. **le délai et la quantité de données nécessaires pour obtenir un résultat correct et stable.**

Si les seuils prédéfinis de performance diagnostique, de taux de succès technique et de rapidité sont atteints, ces résultats permettront de construire une seconde étude prospective en conditions peropératoires, en collaboration avec les équipes de neurochirurgie et de neuropathologie.

Cette seconde étape pourra alors évaluer non plus uniquement la performance analytique du nanopore, mais sa capacité à fournir une information moléculaire suffisamment précoce pour être intégrée à la décision chirurgicale.
