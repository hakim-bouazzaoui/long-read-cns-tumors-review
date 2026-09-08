# Méthodologie scientifique — validation du séquençage nanopore pour le diagnostic des tumeurs du système nerveux central

**Projet :** AAP Jeunes Chercheurs Tremplin 2026 — CHU Montpellier  
**Version :** 2026-09-08 — v2  
**Statut :** document de travail méthodologique à discuter avec l’URCE  

## 1. Objectif et hypothèse

Le diagnostic des tumeurs du système nerveux central (SNC) repose sur l’intégration des données morphologiques, immunohistochimiques et moléculaires. Au CHU de Montpellier, ce diagnostic est établi en routine à partir de tissu fixé et inclus en paraffine (FFPE), selon les procédures diagnostiques en vigueur.

Le séquençage nanopore permet, à partir d’ADN natif, d’obtenir un profil de méthylation à l’échelle du génome exploitable par plusieurs classifieurs de tumeurs du SNC déjà publiés et pré-entraînés.

### Objectif principal

Évaluer, dans les conditions réelles de prise en charge au CHU de Montpellier, si l’analyse nanopore d’un prélèvement tumoral congelé provenant de la même intervention permet d’obtenir une classification diagnostique concordante avec le diagnostic intégré final établi en routine sur FFPE.

### Hypothèse principale

Nous faisons l’hypothèse que l’analyse nanopore sur tissu congelé permet d’obtenir, avec un taux élevé de succès technique, un diagnostic concordant avec le diagnostic intégré de référence établi sur FFPE.

### Objectifs secondaires principaux

L’étude visera également à :

1. comparer les performances de plusieurs classifieurs pré-entraînés appliqués aux mêmes données nanopore ;
2. caractériser les causes d’échec, de non-classification et de discordance ;
3. déterminer la quantité de données nécessaire à une classification correcte et stable ;
4. estimer, dans une sous-cohorte dédiée, la cinétique réelle de classification dans des conditions de séquençage compatibles avec une future transposition peropératoire.

Cette étude constitue une étape préalable de validation avant toute utilisation du résultat nanopore dans la prise en charge clinique ou en situation extemporanée.

---

## 2. Schéma de l’étude

Il s’agira d’une **étude prospective, monocentrique, comparative et appariée de performance diagnostique**.

Pour chaque patient inclus, deux analyses seront considérées :

- le **standard de référence**, correspondant au diagnostic intégré final établi dans le circuit diagnostique habituel sur tissu FFPE ;
- le **test index**, correspondant à l’analyse moléculaire par séquençage nanopore réalisée sur un fragment tumoral congelé issu de la même intervention.

Chaque patient constituera son propre comparateur.

Le résultat nanopore ne sera pas utilisé pour établir le diagnostic clinique ni pour modifier la prise en charge du patient au cours de cette première phase de validation.

### 2.1. Deux modalités de séquençage complémentaires

Le projet comportera deux modalités préspécifiées, répondant à deux questions différentes.

#### Cohorte principale — validation diagnostique

La majorité des prélèvements sera séquencée en **multiplexage de six échantillons par flow cell (6-plex)**. Cette modalité vise à maximiser l’efficience économique tout en générant suffisamment de données par patient pour l’évaluation diagnostique.

La question principale dans cette cohorte est la **concordance diagnostique finale** entre le workflow nanopore et le diagnostic intégré de référence sur FFPE.

Les données de cette cohorte permettront également d’étudier la relation entre performance et quantité de données obtenue. En revanche, le temps chronologique observé en 6-plex ne sera pas interprété comme une estimation directe du délai attendu en situation peropératoire, puisque six bibliothèques se partagent la capacité de séquençage de la flow cell.

#### Sous-cohorte cinétique — transposabilité peropératoire

Une **sous-cohorte prédéfinie** sera séquencée en **singleplex ou en faible multiplexage**, selon le protocole définitivement retenu avant le début de l’étude.

Cette sous-cohorte aura pour objectif spécifique de mesurer la cinétique réelle d’acquisition de l’information moléculaire dans une configuration se rapprochant d’une future utilisation peropératoire.

Elle permettra d’estimer :

