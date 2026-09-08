# Projet JC 2026 — validation du séquençage nanopore sur tumeurs du SNC

**Version :** v0.1 — réécriture clinique et scientifique — 2026-09-08  
**Statut :** manuscrit de travail — non finalisé  
**AAP :** Jeunes Chercheurs Tremplin 2026 — CHU Montpellier

> **IMPORTANT — VERSION NON FINALISÉE**  
> Les éléments signalés `TO DO` doivent être complétés avant soumission. Ils concernent principalement le recrutement réel, le calcul d’effectif avec l’URCE, la qualification réglementaire, les coûts institutionnels, l’équipe et certains paramètres techniques.

---

## 1. Titre provisoire

**Validation prospective du séquençage nanopore sur tissu tumoral congelé pour la classification moléculaire des tumeurs du système nerveux central**

> **TO DO — TITRE / ACRONYME**  
> Définir un titre final et un acronyme après stabilisation du protocole.

---

## 2. Résumé scientifique

La chirurgie des tumeurs du système nerveux central (SNC) repose sur un compromis entre contrôle tumoral et préservation fonctionnelle. L’étendue de résection peut influencer le pronostic, mais le bénéfice attendu d’une résection plus large n’est pas identique pour toutes les tumeurs ni pour tous les sous-types moléculaires. Au moment de l’intervention, la décision repose principalement sur l’imagerie, l’exploration chirurgicale, le monitorage fonctionnel et l’examen anatomopathologique extemporané. Le diagnostic moléculaire intégré, qui définit aujourd’hui de nombreuses entités de la classification OMS, n’est généralement disponible qu’après l’intervention.

Plusieurs études montrent qu’une information moléculaire obtenue pendant l’intervention peut être cliniquement utile. Dans l’étude de Djirackor et al., la classification moléculaire intraopératoire aurait conduit à modifier la stratégie chirurgicale dans 12 des 20 cas évalués en temps réel. Dans une cohorte pédiatrique prospective de 94 patients, Sie et al. ont rapporté une modification effective de la stratégie chirurgicale dans 14,3 % des cas informatifs. Chez l’adulte, Wu et al. ont montré dans une cohorte prospective multicentrique que l’analyse moléculaire rapide pouvait corriger des interprétations extemporanées susceptibles d’influencer la prise en charge : 40 lésions interprétées comme gliomes de bas grade ont été reclassées en glioblastomes sur la base d’informations moléculaires, et 20 lésions interprétées comme gliose ont été identifiées comme gliomes diffus. Par ailleurs, des études rétrospectives suggèrent que le bénéfice d’une résection maximale peut varier selon les sous-classes moléculaires de glioblastome. Ces résultats ne démontrent pas encore qu’une stratégie guidée par nanopore améliore la survie ou réduit la morbidité neurologique chez l’adulte, mais ils justifient l’évaluation d’outils capables de fournir une information moléculaire fiable dans un délai court.

Le séquençage Oxford Nanopore permet d’analyser directement l’ADN natif, y compris sa méthylation, et de produire des données pendant le séquençage. Plusieurs méthodes publiées permettent aujourd’hui de classifier les tumeurs du SNC à partir de données nanopore peu profondes, notamment crossNN/nanoDx, Sturgeon, MethyLYZR et MNP-Flex. D’autres workflows, comme Rapid-CNS2, iSCORED et ROBIN, ont montré que la méthylation et les profils de nombre de copies pouvaient être obtenus dans un délai compatible avec la période périopératoire.

Avant d’évaluer l’impact de cette information sur la décision chirurgicale au CHU Montpellier, il faut démontrer que le workflow est fiable dans les conditions locales. L’objectif principal du présent projet est donc d’évaluer si le séquençage nanopore d’un prélèvement tumoral congelé permet d’obtenir une classification diagnostique concordante avec le diagnostic intégré final établi en routine sur tissu fixé et inclus en paraffine (FFPE).

Il s’agira d’une étude prospective, monocentrique, comparative et appariée de performance diagnostique. Pour chaque patient, le test index sera l’analyse nanopore du prélèvement congelé et le standard de référence sera le diagnostic intégré final établi sur FFPE. Le résultat nanopore restera expérimental et ne modifiera pas la prise en charge pendant cette première étude.

La cohorte principale sera séquencée en multiplexage de six échantillons par flow cell afin d’évaluer la performance diagnostique à un coût compatible avec l’AAP. Une sous-cohorte prédéfinie sera séquencée en singleplex ou faible multiplexage afin de mesurer le temps et la quantité de données nécessaires à une classification correcte et stable dans une configuration plus proche d’une utilisation peropératoire.

Le workflow de référence retenu pour la planification est le **Rapid Barcoding Kit V14 (`SQK-RBK114.24`) sur flow cell R10.4.1 (`FLO-MIN114`)**. Les mêmes données seront analysées par plusieurs classifieurs publiés et pré-entraînés. Aucun modèle ne sera entraîné ou optimisé sur la cohorte locale pour l’analyse principale.

Le critère principal sera le taux de diagnostics nanopore concordants avec le diagnostic intégré de référence, calculé sur l’ensemble des patients pour lesquels l’analyse nanopore a été initiée. Les échecs techniques et les résultats non conclusifs seront intégrés comme échecs dans l’analyse principale.