- le temps jusqu’à la première classification correcte ;
- le temps jusqu’à une classification correcte et stable ;
- le nombre de reads, de bases et de CpG nécessaires à cette classification ;
- les différences de cinétique entre classifieurs.

L’effectif et le niveau exact de multiplexage de cette sous-cohorte seront arrêtés avec l’URCE et en fonction du budget définitif. Ils seront fixés **avant toute analyse des performances**.

---

## 3. Population étudiée

Les patients éligibles seront inclus de manière consécutive afin de limiter le biais de sélection et de refléter la population effectivement prise en charge.

Seront considérés comme éligibles les patients :

- pris en charge pour une lésion tumorale du SNC ;
- disposant d’un prélèvement permettant l’établissement du diagnostic de routine sur FFPE ;
- pour lesquels un fragment tumoral congelé correspondant à la même intervention est disponible sans compromettre les analyses nécessaires aux soins ;
- pour lesquels un diagnostic intégré final peut être établi selon les procédures diagnostiques habituelles.

La cohorte ne sera pas constituée en sélectionnant préférentiellement les tumeurs facilement classifiables.

La distribution des différentes entités tumorales sera décrite afin d’évaluer la représentativité de la population étudiée.

La sélection des patients de la sous-cohorte cinétique suivra une règle prédéfinie afin d’éviter une sélection a posteriori de cas favorables.

---

## 4. Standard diagnostique de référence

Le **diagnostic intégré final sur FFPE** constituera le standard de référence.

Il sera établi dans le cadre du soin courant à partir :

- de l’examen histologique ;
- de l’immunohistochimie ;
- des analyses moléculaires réalisées selon l’indication clinique ;
- et de l’ensemble des informations nécessaires à l’établissement du diagnostic intégré selon la classification des tumeurs du SNC en vigueur.

Le diagnostic de référence sera celui retenu à l’issue du processus diagnostique habituel.

Les équipes réalisant et interprétant le diagnostic conventionnel ne disposeront pas du résultat nanopore expérimental.

---

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

---

## 6. Séquençage nanopore et traitement bioinformatique

L’ADN natif extrait du prélèvement congelé sera séquencé par technologie Oxford Nanopore selon un protocole standardisé permettant de préserver l’information de méthylation.

### 6.1. Cohorte principale

Les bibliothèques de la cohorte principale seront préparées avec un système de barcoding sans amplification et regroupées par **six patients par flow cell**, sauf impossibilité technique documentée.

Le séquençage sera poursuivi jusqu’à obtention de la quantité de données prévue par le protocole. Les données resteront disponibles avec leur horodatage afin de permettre des analyses rétrospectives par quantité cumulée de données.

### 6.2. Sous-cohorte cinétique

Les patients de la sous-cohorte cinétique seront séquencés en **singleplex ou faible multiplexage**. Le protocole exact sera identique pour l’ensemble de cette sous-cohorte après sa fixation.

Les données seront analysées en temps réel ou reconstruites à partir des timestamps de séquençage à des points temporels prédéfinis.

### 6.3. Pipeline bioinformatique

L’analyse comprendra :

1. le basecalling ;
2. l’alignement des lectures sur le génome de référence ;
3. l’identification des CpG couverts et l’estimation de leur état de méthylation ;
4. la génération des formats requis par les différents classifieurs ;
5. l’application des modèles pré-entraînés ;
6. l’enregistrement des prédictions et des scores de confiance ;
7. pour les analyses cinétiques, l’enregistrement des prédictions à différents temps ou niveaux cumulatifs de données.

Les versions des logiciels, modèles, génome de référence, paramètres et seuils de décision seront documentés et **gelés avant l’analyse de la cohorte principale**.

La chaîne bioinformatique sera versionnée afin d’assurer la reproductibilité de l’analyse.

---

## 7. Classifieurs évalués

Plusieurs classifieurs de méthylation déjà publiés seront appliqués indépendamment aux mêmes données nanopore.

Les méthodes envisagées comprennent notamment :

- **crossNN**, notamment via l’écosystème nanoDx ;
- **MethyLYZR** ;
- **Sturgeon** ;
- **MNP-Flex**, sous réserve de son accessibilité dans le cadre du projet.