Le projet utilise des séquenceurs, une infrastructure bioinformatique et des compétences déjà disponibles au CHU Montpellier. Si le workflow atteint les performances diagnostiques et les délais définis avant l’analyse, une étude ultérieure pourra évaluer son effet sur la stratégie chirurgicale, l’étendue de résection, les reprises chirurgicales et les résultats fonctionnels.

---

## 3. Contexte scientifique et clinique

### 3.1. La décision chirurgicale dépend du diagnostic et de la biologie tumorale

Pour de nombreuses tumeurs du SNC, la chirurgie vise à retirer le plus de tumeur possible tout en limitant le risque de déficit neurologique. L’étendue de résection est associée au pronostic dans plusieurs situations, notamment dans les gliomes diffus. Cette association ne signifie cependant pas qu’une résection plus large est toujours bénéfique quel que soit le type tumoral, le sous-type moléculaire, la localisation ou le risque fonctionnel.

La décision peropératoire dépend donc de plusieurs informations : localisation de la tumeur, limites anatomiques, résultats du mapping et du monitorage fonctionnels, aspect macroscopique, imagerie et diagnostic anatomopathologique extemporané. La biologie tumorale est également importante, mais elle est le plus souvent connue après la chirurgie.

Cette question est devenue plus importante depuis que le diagnostic des tumeurs du SNC repose sur une classification intégrée. Plusieurs entités ne peuvent plus être définies correctement par la morphologie seule. Des informations telles que le statut `IDH`, la codélétion `1p/19q`, certaines altérations histoniques, des profils de nombre de copies et, dans certaines situations, la classe de méthylation participent directement au diagnostic final.

### 3.2. L’examen extemporané ne fournit pas toujours l’information nécessaire

L’examen extemporané reste utile pendant la chirurgie, mais il peut être limité par la quantité de tissu, les artéfacts de congélation, l’hétérogénéité tumorale et le chevauchement morphologique entre plusieurs entités.

Djirackor et al. ont étudié l’utilisation peropératoire de la classification par méthylation dans une cohorte de 105 tumeurs cérébrales. La classification moléculaire était concordante avec le diagnostic final dans 93 cas sur 105. Elle était correcte dans les six cas où l’examen extemporané était non conclusif. Parmi 20 cas analysés en situation peropératoire, les auteurs ont estimé qu’une classification moléculaire précise aurait conduit à modifier la stratégie chirurgicale dans 12 cas. Les modifications envisagées allaient dans les deux sens : poursuivre une résection lorsqu’une lésion potentiellement résécable avait été mal caractérisée, ou éviter une résection supplémentaire lorsque le bénéfice oncologique attendu était limité par rapport au risque fonctionnel.

Chez l’adulte, Wu et al. ont évalué une stratégie de diagnostic moléculaire rapide dans une cohorte prospective multicentrique de 296 patients présentant principalement des gliomes diffus. Le premier niveau de l’analyse moléculaire, disponible en environ 35 minutes, permettait de classifier une grande partie des cas. Quarante tumeurs interprétées comme gliomes de bas grade sur l’examen extemporané avaient des résultats moléculaires compatibles avec un glioblastome, confirmés secondairement. Vingt lésions interprétées comme gliose ont été identifiées comme gliomes diffus grâce à la détection d’altérations moléculaires. Cette étude n’utilisait pas le nanopore, mais elle montre qu’une information moléculaire disponible pendant l’intervention peut corriger une interprétation morphologique et fournir une information directement utile à la prise en charge.

### 3.3. L’information moléculaire peut modifier la stratégie chirurgicale

L’intérêt clinique potentiel ne se limite pas à obtenir le diagnostic plus tôt. Une information moléculaire disponible pendant l’intervention peut modifier la décision de poursuivre ou d’arrêter une résection.

Dans l’étude de Sie et al. publiée en 2026, Sturgeon a été utilisé en routine avec l’examen extemporané chez 94 patients pédiatriques consécutifs. Le diagnostic Sturgeon était correct dans 82 cas sur 94 en moins de 90 minutes. Parmi les cas informatifs, le résultat soutenait la stratégie chirurgicale prévue dans 85,7 % des cas et modifiait effectivement la stratégie dans 14,3 %. Les modifications pouvaient conduire à une résection plus large ou plus limitée. Les auteurs rapportent également un faible taux de complications et moins de chirurgies de second look, mais cette étude n’établit pas à elle seule un effet causal du nanopore sur ces résultats.

Les données adultes sont moins avancées sur ce point. Il n’existe pas encore de grande étude prospective adulte montrant qu’un résultat nanopore peropératoire réduit les reprises chirurgicales, la morbidité neurologique ou améliore la survie. Ce manque de données justifie une progression en deux étapes : valider d’abord la performance diagnostique locale, puis tester l’impact clinique dans une étude dédiée.

### 3.4. La biologie tumorale peut modifier le bénéfice attendu d’une résection extensive

Une étude multicentrique de Drexler et al. portant sur 430 glioblastomes IDH-wildtype a analysé l’association entre sous-classe de méthylation et bénéfice de l’étendue de résection. Une résection complète ou quasi complète était associée à une meilleure survie dans les sous-classes RTK I et RTK II. Cette association n’était pas retrouvée de façon significative dans la sous-classe mésenchymateuse. Cette étude est rétrospective et ne permet pas d’utiliser la sous-classe de méthylation comme règle décisionnelle validée. Elle montre néanmoins que le bénéfice associé à l’étendue de résection peut dépendre de la biologie tumorale.

Les recommandations et revues récentes sur la chirurgie des gliomes adultes insistent également sur la nécessité d’adapter la stratégie à la balance entre bénéfice oncologique et risque fonctionnel. Le cadre PIONEER/RANO resect publié en 2026 cite les diagnostics peropératoires émergents parmi les informations susceptibles d’influencer la stratégie chirurgicale. Une future étude d’impact devra donc mesurer non seulement l’exactitude diagnostique, mais aussi l’étendue de résection, les reprises chirurgicales, les déficits neurologiques, les fonctions langagières ou cognitives lorsque cela est pertinent, le statut fonctionnel et la qualité de vie.

### 3.5. Pourquoi évaluer le nanopore

Pour être utile dans ce contexte, une méthode doit fournir une information moléculaire suffisamment large et suffisamment rapide.

Le séquençage nanopore présente plusieurs caractéristiques adaptées à cet objectif :

- analyse directe de l’ADN natif ;
- détection de la méthylation sans conversion au bisulfite ;
- production des données pendant le run ;
- possibilité d’obtenir une classification à faible couverture ;
- possibilité d’extraire, selon le workflow et la quantité de données, des informations de nombre de copies et certaines altérations de séquence ou structurales.

Plusieurs études ont montré que cette information pouvait être produite pendant la période opératoire. Sturgeon a permis une classification en moins de 90 minutes dans des interventions réelles. Rapid-CNS2 a fourni des informations de méthylation et de nombre de copies dans un workflow intraopératoire d’environ 90 minutes. iSCORED a produit des profils de méthylation et de nombre de copies en environ 105 minutes. ROBIN a combiné classification de méthylation et analyses génomiques complémentaires avec un résultat diagnostique en moins de deux heures.

Ces études démontrent la faisabilité technique. Elles ne remplacent pas une validation locale, car la performance dépend du prélèvement, de la qualité de l’ADN, de la préparation de librairie, de la quantité de données, du classifieur et du seuil utilisé pour rendre un résultat.

### 3.6. Positionnement du projet

Le présent projet ne testera pas directement une stratégie chirurgicale guidée par nanopore. Il répond à la question préalable suivante :

> **Le séquençage nanopore réalisé sur un prélèvement tumoral congelé permet-il d’obtenir, au CHU Montpellier, une classification diagnostique suffisamment concordante avec le diagnostic intégré de référence sur FFPE pour justifier une étude peropératoire ultérieure ?**

Le projet ne prévoit pas de développer un nouveau classifieur local. Plusieurs modèles publiés seront appliqués aux mêmes données afin de mesurer leur performance et leurs échecs sur une cohorte locale indépendante.

---

## 4. Faisabilité locale

Le projet sera réalisé dans l’environnement du Plateau de Médecine Moléculaire et de Génomique (PMMG). Les séquenceurs nanopore et l’infrastructure bioinformatique nécessaires sont déjà disponibles.

Des équipes du CHU Montpellier ont déjà publié des travaux utilisant le séquençage long-read et Oxford Nanopore. Une étude sur une duplication intragénique de `PALB2` a notamment utilisé MinION/Flongle, le basecalling, l’alignement long-read, la visualisation des alignements et la détection de variants structuraux, avec implication de MOBIDIC/PMMG.

Le CHU Montpellier a également participé à une étude directement liée aux tumeurs du SNC. Dans l’étude de Filser et al. publiée dans *Neuro-Oncology* en 2025 sur la classification des médulloblastomes par nanopore, Valérie Rigau et Gilles Palenzuela figurent parmi les co-auteurs. Cette étude a montré une forte concordance avec la classification de référence et a utilisé un multiplexage de six tumeurs par flow cell MinION dans une partie du travail.

Le projet ne nécessite donc pas l’achat d’un séquenceur ni la création d’une nouvelle infrastructure informatique. Les principales dépenses concernent les prélèvements congelés, l’extraction et le contrôle qualité de l’ADN, les kits de préparation de librairie et les flow cells.

> **TO DO — RECRUTEMENT RÉEL**  
> - Nombre annuel de patients opérés / pris en charge pour une tumeur du SNC : `....................`  
> - Nombre annuel disposant d’un fragment congelé exploitable : `....................`  
> - Durée réaliste d’inclusion : `....................`  
> - Répartition approximative des principales familles tumorales : `....................`

---

## 5. Hypothèse et objectifs

### 5.1. Hypothèse principale

Nous faisons l’hypothèse que le séquençage nanopore sur tissu tumoral congelé permet d’obtenir une classification diagnostique concordante avec le diagnostic intégré final établi en routine sur FFPE, avec un taux de résultats conclusifs compatible avec une utilisation clinique ultérieure.

### 5.2. Objectif principal

Évaluer la concordance diagnostique entre le workflow nanopore appliqué à un prélèvement tumoral congelé et le diagnostic intégré final établi en routine sur FFPE.