La liste définitive sera arrêtée avant le début des analyses comparatives.

### Validation externe sans entraînement local

L’étude est conçue comme une **validation externe de modèles pré-entraînés**.

Aucun modèle ne sera entraîné à partir de la cohorte locale pour l’analyse principale. Aucune procédure de réentraînement, fine-tuning, sélection de variables, optimisation des seuils ou calibration sur les diagnostics de la cohorte ne sera réalisée avant le calcul des performances principales.

Il n’est donc pas nécessaire de séparer la cohorte en sous-ensembles d’entraînement et de test.

---

## 8. Procédure d’analyse en aveugle

Les prédictions nanopore seront générées sans connaissance du diagnostic intégré final.

Pour chaque cas, les résultats des différents classifieurs seront enregistrés avant la levée de l’aveugle.

Les règles permettant de convertir les sorties propres à chaque modèle — methylation family, class ou subclass — vers les catégories diagnostiques utilisées pour la comparaison clinique seront définies **a priori** et gelées avant l’analyse principale.

Les discordances feront l’objet d’une revue secondaire après calcul des performances principales, sans modification rétrospective de la classification primaire.

---

## 9. Critère de jugement principal

Le critère principal sera le :

**taux de diagnostics nanopore concordants avec le diagnostic intégré de référence, calculé sur l’ensemble des patients pour lesquels l’analyse nanopore a été initiée.**

La concordance principale sera évaluée à un niveau diagnostique prédéfini et cliniquement pertinent.

Le numérateur correspondra au nombre de patients pour lesquels le workflow nanopore fournit un diagnostic concordant avec le diagnostic intégré final.

Le dénominateur correspondra à l’ensemble des patients inclus dans l’analyse principale.

Cette analyse suivra une approche **intention-to-diagnose**.

Seront donc comptabilisés comme échecs pour le critère principal :

- les échecs d’extraction empêchant l’analyse ;
- les échecs de séquençage ;
- une quantité de données insuffisante ;
- l’absence de prédiction ;
- une prédiction dont le score est inférieur au seuil prédéfini ;
- tout autre résultat non conclusif.

---

## 10. Critères de jugement secondaires

### 10.1. Performance diagnostique

- taux de résultats techniquement exploitables ;
- taux de classifications conclusives ;
- exactitude diagnostique parmi les résultats conclusifs ;
- performance propre à chacun des classifieurs ;
- concordance entre classifieurs ;
- performances selon les principales familles tumorales ;
- distribution et nature des erreurs diagnostiques.

### 10.2. Quantité de données nécessaire

Dans l’ensemble de la cohorte, les performances seront étudiées en fonction :

- du nombre de reads ;
- du nombre de bases séquencées ;
- du nombre de CpG informatifs ;
- de la profondeur/couverture obtenue.

Cette analyse permet de caractériser la quantité minimale de données nécessaire indépendamment du niveau de multiplexage.

### 10.3. Cinétique réelle de classification

Cette analyse sera conduite principalement dans la sous-cohorte singleplex/faible multiplexage et comprendra :

- temps jusqu’à la première classification correcte ;
- temps jusqu’à une classification correcte et stable ;
- proportion de diagnostics corrects aux différents temps prédéfinis ;
- comparaison de la cinétique entre classifieurs.

### 10.4. Faisabilité

- taux d’échec technique ;
- délai extraction–résultat ;
- temps de calcul bioinformatique ;
- consommation de réactifs ;
- coût analytique par patient ;
- coût selon le niveau de multiplexage.

---

## 11. Analyse de la cinétique de classification

L’une des particularités du séquençage nanopore est la production continue des données.

Dans la sous-cohorte cinétique, les données seront analysées de manière cumulative à des temps prédéfinis, par exemple :

**5, 10, 15, 30, 45 et 60 minutes**, puis au terme du séquençage.

Les temps définitifs seront fixés dans le plan d’analyse avant l’étude.

Pour chaque temps seront enregistrés :

- le nombre de reads disponibles ;
- le nombre de bases séquencées ;
- le nombre de CpG informatifs ;
- la prédiction de chaque classifieur ;
- son score de confiance ;
- la concordance avec le diagnostic de référence.