### 5.3. Objectifs secondaires

Les objectifs secondaires seront de :

1. comparer les performances de plusieurs classifieurs pré-entraînés appliqués aux mêmes données nanopore ;
2. mesurer le taux de résultats techniquement exploitables ;
3. mesurer le taux de classifications conclusives ;
4. caractériser les discordances diagnostiques et les situations de non-classification ;
5. étudier l’association entre performance et cellularité tumorale, nécrose, qualité de l’ADN et paramètres pré-analytiques ;
6. déterminer la quantité de données nécessaire à une classification correcte et stable ;
7. mesurer la cinétique de classification dans une sous-cohorte séquencée en singleplex ou faible multiplexage ;
8. documenter le délai analytique et le coût par prélèvement ;
9. explorer, lorsque les données le permettent, les informations additionnelles accessibles par nanopore, notamment les CNV, la méthylation de `MGMT` et certaines altérations structurales ou de séquence.

---

## 6. Méthodologie

### 6.1. Schéma de l’étude

Il s’agira d’une **étude prospective, monocentrique, comparative et appariée de performance diagnostique**.

Pour chaque patient :

- le **standard de référence** sera le diagnostic intégré final établi dans le circuit diagnostique habituel sur tissu FFPE ;
- le **test index** sera l’analyse nanopore réalisée sur un fragment tumoral congelé provenant de la même intervention.

Chaque patient constituera son propre comparateur. Le résultat nanopore restera expérimental et ne sera pas utilisé pour établir le diagnostic clinique ni modifier la prise en charge pendant cette première étude.

### 6.2. Population

Les patients éligibles seront inclus consécutivement afin de limiter le biais de sélection et de refléter la population réellement prise en charge.

Seront considérés comme éligibles les patients :

- pris en charge pour une lésion tumorale du SNC ;
- disposant d’un prélèvement permettant l’établissement du diagnostic de routine sur FFPE ;
- pour lesquels un fragment tumoral congelé correspondant à la même intervention est disponible sans compromettre les analyses nécessaires aux soins ;
- pour lesquels un diagnostic intégré final peut être établi selon les procédures diagnostiques habituelles.

La cohorte ne sera pas sélectionnée sur la facilité attendue de classification.

### 6.3. Standard diagnostique de référence

Le diagnostic intégré final sur FFPE constituera le standard de référence. Il reposera sur l’examen histologique, l’immunohistochimie, les analyses moléculaires indiquées et les autres informations nécessaires à l’établissement du diagnostic selon la classification des tumeurs du SNC en vigueur.

Les équipes réalisant le diagnostic conventionnel ne disposeront pas du résultat nanopore expérimental.

Une règle spécifique devra être définie pour les situations où le diagnostic final reste indéterminé, NOS ou NEC, afin de ne pas classer artificiellement comme erreur une divergence qui reflète une incertitude du standard de référence.

> **TO DO — STANDARD DE RÉFÉRENCE**  
> Définir avec la neuropathologie et l’URCE la gestion des cas NOS/NEC ou des diagnostics de référence non définitifs.

### 6.4. Prélèvement congelé

Un fragment tumoral congelé provenant de la même intervention que le matériel FFPE sera utilisé pour le test index. Lorsque cela sera possible, les fragments congelé et FFPE seront issus de territoires anatomiquement proches.

Une évaluation anatomopathologique du fragment destiné au nanopore ou d’une section adjacente documentera la représentativité tumorale. Les variables suivantes seront enregistrées :

- cellularité tumorale ;
- nécrose ;
- proportion de tissu non tumoral ;
- quantité d’ADN ;
- qualité et intégrité de l’ADN ;
- principales variables pré-analytiques.

### 6.5. Séquençage nanopore

L’ADN natif extrait du prélèvement congelé sera séquencé sur une plateforme Oxford Nanopore disponible localement.

#### Workflow de référence

Le workflow de référence utilisé pour la planification est le **Rapid Barcoding Kit 24 V14 (`SQK-RBK114.24`) sur flow cell R10.4.1 (`FLO-MIN114`)**.

Ce choix repose sur des critères pratiques directement liés au protocole :

- préparation PCR-free ;
- compatibilité avec l’analyse des modifications de bases ;
- préparation de librairie rapide ;
- faible nombre de réactifs externes ;
- possibilité de multiplexage ;
- utilisation de Rapid Barcoding dans plusieurs travaux de classification nanopore de tumeurs du SNC.

Le contrôle de quantité d’ADN sera réalisé avant préparation de librairie. Le budget inclut actuellement un contrôle d’intégrité par Genomic DNA ScreenTape/TapeStation. Ce point pourra être modifié si le circuit local utilise une autre méthode.

La fragmentation mécanique par g-TUBE n’est pas prévue par défaut. Elle ne sera utilisée que si un besoin analytique est défini avant le début de l’étude.

#### Workflows alternatifs

**Native Barcoding V14 (`SQK-NBD114.24`).** Ce workflow est compatible avec MinION/GridION mais nécessite des étapes supplémentaires de réparation, end-prep et ligation. Il n’est pas retenu comme scénario principal à ce stade.

**Ligation Sequencing Kit V14 (`SQK-LSK114`).** Ce workflow peut être utilisé en singleplex ou pour une question analytique spécifique. Le module de réactifs associé retenu dans l’audit est le NEBNext Companion Module v2 `E7672`.

**RRMS.** Le protocole RRMS actuel repose sur PromethION, quatre échantillons par run, une quantité d’ADN plus élevée, une fragmentation g-TUBE, l’adaptive sampling et des lavages de flow cell pendant un run prolongé. Son coût estimé dépasse le plafond de l’AAP pour une cohorte de 150 patients. Il n’est donc pas retenu pour le protocole principal.

> **TO DO — WORKFLOW FINAL**  
> - Confirmer définitivement `SQK-RBK114.24` comme kit de référence : `....................`  
> - Confirmer la plateforme/configuration exacte : `....................`  
> - Confirmer la méthode d’extraction : `....................`  
> - Confirmer le QC d’intégrité ADN : `TapeStation / autre / non requis : ....................`  
> - Confirmer l’absence ou l’usage ciblé de g-TUBE : `....................`

### 6.6. Traitement bioinformatique

La chaîne bioinformatique comprendra au minimum :

1. basecalling ;
2. alignement sur le génome de référence ;
3. appel de méthylation ;
4. génération des formats nécessaires aux classifieurs ;
5. application des modèles pré-entraînés ;
6. enregistrement des prédictions et scores de confiance ;
7. collecte des métriques nécessaires aux analyses de cinétique.

Les versions des logiciels, modèles, paramètres et seuils seront fixées avant l’analyse de la cohorte principale.

### 6.7. Deux modalités de séquençage

#### Cohorte principale — validation diagnostique

La majorité des prélèvements sera séquencée en **6-plex**, soit six échantillons par flow cell. Cette modalité est utilisée pour évaluer la performance diagnostique avec un coût compatible avec l’effectif prévu.

Le temps chronologique observé en 6-plex ne sera pas utilisé comme estimation du délai peropératoire, car les six bibliothèques partagent la capacité de séquençage.

#### Sous-cohorte cinétique

Une sous-cohorte prédéfinie sera séquencée en **singleplex ou faible multiplexage**. L’objectif sera de mesurer la vitesse d’acquisition des données dans une configuration plus proche d’une utilisation peropératoire.

Seront mesurés :

- temps jusqu’à la première classification correcte ;
- temps jusqu’à une classification correcte et stable ;
- nombre de reads nécessaires ;
- quantité de bases nécessaires ;
- nombre de CpG informatifs nécessaires.

> **TO DO — SOUS-COHORTE CINÉTIQUE**  
> - Effectif : `....................`  
> - Modalité : `singleplex / 2-plex / autre : ....................`  
> - Critères d’arrêt du run : `....................`

### 6.8. Classifieurs

Les mêmes données nanopore seront analysées indépendamment par plusieurs classifieurs publiés et pré-entraînés :

- crossNN/nanoDx ;
- MethyLYZR ;
- Sturgeon ;
- MNP-Flex, sous réserve d’accessibilité.

L’étude est une validation externe. Aucun modèle ne sera entraîné, fine-tuné, recalibré ou optimisé sur la cohorte locale avant l’analyse principale.

Les règles permettant de traduire les sorties de chaque classifieur en catégories diagnostiques comparables au diagnostic intégré de référence seront définies avant l’analyse.

> **TO DO — PARAMÈTRES TECHNIQUES**  
> - Liste définitive des classifieurs : `....................`  
> - Versions exactes : `....................`  
> - Seuils de confiance : `....................`  
> - Règles de mapping methylation family/class/subclass → diagnostic clinique : `....................`

### 6.9. Analyse en aveugle

Les prédictions nanopore seront générées sans connaissance du diagnostic intégré final. Les résultats de chaque classifieur seront enregistrés avant levée de l’aveugle.

Le diagnostic de routine sera établi sans accès au résultat nanopore expérimental.

---

## 7. Critères de jugement

### 7.1. Critère principal

Le critère principal sera le **taux de diagnostics nanopore concordants avec le diagnostic intégré de référence**, calculé sur l’ensemble des patients pour lesquels l’analyse nanopore a été initiée.

L’analyse principale suivra une approche **intention-to-diagnose**. Seront considérés comme échecs :

- échec d’extraction empêchant l’analyse ;
- échec de séquençage ;
- quantité de données insuffisante ;
- absence de prédiction ;
- prédiction sous le seuil de confiance prédéfini ;
- autre résultat non conclusif.

La concordance sera évaluée à un niveau diagnostique prédéfini et cliniquement pertinent. Une différence de sous-classe de méthylation sans conséquence sur le diagnostic intégré ne sera pas nécessairement considérée comme une discordance majeure.

### 7.2. Critères secondaires

Seront notamment évalués :

- proportion de patients avec un résultat nanopore conclusif ;
- proportion de diagnostics corrects parmi les résultats conclusifs ;
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

Une **classification correcte et stable** sera définie comme la première prédiction concordante avec le diagnostic de référence qui reste concordante à tous les temps ultérieurs préspécifiés.

> **TO DO — DÉFINITION FINALE DE LA CINÉTIQUE**  
> Valider les temps d’analyse et la définition de stabilité avec l’URCE après choix final du workflow.

---

## 9. Analyse statistique