Le **temps jusqu’à classification correcte et stable** sera défini comme le premier temps auquel le diagnostic obtenu est concordant avec le diagnostic de référence et reste concordant lors de toutes les évaluations ultérieures prévues pour le même run.

Dans la cohorte principale 6-plex, les mêmes sous-échantillonnages pourront être reproduits en fonction de la **quantité cumulée de données**, mais le temps chronologique ne sera pas directement extrapolé à une situation peropératoire.

---

## 12. Analyse des discordances

Toutes les discordances entre le résultat nanopore et le diagnostic intégré seront documentées.

Elles seront secondairement classées en :

- erreur de famille tumorale ;
- erreur de classe ou subclass sans modification du diagnostic clinique principal ;
- discordance susceptible d’avoir un impact diagnostique ;
- résultat nanopore non conclusif ;
- discordance possiblement expliquée par la qualité ou la composition du prélèvement ;
- discordance pouvant évoquer une hétérogénéité tumorale.

Cette analyse aura un objectif explicatif et ne modifiera pas rétrospectivement le résultat de l’analyse principale.

---

## 13. Analyses statistiques

Les analyses seront réalisées principalement au niveau du patient. Toutes les estimations seront accompagnées d’un **intervalle de confiance à 95 %**. Un plan d’analyse statistique détaillé sera finalisé avant le gel de la base de données.

### 13.1. Description de la population

Les variables quantitatives seront décrites par moyenne et écart-type ou médiane et intervalle interquartile selon leur distribution. Les variables qualitatives seront présentées sous forme d’effectifs et de pourcentages.

La distribution des diagnostics, la qualité des prélèvements, les variables pré-analytiques et la modalité de séquençage seront décrites.

### 13.2. Analyse du critère principal

Le taux de concordance diagnostique du workflow nanopore avec le diagnostic intégré de référence sera estimé avec son **intervalle de confiance binomial à 95 %**.

L’analyse principale inclura les résultats non conclusifs comme échecs diagnostiques.

Seront rapportés séparément :

1. le **diagnostic yield**, défini comme la proportion de patients ayant obtenu un résultat nanopore conclusif ;
2. la **conditional accuracy**, définie comme la proportion de diagnostics corrects parmi les résultats conclusifs ;
3. la **performance globale en intention-to-diagnose**, qui constituera l’analyse principale.

### 13.3. Comparaison des classifieurs

Les différents classifieurs étant appliqués aux mêmes patients, les comparaisons seront appariées.

Les différences de taux de succès diagnostique entre deux classifieurs seront analysées par **test de McNemar**. En cas de comparaisons multiples, une correction adaptée, par exemple la procédure de Holm, sera appliquée.

La concordance catégorielle sera également décrite par matrices de confusion et, lorsque pertinent, coefficient kappa.

Lorsque les effectifs le permettront, des métriques par classe ou famille tumorale seront rapportées : sensibilité, valeur prédictive positive, rappel macro-moyenné et exactitude équilibrée.

### 13.4. Effet de la quantité de données

Dans l’ensemble de la cohorte, la probabilité d’obtenir une classification correcte sera modélisée en fonction de la quantité cumulée de données : nombre de reads, nombre de bases et nombre de CpG informatifs.

Les mesures répétées provenant d’un même patient seront prises en compte par un **modèle de régression logistique à effets mixtes** ou une méthode équivalente pour données longitudinales.

Le modèle pourra inclure le classifieur, la quantité de données et leur interaction, avec un effet aléatoire lié au patient.

### 13.5. Effet du temps dans la sous-cohorte cinétique

L’analyse temporelle sera conduite séparément dans la sous-cohorte singleplex/faible multiplexage afin de ne pas confondre le temps de séquençage avec le partage de capacité lié au multiplexage 6-plex.

La probabilité de classification correcte sera étudiée en fonction du temps à l’aide d’un modèle pour mesures répétées. Le classifieur, le temps et leur interaction pourront être inclus comme effets fixes, avec un effet aléatoire patient.

Le temps médian jusqu’à classification correcte et stable sera estimé pour chaque classifieur. Selon la distribution et la fréquence des événements, une représentation de type temps-vers-événement pourra également être utilisée à titre descriptif.