Les analyses seront conduites au niveau du patient. Les estimations seront accompagnées d’intervalles de confiance à 95 %.

### 9.1. Analyse descriptive

Les variables quantitatives seront décrites par moyenne et écart-type ou par médiane et intervalle interquartile selon leur distribution. Les variables qualitatives seront décrites par effectifs et pourcentages.

### 9.2. Critère principal

Le taux de concordance diagnostique sera estimé avec un **intervalle de confiance binomial à 95 %**.

Trois mesures seront rapportées séparément :

1. taux de résultat conclusif ;
2. exactitude diagnostique parmi les résultats conclusifs ;
3. performance globale en intention-to-diagnose, qui constituera l’analyse principale.

### 9.3. Comparaison des classifieurs

Les classifieurs étant appliqués aux mêmes patients, les comparaisons seront appariées. Les différences de proportions de diagnostics corrects entre deux modèles pourront être testées par test de McNemar. Une correction de multiplicité, par exemple selon Holm, sera appliquée lorsque plusieurs comparaisons seront réalisées.

Un test global de Cochran pourra être utilisé avant les comparaisons deux à deux si plusieurs classifieurs sont comparés simultanément.

Les matrices de confusion et le coefficient kappa de Cohen seront utilisés comme mesures descriptives complémentaires. Lorsque les effectifs le permettront, les performances par famille tumorale seront décrites par sensibilité/rappel, valeur prédictive positive et balanced accuracy.

### 9.4. Effet du temps et de la quantité de données

La probabilité d’obtenir une classification correcte sera étudiée aux différents temps de séquençage. Les mesures répétées chez un même patient seront prises en compte à l’aide d’un modèle de régression logistique à effets mixtes ou d’une méthode équivalente pour données longitudinales.

Le modèle pourra inclure :

- temps ;
- classifieur ;
- interaction temps × classifieur ;
- effet aléatoire patient.

Des analyses analogues pourront utiliser le nombre de reads, le nombre de bases ou le nombre de CpG à la place du temps.

Le temps jusqu’à une classification correcte et stable pourra également être décrit comme un délai jusqu’à événement.

### 9.5. Facteurs associés aux échecs ou discordances

Les facteurs associés à un résultat non conclusif, une discordance diagnostique ou un délai prolongé seront étudiés de façon exploratoire.

Les variables candidates incluront notamment :

- cellularité tumorale ;
- nécrose ;
- quantité et qualité de l’ADN ;
- type tumoral ;
- nombre de CpG obtenus ;
- autres paramètres de séquençage ou pré-analytiques.

Le nombre de variables des modèles multivariés sera limité en fonction du nombre d’événements observés afin de réduire le risque de surajustement.

### 9.6. Données manquantes

Aucune imputation ne sera réalisée pour le critère principal. Les résultats nanopore non conclusifs resteront intégrés comme échecs dans l’analyse principale.

Une analyse de sensibilité sera réalisée parmi les seuls cas techniquement évaluables.

---

## 10. Taille de cohorte

La taille définitive de la cohorte sera déterminée avec l’URCE.

Deux approches sont envisagées :

- une approche estimative, visant à estimer la concordance avec une précision prédéfinie ;
- une approche confirmatoire, visant à démontrer que la concordance dépasse un seuil minimal défini avant l’étude.

Les simulations budgétaires explorent des effectifs compris entre environ 80 et 200 patients. Une cohorte de l’ordre de 120 à 150 patients constitue actuellement un scénario de travail, mais **ne correspond pas encore à l’effectif statistique final**.

> **TO DO — CALCUL D’EFFECTIF URCE**  
> - Approche retenue : `....................`  
> - Concordance attendue : `....................`  
> - Seuil minimal acceptable : `....................`  
> - Alpha : `....................`  
> - Puissance : `....................`  
> - Taux attendu de non-évaluables : `....................`  
> - Effectif final : `....................`  
> - Effectif sous-cohorte cinétique : `....................`

---

## 11. Aspects réglementaires et éthiques

Le résultat nanopore restera expérimental pendant cette première étude et ne modifiera pas la prise en charge clinique.

Le projet utilisera un fragment tumoral congelé obtenu dans le contexte de l’intervention, sans compromettre le matériel nécessaire au diagnostic et aux soins.

> **TO DO — QUALIFICATION RÉGLEMENTAIRE**  
> À valider avec URCE / DRI :  
> - cadre réglementaire : `HLJ / RIPH3 / autre cadre compatible : ....................`  
> - modalités d’information / consentement / non-opposition : `....................`  
> - modalités de constitution et conservation de la collection : `....................`  
> - cadre de conservation et d’utilisation des données génomiques : `....................`

---

## 12. Organisation du projet

Le projet nécessite les compétences suivantes :

- neuropathologie ;
- biologie moléculaire et séquençage long-read ;
- bioinformatique clinique ;
- tumorothèque / CRB ;
- méthodologie et biostatistiques ;
- neurochirurgie pour la définition de la future étude clinique et, selon l’organisation retenue, pour le recrutement et l’interprétation clinique des cas.

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

Les séquenceurs et l’infrastructure bioinformatique étant déjà disponibles, le budget spécifique du projet concerne principalement :