### 13.6. Facteurs associés aux échecs diagnostiques

Les facteurs associés à un résultat non conclusif, une discordance diagnostique ou un délai prolongé avant classification correcte seront étudiés de manière exploratoire.

Les variables candidates comprendront notamment : cellularité tumorale, nécrose, quantité et qualité d’ADN, quantité de données obtenue, type tumoral et variables pré-analytiques.

Le nombre de variables introduites dans les modèles multivariés sera limité en fonction du nombre d’événements observés afin d’éviter le surajustement.

---

## 14. Taille de la cohorte

La taille définitive de la cohorte sera déterminée avec l’URCE à partir de l’objectif statistique retenu, du recrutement réalisable et du budget disponible.

Deux approches sont envisageables.

### Approche fondée sur la précision

L’effectif peut être choisi afin d’estimer une concordance attendue élevée, par exemple proche de 95 %, avec une précision jugée suffisante. Des cohortes de l’ordre de **80 à 150 patients** permettent une estimation informative de la performance globale.

### Approche fondée sur un seuil minimal de performance

Une seconde possibilité consiste à définir un taux minimal de concordance `p0` nécessaire pour poursuivre le développement clinique, puis à tester :

**H0 : p ≤ p0**  
**H1 : p > p0**

L’effectif sera alors calculé en fonction du seuil minimal, de la performance attendue, du risque alpha, de la puissance souhaitée et du taux anticipé d’échec/non-classification.

Une cohorte plus importante, potentiellement de l’ordre de **150 à 200 patients**, peut être nécessaire si l’objectif retenu est de démontrer formellement que la performance dépasse un seuil élevé.

L’effectif de la **sous-cohorte cinétique** sera déterminé séparément. Son objectif est principalement d’estimer la distribution des délais de classification dans des conditions de séquençage proches d’un futur usage peropératoire ; il ne sera pas nécessairement dimensionné pour le critère principal de concordance.

---

## 15. Gestion des données manquantes et analyses de sensibilité

Aucune imputation ne sera réalisée pour le critère diagnostique principal.

Les résultats nanopore non conclusifs seront intégrés comme échecs conformément à l’analyse intention-to-diagnose.

Le nombre et les causes des données manquantes concernant les variables secondaires seront décrits.

Une analyse de sensibilité limitée aux cas techniquement évaluables sera réalisée afin de distinguer les performances de l’ensemble du workflow des performances conditionnelles des classifieurs lorsqu’une donnée exploitable est disponible.

---

## 16. Reproductibilité et traçabilité

Afin de garantir la reproductibilité :

- les versions exactes des modèles seront conservées ;
- le code utilisé pour la préparation et l’analyse des données sera versionné ;
- les paramètres de chaque pipeline seront enregistrés ;
- les règles de correspondance entre classes moléculaires et diagnostics seront définies avant l’analyse ;
- les modalités de multiplexage et la règle de constitution de la sous-cohorte cinétique seront préspécifiées ;
- les sorties brutes et intermédiaires nécessaires à la vérification des résultats seront conservées selon les règles applicables aux données de recherche.

La cohorte ne sera pas utilisée pour optimiser rétrospectivement les modèles évalués.

---

## 17. Perspectives translationnelles

Cette étude ne vise pas à démontrer directement l’intérêt clinique d’une classification peropératoire.

Elle vise d’abord à établir :

1. **la concordance diagnostique du nanopore avec le diagnostic intégré conventionnel sur FFPE ;**
2. **la robustesse comparative de plusieurs classifieurs pré-entraînés sur les prélèvements locaux ;**
3. **la quantité minimale de données nécessaire pour obtenir un résultat correct et stable ;**
4. **dans une sous-cohorte dédiée, le délai réel nécessaire à cette classification dans des conditions de séquençage compatibles avec une future transposition peropératoire.**

Si les seuils prédéfinis de performance diagnostique, de taux de succès technique et de rapidité sont atteints, ces résultats permettront de construire une seconde étude prospective en conditions peropératoires, en collaboration avec les équipes de neurochirurgie et de neuropathologie.