- le prélèvement congelé et le CRB ;
- l’extraction et le contrôle qualité de l’ADN ;
- les kits de préparation de librairie ;
- les flow cells ;
- les petits consommables ;
- les coûts institutionnels obligatoires.

### 13.1. Hypothèses actuelles

Le modèle budgétaire utilise actuellement :

- `FLO-MIN114` : **740 € HT / flow cell** ;
- `SQK-RBK114.24` : **730 € HT / kit**, six réactions complètes par kit ;
- QIAamp Fast DNA Tissue Kit : **296 € / 50 extractions** ;
- Qubit dsDNA HS : **135,65 € / 100 dosages** ;
- Genomic DNA Reagents `5067-5366` : **186 € HT / 105 échantillons** ;
- Genomic DNA ScreenTape `5067-5365` : **270 € HT / 105 échantillons** ;
- petits consommables : **4 € / patient** ;
- CRB : hypothèse basse et haute provisoires, en attente d’un devis spécifique.

Le g-TUBE est valorisé dans le fichier budgétaire mais n’est pas inclus dans le scénario principal tant que la fragmentation mécanique n’est pas retenue dans le protocole.

### 13.2. Scénario de travail à 150 patients

Avec **150 patients dont 12 en 2-plex et 138 en 6-plex**, le modèle actuel prévoit :

- 29 flow cells `FLO-MIN114` ;
- 5 kits `SQK-RBK114.24` ;
- 3 kits d’extraction QIAamp ;
- 2 kits Qubit ;
- 2 packs Genomic DNA Reagents ;
- 2 packs Genomic DNA ScreenTape.

Le coût technique estimé, avec une marge de 10 % et avant ajout des coûts institutionnels, est de :

- **40,7 k€** avec l’hypothèse CRB basse ;
- **50,9 k€** avec l’hypothèse CRB haute.

Le coût technique moyen est donc d’environ :

- **271 € HT par patient** dans le scénario CRB bas ;
- **339 € HT par patient** dans le scénario CRB haut.

Le scénario CRB haut laisse peu de marge sous le plafond de 60 k€ avant ajout des coûts de promotion, méthodologie ou personnel. Le prix marché réel des consommables ONT et le devis CRB sont donc nécessaires avant de fixer l’effectif.

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

### Phase 1 — préparation

- finalisation du protocole ;
- validation réglementaire ;
- validation technique du workflow local ;
- fixation des versions de pipelines et classifieurs ;
- ouverture de l’étude.

### Phase 2 — inclusion et séquençage

- inclusion consécutive des patients ;
- préparation du prélèvement congelé ;
- séquençage de la cohorte principale en 6-plex ;
- séquençage de la sous-cohorte cinétique en singleplex ou faible multiplexage ;
- contrôle qualité ;
- enregistrement prospectif des échecs techniques.

### Phase 3 — analyse et publication

- gel de la base de données ;
- levée de l’aveugle ;
- analyses statistiques ;
- analyse des discordances ;
- rédaction de la publication principale ;
- préparation d’un protocole d’étude peropératoire si les critères préspécifiés sont atteints.

> **TO DO — CALENDRIER**  
> Définir un calendrier daté après obtention du recrutement annuel réel et de l’effectif final.

---

## 15. Risques et mesures de contrôle

### Hétérogénéité tumorale

Le fragment congelé et le bloc FFPE peuvent provenir de zones différentes de la tumeur. Ce risque sera limité par la traçabilité anatomique des prélèvements et par l’évaluation histologique du fragment destiné au nanopore ou d’une section adjacente.

### Échec technique ou données insuffisantes

Les échecs seront enregistrés prospectivement et inclus dans l’analyse principale en intention-to-diagnose.

### Déséquilibre entre classes tumorales

L’inclusion consécutive reflétera la distribution réelle des tumeurs prises en charge. Les analyses par classe seront secondaires lorsque les effectifs sont faibles.

### Évolution des classifieurs

Les versions utilisées seront fixées avant l’analyse principale. Une version plus récente pourra être testée secondairement mais ne remplacera pas l’analyse préspécifiée.

### Risque de surapprentissage

Aucun réentraînement ni optimisation sur la cohorte locale ne sera réalisé pour l’analyse principale.

### Choix du workflow de librairie

Le choix du Rapid Barcoding devra être confirmé avant l’ouverture de l’étude. Si un autre workflow est retenu pour des raisons analytiques, le protocole et le budget seront recalculés avant inclusion.

### Budget

Le budget dépend surtout du prix des flow cells et du coût CRB. L’effectif ne devra pas être fixé avant obtention des tarifs institutionnels et du calcul méthodologique final.

---

## 16. Résultats attendus

L’étude doit fournir une estimation précise de la proportion de patients pour lesquels le workflow nanopore sur tissu congelé reproduit le diagnostic intégré établi sur FFPE.

Elle doit également permettre de :

- mesurer le taux de résultats non conclusifs ;
- comparer plusieurs classifieurs sur les mêmes patients ;
- identifier les principaux types de discordance ;
- déterminer les facteurs associés aux échecs ;
- estimer la quantité minimale de données nécessaire à une classification correcte et stable ;
- estimer le délai compatible avec une utilisation peropératoire ;
- établir le coût du workflow dans les conditions locales.

---

## 17. Suite clinique du programme

Si la performance diagnostique, le taux de résultats conclusifs et le délai sont jugés suffisants selon des seuils définis avant l’analyse, une seconde étude prospective pourra évaluer l’utilisation du workflow pendant la chirurgie.

Cette étude devra répondre à une question clinique différente :

> **Une information moléculaire obtenue pendant l’intervention modifie-t-elle la stratégie chirurgicale et améliore-t-elle la prise en charge du patient ?**

Les critères de cette seconde étude pourront inclure :

- modification de la stratégie chirurgicale prévue ;
- modification de l’étendue de résection ;
- étendue de résection obtenue ;
- nécessité d’une chirurgie de second look ou d’une reprise précoce ;
- nouveaux déficits neurologiques ;
- fonctions langagières ou cognitives lorsque cela est pertinent ;
- statut fonctionnel ;
- qualité de vie ;
- délais jusqu’au diagnostic intégré et au traitement adjuvant.

Cette seconde étape ne sera justifiée que si le présent projet démontre une performance diagnostique suffisante.

---

## 18. Valorisation scientifique

La publication principale portera sur la validation prospective du workflow nanopore local.

Elle devra rapporter :

- la performance globale en intention-to-diagnose ;
- le taux de résultats conclusifs ;
- les performances par classifieur ;
- les discordances ;
- les échecs techniques ;
- les facteurs associés aux échecs ;
- la cinétique de classification ;
- le coût analytique.

Des analyses secondaires pourront porter sur les CNV, `MGMT`, les cas discordants et la relation entre cellularité tumorale et performance.

Le porteur du projet devra être premier auteur de la publication princeps conformément aux règles de l’AAP.

---

## 19. Bibliographie principale

La bibliographie complète est conservée dans les fichiers bibliographiques du projet. Les références les plus directement liées au rationnel et au protocole sont :

1. Capper D, et al. *Nature*. 2018. DNA methylation-based classification of central nervous system tumours.
2. Louis DN, et al. *Neuro-Oncology*. 2021. WHO Classification of Tumors of the Central Nervous System.
3. Djirackor L, et al. *Neuro-Oncology Advances*. 2021. Intraoperative DNA methylation classification of brain tumors impacts neurosurgical strategy.
4. Drexler R, et al. *Neuro-Oncology*. 2023. DNA methylation subclasses predict the benefit from gross total tumor resection in IDH-wildtype glioblastoma patients.
5. Kuschel LP, et al. *Neuropathology and Applied Neurobiology*. 2023. Robust methylation-based classification of brain tumours using nanopore sequencing.
6. Vermeulen C, et al. *Nature*. 2023. Ultra-fast deep-learned CNS tumour classification during surgery.
7. Wu et al. *BMC Medicine*. 2025. Rapid diagnosis of adult-type diffuse glioma using a layered scheme.
8. Brändl B, et al. *Nature Medicine*. 2025. Rapid brain tumor classification from sparse epigenomic data.
9. Patel A, et al. *Nature Medicine*. 2025. Prospective multicenter validation of a platform for rapid molecular profiling of central nervous system tumors.
10. Emiliani et al. *Genome Medicine*. 2025. Nanopore-based random genomic sampling for intraoperative molecular diagnosis.
11. Yuan D, et al. *Nature Cancer*. 2025. crossNN.
12. Deacon S, et al. *Neuro-Oncology*. 2025. ROBIN.
13. Filser M, et al. *Neuro-Oncology*. 2025. Nanopore sequencing as a cutting-edge technology for medulloblastoma classification.
14. Drexler R, Lim M, Hervey-Jumper S. *Neuro-Oncology*. 2025. Molecular-based decision-making in glioblastoma surgery.
15. PIONEER Consortium / RANO resect. *Lancet Oncology*. 2026. Recommendations for intraoperative decision making in diffuse glioma surgery.
16. Sie M, et al. *Neuro-Oncology*. 2026. How “Sturgeon” guides the surgeon in pediatric neuro-oncology.

---

## 20. Éléments à compléter avant version v1.0

### Bloquants avant soumission

- [ ] Recrutement réel et durée d’inclusion.
- [ ] Calcul d’effectif définitif avec l’URCE.
- [ ] Qualification réglementaire.
- [ ] Prix marché CHU et devis CRB.
- [ ] Coûts institutionnels complets.
- [ ] Composition de l’équipe et responsabilités.

### À préspécifier avant démarrage

- [ ] Workflow `SQK-RBK114.24` / `FLO-MIN114` définitif.
- [ ] Méthode d’extraction.
- [ ] QC d’intégrité de l’ADN.
- [ ] Multiplexage de la sous-cohorte cinétique.
- [ ] Classifieurs et versions.
- [ ] Seuils de confiance.
- [ ] Mapping classes → diagnostic clinique.
- [ ] Gestion des cas NOS/NEC.
- [ ] Définition finale d’une classification correcte et stable.

---

## 21. Statut de la version v0.1

Cette version décrit la question clinique, la justification de l’étude, le design diagnostique, le workflow technique, le plan statistique et le budget de travail. Les paramètres qui dépendent du recrutement local, de l’URCE, de la DRI, du CRB et des prix marché restent volontairement non renseignés.