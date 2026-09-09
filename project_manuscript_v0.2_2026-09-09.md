# Projet JC 2026 — implémentation clinique accélérée du séquençage nanopore pour les tumeurs du SNC

**Version :** v0.2 — 2026-09-09  
**Statut :** manuscrit de travail — cadrage scientifique révisé  
**AAP :** Jeunes Chercheurs Tremplin 2026 — CHU Montpellier  
**Version précédente conservée :** `project_manuscript_v0.1.md`

> **POINT DE CADRAGE**  
> Cette version remplace le principe d'une large cohorte de validation locale préalable à toute utilisation clinique par une stratégie d'implémentation progressive : **transfert et benchmark inter-centres → qualification locale courte → évaluation prospective dans le circuit diagnostique → utilisation périopératoire lorsque les conditions analytiques, qualité et réglementaires sont réunies**.  
> La phase périopératoire décisionnelle ne doit être incluse dans le protocole AAP que si l'URCE/DRI confirme qu'elle reste compatible avec le cadre réglementaire autorisé par l'appel.

---

## 1. Titre provisoire

**Implémentation clinique du séquençage nanopore pour la classification moléculaire rapide des tumeurs du système nerveux central**

### Variantes possibles

- **Mise en place d'un profilage moléculaire rapide par nanopore pour le diagnostic intégré des tumeurs du SNC**
- **Classification moléculaire rapide des tumeurs du SNC par séquençage nanopore : transfert, qualification et évaluation clinique**

> **TO DO — TITRE / ACRONYME**  
> Le titre définitif sera arrêté après le retour opérationnel de Toulouse et la discussion avec l'URCE/DRI.

---

## 2. Résumé scientifique

La classification des tumeurs du système nerveux central (SNC) repose désormais sur un diagnostic intégré associant morphologie, immunohistochimie et données moléculaires. La cinquième édition de la classification OMS des tumeurs du SNC (WHO CNS5) a renforcé la place des caractéristiques moléculaires et épigénétiques dans la définition de nombreuses entités. Le profilage pangénomique de méthylation de l'ADN constitue, selon le type tumoral, un critère diagnostique essentiel ou désirable et permet également de résoudre des situations dans lesquelles la morphologie et les analyses ciblées restent insuffisantes ou discordantes.

Cette évolution est désormais portée par plusieurs référentiels internationaux et européens. L'EANO recommande qu'un accès à l'analyse de méthylation, localement ou par adressage, soit disponible dans tout établissement impliqué dans le diagnostic des tumeurs du SNC. Le cIMPACT-NOW update 9 a défini en 2025 les principales indications du profilage pangénomique de méthylation en neuropathologie. L'International Collaboration on Cancer Reporting (ICCR) a ajouté le profilage du méthylome parmi les éléments moléculaires core de son dataset 2024 consacré aux tumeurs du SNC. Les recommandations SIOP-Europe/ERN PaedCan intègrent l'accès à une plateforme de méthylation dans l'organisation diagnostique pédiatrique et citent le séquençage Nanopore parmi les méthodes utilisées pour la classification moléculaire du médulloblastome. Pour certaines entités, l'absence de profil de méthylation limite déjà la classification diagnostique : le cIMPACT-NOW update 11 précise notamment que certains épendymomes de fosse postérieure doivent rester classés NOS en l'absence d'un profil de méthylation permettant de confirmer le type PFB.

Il serait cependant incorrect d'affirmer que le profilage pangénomique de méthylation est obligatoire pour toutes les tumeurs cérébrales. Son indication dépend du contexte diagnostique. L'enjeu hospitalier est plutôt de disposer d'un accès rapide, fiable et interprétable à cette information lorsque celle-ci est nécessaire au diagnostic intégré.

Le séquençage Oxford Nanopore permet d'analyser directement l'ADN natif et sa méthylation, sans conversion au bisulfite, avec production continue des données. Des méthodes telles que nanoDx/crossNN, Sturgeon et MethyLYZR montrent qu'une classification des tumeurs du SNC est possible à partir de données nanopore peu profondes. Des workflows tels que Rapid-CNS2, iSCORED et ROBIN montrent en outre qu'une classification de méthylation peut être associée à un profil de nombre de copies et, selon l'approche, à d'autres informations génomiques dans un délai compatible avec la période périopératoire. Plusieurs travaux prospectifs et multicentriques ont désormais dépassé le stade de la simple preuve de concept.

Le CHU Montpellier dispose déjà d'une infrastructure de séquençage long-read, de compétences de biologie moléculaire et de bioinformatique clinique, ainsi que d'une expérience scientifique locale du Nanopore. Des équipes montpelliéraines ont participé à l'étude de Filser et al. sur la classification nanopore des médulloblastomes. Le projet ne vise donc pas à redémontrer sur une large cohorte locale que le principe technologique fonctionne. Il vise à **transférer, qualifier et intégrer rapidement un workflow de classification moléculaire nanopore dans le parcours diagnostique local**, puis à préparer son utilisation lorsque l'information peut être fournie pendant la fenêtre de décision neurochirurgicale.

La première étape consistera à documenter le fonctionnement réel d'un centre français expérimenté, en priorité le CHU/IUCT Toulouse : séquenceur, flow cell, kit, extraction, quantité d'ADN, multiplexage, classifieur, seuils, contrôles qualité, délai, taux d'échec, organisation du rendu, cadre qualité et coût complet. Ces données permettront de ne pas figer prématurément un protocole local différent d'une pratique déjà éprouvée.

Une phase locale courte vérifiera ensuite le transfert du workflow sur des cas représentatifs. Le nombre de cas ne sera pas fixé arbitrairement à 100–200 patients ; il sera déterminé selon la finalité réglementaire et qualité de cette phase. Lorsque les critères prédéfinis seront atteints, le projet passera à une évaluation prospective dans le circuit diagnostique réel. L'objectif sera alors de mesurer non seulement la concordance au diagnostic intégré final, mais aussi le taux de résultats conclusifs, le délai prélèvement-résultat, la proportion de situations diagnostiques résolues, les informations moléculaires additionnelles obtenues et le coût complet du diagnostic.

Une utilisation périopératoire avec la neurochirurgie constitue l'étape translationnelle logique. Elle devra être conditionnée par la qualification du workflow et par la possibilité réglementaire de rendre le résultat en soin. Si une utilisation décisionnelle pendant la chirurgie n'est pas compatible avec le cadre du présent AAP, le projet devra néanmoins recueillir prospectivement les délais et simuler la disponibilité du résultat pendant la fenêtre opératoire afin de préparer immédiatement l'étude clinique suivante.

---

## 3. Contexte scientifique et recommandations

### 3.1. La classification des tumeurs du SNC est devenue histomoléculaire

WHO CNS5 a consolidé le principe d'un diagnostic intégré. L'identité de plusieurs tumeurs ne repose plus sur la morphologie seule. Le statut `IDH`, la codélétion `1p/19q`, certaines altérations histoniques, les profils de nombre de copies, les fusions et, pour plusieurs entités, la classe de méthylation participent au diagnostic final.

La conséquence est directement clinique : un diagnostic anatomopathologique moderne nécessite l'accès à des méthodes capables de fournir les données moléculaires pertinentes dans des délais compatibles avec la prise en charge.

### 3.2. Le profilage pangénomique de méthylation est désormais intégré aux standards diagnostiques

Le profilage de méthylation permet de comparer une tumeur à des classes moléculaires de référence définies sur des cohortes de grande taille. Le travail fondateur de Capper et al. a montré que cette approche pouvait confirmer, préciser ou réviser le diagnostic de tumeurs du SNC. Les validations ultérieures ont confirmé son utilité dans les cas difficiles et dans le diagnostic de routine.

La recommandation EANO 2023 est particulièrement importante pour un projet hospitalier :

> **« Access to DNA methylation analysis, on-site or via referral, should be made available at any institution involved in the diagnostics of CNS tumors. »**

Cette recommandation est classée **C II ; niveau A**.

Le cIMPACT-NOW update 9 recommande notamment le profilage pangénomique de méthylation lorsque celui-ci peut résoudre un diagnostic différentiel, lorsqu'il existe une discordance entre les données disponibles, lorsqu'un sous-typage moléculaire est nécessaire ou lorsque la classe de méthylation est la seule méthode permettant de définir le type tumoral.

L'ICCR a par ailleurs ajouté en 2024 le **methylome profiling** parmi les éléments moléculaires core de son guide international de reporting des tumeurs du SNC, afin d'aligner le compte rendu sur les critères essentiels de WHO CNS5.

### 3.3. Certaines entités dépendent directement du profil de méthylation

Le profil de méthylation n'est pas requis pour tous les diagnostics. En revanche, certaines entités ne peuvent pas être assignées de manière complète sans cette information.

Le cIMPACT-NOW update 11 fournit un exemple particulièrement utile : pour certains épendymomes de la fosse postérieure, la classification définitive en PFB nécessite un profil de méthylation concordant. Lorsque celui-ci n'est pas disponible, le diagnostic doit rester `posterior fossa ependymoma, NOS`.

D'autres tumeurs, telles que les high-grade astrocytoma with piloid features (HGAP), illustrent également la place structurante de la classe de méthylation dans la taxonomie contemporaine.

### 3.4. Les recommandations européennes pédiatriques vont dans le même sens

Les recommandations SIOP-Europe Brain Tumour Group demandent un accès local ou par filière de recours à une plateforme de méthylation de l'ADN et au séquençage par panel de gènes dans l'organisation de la neuropathologie pédiatrique.

Pour le médulloblastome, les recommandations de consensus SIOP-Europe/ERN PaedCan indiquent que la classification moléculaire doit reposer sur le profilage de méthylation ou le profilage transcriptomique, complétés par les analyses de séquence nécessaires. Elles citent explicitement **Nanopore sequencing** parmi les technologies utilisées en diagnostic clinique.

### 3.5. Situation française

Le référentiel ANOCEF Glioblastome 2025 ne recommande pas un méthylome systématique pour tous les glioblastomes adultes. Il indique cependant que le méthylome peut aider à classer les tumeurs de diagnostic difficile et souligne l'intérêt des profils chromosomiques et du statut de méthylation de `MGMT` qui peuvent en être dérivés. Il recommande également de congeler du tissu tumoral pour les analyses complémentaires de biologie moléculaire, ce qui est cohérent avec le prélèvement envisagé dans ce projet.

Une synthèse française publiée en 2025 par Fontaine et al. rappelle par ailleurs que certaines entités WHO CNS nécessitent le méthylome pour une classification complète.

### 3.6. WHO CNS6 est en préparation

En septembre 2026, la sixième édition de la classification OMS des tumeurs du SNC n'est pas publiée. L'IARC indique officiellement que le volume CNS est **in progress** et la deuxième réunion de l'Editorial Board CNS s'est tenue les 29 et 30 avril 2026 à Lyon.

Il ne faut pas anticiper la formulation de WHO CNS6. En revanche, le développement actuel des recommandations cIMPACT-NOW et la place croissante de la classification épigénétique montrent que le projet s'inscrit dans une évolution diagnostique déjà engagée.

---

## 4. Pourquoi le Nanopore est pertinent pour ce besoin clinique

Le profilage de méthylation par arrays est une méthode robuste et largement utilisée. Son organisation repose cependant souvent sur des séries d'échantillons et sur un délai qui n'est pas compatible avec une décision périopératoire.

Le Nanopore présente plusieurs caractéristiques différentes :

- analyse directe de l'ADN natif ;
- détection directe de la méthylation ;
- absence de conversion au bisulfite ;
- production des données en temps réel ;
- classification possible à faible couverture ;
- obtention d'un profil CNV à partir des mêmes données ;
- possibilité, selon le workflow et la couverture, d'étendre l'analyse à `MGMT`, certaines SNV/indels, SV et fusions.

Le principal intérêt n'est donc pas de reproduire à l'identique une technologie existante avec une autre plateforme. Il est de **réduire le délai entre prélèvement et information moléculaire intégrée**, tout en conservant suffisamment d'information pour répondre à plusieurs questions diagnostiques à partir d'une seule librairie.

---

## 5. Données soutenant une utilisation rapide et périopératoire

Djirackor et al. ont montré qu'une classification moléculaire intraopératoire pouvait compléter l'examen extemporané et aurait modifié la stratégie chirurgicale dans 12 des 20 cas évalués en situation peropératoire.

Sturgeon a montré qu'une classification tumorale pouvait être obtenue en moins de 90 minutes pendant des interventions réelles. Dans une cohorte pédiatrique prospective de 94 patients publiée en 2026, le résultat Sturgeon a effectivement modifié la stratégie chirurgicale dans 14,3 % des cas informatifs.

Rapid-CNS2 a fait l'objet d'une validation prospective multicentrique. iSCORED et ROBIN montrent également que la classification de méthylation peut être associée à une information génomique complémentaire dans un délai compatible avec le bloc opératoire.

Chez l'adulte, les preuves directes d'un changement de stratégie chirurgicale guidé par Nanopore sont encore moins nombreuses. En revanche, plusieurs éléments soutiennent la pertinence de la question :

- Wu et al. ont montré qu'un diagnostic moléculaire rapide pouvait corriger des interprétations extemporanées importantes dans les gliomes diffus adultes ;
- Drexler et al. ont montré que l'association entre étendue de résection et pronostic peut varier selon la sous-classe de méthylation d'un glioblastome IDH-wildtype ;
- le cadre PIONEER/RANO resect 2026 rappelle que la décision neurochirurgicale doit intégrer le bénéfice oncologique attendu et le risque fonctionnel.

Le manque actuel de données adultes prospectives sur l'impact décisionnel du Nanopore constitue donc une question de recherche pertinente, mais elle ne doit pas conduire à retarder inutilement la qualification d'un outil diagnostique dont le principe analytique est déjà bien documenté.

---

## 6. Faisabilité à Montpellier et intérêt d'un transfert inter-centres

Le projet sera développé dans l'environnement du Plateau de Médecine Moléculaire et de Génomique (PMMG), avec accès aux compétences de biologie moléculaire, de séquençage long-read et de bioinformatique clinique.

Des équipes du CHU Montpellier ont déjà publié des travaux utilisant Oxford Nanopore. Le CHU a également participé à l'étude de Filser et al. consacrée à la classification nanopore des médulloblastomes, avec notamment Valérie Rigau et Gilles Palenzuela parmi les co-auteurs.

Le même travail comporte des co-auteurs toulousains, notamment Anne-Isabelle Bertozzi et Emmanuelle Uro-Coste. Des éléments publics montrent également une expérience toulousaine du méthylome rapide et du Nanopore en contexte extemporané. Le CHU/IUCT Toulouse constitue donc un centre prioritaire pour obtenir un retour d'expérience opérationnel avant de figer le workflow montpelliérain.

### Informations à obtenir de Toulouse

Le contact devra documenter :

1. séquenceur et configuration exacte ;
2. flow cell et version ;
3. kit de librairie/barcoding ;
4. méthode d'extraction ;
5. quantité et qualité minimales d'ADN ;
6. singleplex ou multiplexage ;
7. classifieur et version ;
8. seuils de confiance ;
9. pipeline de methylation calling ;
10. CNV, `MGMT` et autres sorties produites ;
11. délai extraction → résultat ;
12. taux d'échec et causes principales ;
13. organisation de l'interprétation neuropathologique ;
14. format de compte rendu ;
15. validation analytique et cadre qualité ;
16. statut ISO 15189 / LDT / IVDR applicable ;
17. coût complet réel par patient ;
18. principaux points à modifier ou optimiser après leur retour d'expérience.

Les hypothèses actuelles `SQK-RBK114.24` / `FLO-MIN114` doivent donc être considérées comme **provisoires** jusqu'à cet échange.

---

## 7. Hypothèse générale

Nous faisons l'hypothèse qu'un workflow nanopore déjà soutenu par des validations publiées peut être transféré et qualifié au CHU Montpellier avec une phase locale limitée, puis intégré au parcours diagnostique afin de fournir plus rapidement une classification moléculaire et des informations génomiques complémentaires utiles à la prise en charge des tumeurs du SNC.

Nous faisons également l'hypothèse que, dans une configuration optimisée, cette information peut être obtenue suffisamment tôt pour être disponible pendant la fenêtre de décision neurochirurgicale chez une proportion cliniquement pertinente de patients.

---

## 8. Objectifs

### 8.1. Objectif principal

**Évaluer la faisabilité de l'implémentation clinique d'un workflow nanopore de classification moléculaire rapide des tumeurs du SNC au CHU Montpellier, après transfert et qualification locale de la méthode.**

Le critère principal exact sera arrêté avec l'URCE en fonction du design final. Il pourra combiner la capacité à produire un résultat interprétable dans le délai cible et la concordance avec le diagnostic intégré final.

### 8.2. Objectifs secondaires

Les objectifs secondaires seront de :

1. documenter la reproductibilité et les performances du workflow après transfert ;
2. mesurer le taux de résultats techniquement exploitables ;
3. mesurer le taux de classifications conclusives ;
4. comparer le résultat nanopore au diagnostic intégré final ;
5. mesurer le délai prélèvement → résultat et ses différentes composantes ;
6. déterminer la quantité de données nécessaire à une classification correcte et stable ;
7. caractériser les échecs, non-classifications et discordances ;
8. étudier l'effet de la cellularité tumorale, de la nécrose et de la qualité de l'ADN ;
9. documenter les informations complémentaires accessibles, notamment les CNV et `MGMT`, et selon le workflow certaines altérations structurales ou de séquence ;
10. mesurer la proportion de cas pour lesquels le résultat nanopore apporte une information diagnostique additionnelle ;
11. documenter la proportion de cas NOS/NEC ou complexes dont la classification peut être précisée ;
12. mesurer le coût complet par patient et par résultat concluant ;
13. comparer plusieurs classifieurs pré-entraînés si cela reste pertinent après le benchmark de Toulouse ;
14. mesurer, dans les cas analysés rapidement, la proportion de résultats disponibles pendant la fenêtre de décision neurochirurgicale ;
15. préparer l'évaluation de l'impact réel du résultat sur la stratégie chirurgicale.

---

## 9. Architecture proposée du projet

### Phase A — benchmark et transfert de méthode

Cette phase sera réalisée avant le gel du protocole analytique.

Elle comprendra :

- retour d'expérience structuré du centre toulousain ;
- choix de la plateforme, de la flow cell et du kit ;
- choix de la méthode d'extraction et du QC ;
- choix du classifieur principal et, si utile, des comparateurs ;
- définition des seuils de confiance ;
- définition des sorties moléculaires ;
- définition du contrôle qualité ;
- estimation du coût complet ;
- définition du circuit d'interprétation neuropathologique ;
- analyse du cadre qualité/réglementaire permettant le passage au rendu clinique.

### Phase B — qualification/vérification locale courte

Cette phase utilisera un nombre limité de cas représentatifs, idéalement avec diagnostic intégré de référence connu ou obtenu indépendamment.

Elle devra vérifier :

- qualité de l'ADN ;
- taux de succès technique ;
- reproductibilité ;
- concordance de classification ;
- robustesse des seuils ;
- cohérence des profils CNV ;
- délai réel ;
- fonctionnement du pipeline ;
- traçabilité ;
- conditions du compte rendu.

Le nombre de cas sera défini par la finalité de la qualification et les exigences du laboratoire/qualité ; il ne sera pas dérivé d'une hypothèse arbitraire de cohorte de 100–200 patients.

### Phase C — évaluation prospective dans le circuit clinique

Après atteinte de critères de passage prédéfinis, les nouveaux cas seront analysés prospectivement.

Le résultat nanopore sera comparé au diagnostic intégré final. Selon le cadre validé, il pourra soit rester masqué pendant une phase transitoire, soit être intégré au diagnostic clinique sous responsabilité du neuropathologiste.

Les critères de cette phase devront inclure :

- diagnostic yield ;
- concordance ;
- délai ;
- cas résolus ou reclassés ;
- examens complémentaires évités ou orientés ;
- informations CNV/`MGMT`/autres utiles ;
- coût complet ;
- proportion de résultats disponibles avant les principales décisions cliniques.

### Phase D — évaluation périopératoire

La phase D ne sera activée que si le workflow est qualifié pour l'usage prévu et si le cadre réglementaire permet que le résultat contribue au soin.

Deux scénarios doivent être distingués.

**Scénario 1 — rendu clinique décisionnel autorisé dans le cadre du projet.**  
Le résultat peut être communiqué à la neuropathologie/neurochirurgie pendant l'intervention. L'étude mesurera alors l'impact réel sur la décision.

**Scénario 2 — rendu décisionnel non compatible avec le cadre de l'AAP.**  
Le workflow sera exécuté en temps réel mais le résultat ne modifiera pas le geste dans le protocole de recherche. Les délais seront enregistrés et l'équipe déterminera prospectivement si le résultat aurait été disponible au moment où une décision pouvait être modifiée. Cette phase préparera un protocole clinique distinct.

Cette distinction est indispensable car l'AAP Jeunes Chercheurs Tremplin 2026 n'autorise pas les RIPH1.

---

## 10. Population et prélèvements

Les patients seront pris en charge pour une tumeur du SNC et disposeront d'un prélèvement compatible avec le diagnostic de routine.

Le workflow nanopore reposera préférentiellement sur du tissu tumoral congelé, cohérent avec :

- la qualité de l'ADN nécessaire aux analyses long-read ;
- les recommandations françaises de conservation de matériel tumoral pour les analyses moléculaires ;
- les workflows nanopore publiés.

La représentativité tumorale devra être vérifiée par un neuropathologiste sur le fragment ou une section adjacente.

Seront enregistrés :

- type de prélèvement ;
- cellularité tumorale ;
- nécrose ;
- proportion de tissu non tumoral ;
- masse de tissu ;
- quantité d'ADN ;
- qualité/intégrité de l'ADN ;
- principales variables pré-analytiques.

La population de la phase clinique devra être aussi consécutive que possible afin de ne pas sélectionner uniquement les tumeurs faciles à classifier.

---

## 11. Standard diagnostique de référence

Le standard de référence restera le **diagnostic intégré final** établi par la neuropathologie selon la classification des tumeurs du SNC en vigueur, à partir de la morphologie, de l'immunohistochimie, des analyses moléculaires conventionnelles et des autres éléments nécessaires.

Le résultat du classifieur de méthylation ne doit jamais être considéré comme un diagnostic autonome. Il sera interprété dans le contexte des données histologiques, moléculaires et cliniques.

Une procédure spécifique sera définie pour :

- cas NOS ;
- cas NEC ;
- résultats de méthylation sous le seuil de confiance ;
- classes inattendues ;
- discordances entre classifieur et données morphologiques/génétiques ;
- nécessité d'une méthode orthogonale pour confirmer une fusion ou une altération thérapeutique.

---

## 12. Workflow nanopore

### 12.1. Choix technique provisoire

Les références `SQK-RBK114.24` et `FLO-MIN114`, utilisées dans la v0.1 et dans le budget actuel, restent des hypothèses de travail et **ne doivent plus être présentées comme définitivement choisies**.

Le choix final sera effectué après le benchmark toulousain et devra tenir compte :

- du délai de préparation ;
- de la quantité d'ADN requise ;
- de la conservation du signal de méthylation ;
- du rendement ;
- de la possibilité de multiplexage ;
- du coût réel ;
- de la reproductibilité ;
- de la compatibilité avec le classifieur et les sorties secondaires ;
- de la possibilité d'un workflow périopératoire.

### 12.2. Pipeline bioinformatique

Le pipeline comprendra au minimum :

1. basecalling ;
2. alignement sur le génome de référence ;
3. appel de méthylation ;
4. génération des features nécessaires au classifieur ;
5. classification ;
6. score de confiance ;
7. profil CNV ;
8. métriques de qualité ;
9. horodatage des étapes pour l'analyse de délai.

Les analyses supplémentaires (`MGMT`, SNV/indels, SV, fusions) seront intégrées uniquement si le workflow choisi les permet avec une performance et un délai compatibles avec la finalité clinique.

Le code, les versions des modèles et les paramètres seront versionnés et gelés pour chaque phase d'analyse.

---

## 13. Classifieurs

Les méthodes actuellement envisagées sont :

- crossNN/nanoDx ;
- MethyLYZR ;
- Sturgeon ;
- MNP-Flex, sous réserve d'accessibilité ;
- éventuellement le classifieur utilisé dans le centre toulousain si celui-ci est différent et transférable.

Le projet n'a pas pour objectif principal de développer un nouveau modèle. Une comparaison de plusieurs classifieurs n'est pertinente que si elle répond à une question clinique ou de robustesse et ne doit pas alourdir inutilement l'implémentation.

Aucun réentraînement sur la cohorte locale ne sera utilisé pour gonfler artificiellement les performances de la phase principale.

---

## 14. Critères de jugement

### 14.1. Phase B — qualification locale

Critères possibles :

- taux de succès technique ;
- répétabilité/reproductibilité selon le plan qualité ;
- concordance avec la classification de référence ;
- concordance CNV ;
- délai ;
- taux de résultats sous le seuil ;
- causes d'échec.

Les seuils de passage à la phase C devront être prédéfinis.

### 14.2. Phase C — clinique prospective

Le critère principal sera défini avec l'URCE après choix du design final. Les mesures prioritaires sont :

- proportion de patients avec résultat interprétable ;
- concordance avec le diagnostic intégré final ;
- proportion de cas pour lesquels le résultat apporte une information diagnostique utile ;
- délai prélèvement → résultat ;
- proportion de résultats rendus dans le délai cible.

Les critères secondaires incluront :

- diagnostic yield ;
- exactitude parmi les résultats conclusifs ;
- cas NOS/NEC résolus ;
- nombre d'examens complémentaires orientés ou évités ;
- CNV et autres informations pertinentes ;
- coût complet ;
- facteurs associés aux échecs.

### 14.3. Phase D — périopératoire

Si le résultat peut être utilisé pendant l'intervention :

- proportion d'interventions avec résultat disponible dans la fenêtre décisionnelle ;
- concordance avec l'extemporané ;
- concordance avec le diagnostic final ;
- proportion de décisions confirmées ;
- proportion de stratégies modifiées ;
- direction de la modification : résection poursuivie ou limitée ;
- étendue de résection ;
- second-look/reprise ;
- déficit neurologique postopératoire ;
- paramètres fonctionnels et qualité de vie lorsque cela est possible.

Si le résultat ne peut pas être utilisé décisionnellement dans le présent protocole, les métriques de délai et la disponibilité théorique pendant la fenêtre opératoire seront néanmoins recueillies.

---

## 15. Analyse statistique

Le plan statistique final dépendra du design retenu après discussion avec l'URCE.

### Principe général

Il faut distinguer trois questions différentes :

1. **qualification locale** : démontrer que le workflow transféré fonctionne dans l'environnement local ;
2. **performance clinique** : estimer sa capacité à produire un résultat exact et utile sur des patients consécutifs ;
3. **impact clinique** : mesurer si un résultat disponible rapidement modifie effectivement une décision ou un parcours de soins.

Ces questions ne doivent pas être artificiellement fondues dans un unique calcul d'effectif.

### Phase B

Le nombre de cas sera fondé sur les exigences de validation/qualification de la méthode et sur la couverture des principaux types de résultats attendus. Une large puissance statistique n'est pas nécessairement l'objectif de cette phase.

### Phase C

Les estimations principales seront accompagnées d'intervalles de confiance à 95 %. Les analyses pourront inclure :

- taux de résultat concluant ;
- exactitude diagnostique ;
- analyse intention-to-diagnose ;
- matrices de confusion ;
- analyses par grande famille tumorale lorsque l'effectif le permet ;
- relation entre succès et cellularité/qualité d'ADN ;
- distribution des délais.

### Cinétique

Les données nanopore étant acquises en continu, la classification pourra être recalculée à différents temps ou quantités cumulées de données. Les temps exacts seront définis selon le workflow réel après benchmark.

Le **temps jusqu'à une classification correcte et stable** restera un indicateur important.

---

## 16. Réglementation, qualité et passage au soin

Le passage rapide à une utilisation clinique est un objectif du projet, mais il doit être organisé explicitement.

L'EANO rappelle que les classifieurs de méthylation disponibles ne sont pas, en eux-mêmes, des dispositifs CE-IVD et que l'utilisation diagnostique locale doit respecter le cadre applicable aux tests développés en laboratoire, à l'IVDR et à l'accréditation.

Le projet devra donc définir avec le laboratoire, la qualité, l'URCE et la DRI :

- qualification réglementaire de chaque phase ;
- statut du workflow comme LDT ou autre cadre applicable ;
- exigences de l'IVDR et de l'article 5(5) le cas échéant ;
- exigences ISO 15189 ;
- validation/vérification analytique nécessaire ;
- contrôles qualité internes ;
- traçabilité ;
- validation biologique/neuropathologique ;
- format et responsabilité du compte rendu ;
- règles de conservation des données génomiques ;
- conditions précises autorisant l'utilisation du résultat pour le soin.

> **POINT AAP**  
> L'AAP Jeunes Chercheurs Tremplin 2026 est limité aux cadres réglementaires éligibles définis dans son cahier des charges et exclut les RIPH1. Toute phase dans laquelle le résultat expérimental est susceptible de modifier directement le geste chirurgical doit donc être discutée explicitement avec l'URCE/DRI avant d'être incluse dans le protocole financé.

---

## 17. Budget

Le budget actuel fondé sur `FLO-MIN114`, `SQK-RBK114.24` et un scénario de 150 patients ne doit plus être considéré comme le scénario principal.

Il reste utile comme **modèle de sensibilité**, mais le budget final devra être reconstruit à partir :

- du workflow toulousain réellement utilisé ;
- des prix marché CHU Montpellier ;
- du niveau de multiplexage ;
- de la taille de la phase B ;
- de l'effectif clinique réaliste de la phase C ;
- du nombre de runs rapides/singleplex nécessaires ;
- des coûts CRB ;
- des coûts de validation/qualité ;
- des coûts de méthodologie/promotion ;
- du temps technicien/biologiste/bioinformaticien ;
- du stockage et de la gestion des données lorsque ces coûts doivent être valorisés.

Le coût pertinent à rapporter ne sera pas seulement le coût des consommables par échantillon, mais également le **coût complet par résultat clinique concluant**.

---

## 18. Organisation du projet

Le projet nécessite dès sa conception :

- neuropathologie ;
- biologie moléculaire / PMMG ;
- bioinformatique clinique ;
- CRB/tumorothèque ;
- neurochirurgie ;
- méthodologie/biostatistiques ;
- qualité/accréditation ;
- DRI/URCE.

La neurochirurgie ne doit plus être considérée uniquement comme partenaire d'une étude ultérieure. Elle doit participer à la définition :

- de la fenêtre temporelle réellement utile ;
- des situations où le diagnostic moléculaire pourrait modifier la stratégie ;
- des critères de décision ;
- des endpoints fonctionnels et chirurgicaux d'une phase périopératoire.

> **TO DO — ÉQUIPE**
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
> | Qualité / accréditation |  |  |  |

---

## 19. Calendrier conceptuel

### Étape 1 — transfert et cadrage

- échange Toulouse ;
- verrouillage du workflow ;
- prix réels ;
- circuit qualité ;
- protocole final ;
- qualification réglementaire.

### Étape 2 — qualification locale

- cas représentatifs ;
- reproductibilité ;
- concordance ;
- délai ;
- QC ;
- critères de passage.

### Étape 3 — prospective clinique

- inclusion consécutive ;
- analyse en routine expérimentale puis clinique selon autorisation ;
- suivi des délais, performances, apports diagnostiques et coûts.

### Étape 4 — périopératoire

- activation si les conditions de soin et le cadre AAP le permettent ;
- sinon préparation immédiate d'un protocole distinct sur la base des données de temps réel acquises.

Cette progression permet de ne pas consacrer la totalité des trois années à une validation technique alors que la littérature et l'expérience d'autres centres justifient un transfert plus rapide vers la clinique.

---

## 20. Résultats attendus

Le projet doit permettre :

1. de disposer au CHU Montpellier d'un workflow nanopore documenté et qualifié pour la classification moléculaire des tumeurs du SNC ;
2. de connaître son taux de succès, son exactitude, ses limites et ses causes d'échec ;
3. de disposer d'un délai réel prélèvement → résultat ;
4. d'estimer le nombre de cas pour lesquels le résultat modifie ou précise le diagnostic ;
5. de caractériser les informations de CNV et autres données obtenues à partir du même run ;
6. de documenter le coût complet d'une utilisation hospitalière ;
7. de définir les conditions de passage au rendu clinique ;
8. d'établir la proportion de cas pour lesquels l'information pourrait être disponible pendant la fenêtre neurochirurgicale ;
9. de produire les données nécessaires à une étude d'impact clinique, voire de l'intégrer au projet si le cadre réglementaire le permet.

---

## 21. Effet levier

Le projet répond à un besoin qui dépasse une comparaison technique de plateformes. Il vise à rapprocher le diagnostic moléculaire intégré du moment où les décisions cliniques sont prises.

L'effet levier attendu est triple :

- **diagnostique** : accès local rapide à une information recommandée ou nécessaire pour certaines entités ;
- **organisationnel** : réduction du délai lié aux envois externes et aux analyses séquentielles lorsque le nanopore peut regrouper plusieurs informations ;
- **clinique** : préparation d'une utilisation périopératoire susceptible de modifier la stratégie neurochirurgicale chez certains patients.

Ces résultats pourront soutenir une publication princeps, la structuration d'un parcours diagnostique local et un projet multicentrique ultérieur centré sur l'impact clinique.

---

## 22. Risques et mesures de contrôle

### Risque : transposer trop rapidement une méthode sans qualification locale

**Contrôle :** phase B dédiée, critères de passage prédéfinis, implication qualité/accréditation.

### Risque : prolonger inutilement la validation et ne jamais atteindre la clinique

**Contrôle :** phase B volontairement dimensionnée selon sa finalité réglementaire, critères de transition vers la phase C définis avant le démarrage.

### Risque : surinterpréter le classifieur

**Contrôle :** interprétation neuropathologique intégrée ; pas de diagnostic autonome ; méthode orthogonale si nécessaire.

### Risque : résultat sous le seuil ou classe inattendue

**Contrôle :** règles de non-rendu, répétition ou investigation complémentaire définies a priori.

### Risque : échec lié au prélèvement

**Contrôle :** sélection du fragment, contrôle de cellularité, nécrose, quantité et qualité d'ADN.

### Risque : workflow trop coûteux pour le périopératoire

**Contrôle :** coût complet documenté par phase ; benchmark Toulouse ; choix raisonné du multiplexage.

### Risque : phase décisionnelle non éligible à l'AAP

**Contrôle :** arbitrage URCE/DRI avant le gel du protocole ; possibilité de conserver dans l'AAP une phase temps-réel non décisionnelle et de basculer l'impact chirurgical dans un protocole ultérieur.

---

## 23. Bibliographie principale

La bibliographie complète est conservée dans `references.bib`. Les références institutionnelles et scientifiques les plus directement liées au présent cadrage sont :

1. WHO Classification of Tumours Editorial Board. *Central Nervous System Tumours*. WHO Classification of Tumours, 5th Edition, Volume 6. IARC; 2021.
2. Louis DN, et al. The 2021 WHO Classification of Tumors of the Central Nervous System: a summary. *Neuro-Oncology*. 2021;23:1231-1251. doi:10.1093/neuonc/noab106.
3. Capper D, et al. DNA methylation-based classification of central nervous system tumours. *Nature*. 2018;555:469-474. doi:10.1038/nature26000.
4. Sahm F, et al. Molecular diagnostic tools for the WHO 2021 classification of gliomas, glioneuronal and neuronal tumors; an EANO guideline. *Neuro-Oncology*. 2023;25:1731-1749. doi:10.1093/neuonc/noad100.
5. Aldape K, et al. cIMPACT-NOW update 9: Recommendations on utilization of genome-wide DNA methylation profiling for CNS tumor diagnostics. *Neuro-Oncology Advances*. 2025;7:vdae228. doi:10.1093/noajnl/vdae228.
6. Wesseling P, et al. *Tumours of the Central Nervous System (CNS) Reporting Guide*. 2nd ed. ICCR; 2024.
7. Otth M, et al. Overview of European standard clinical practice recommendations for multidisciplinary teams involved in the treatment of CNS tumours in children and adolescents — SIOPE Brain Tumour Group. *EJC Paediatric Oncology*. 2024;3:100166. doi:10.1016/j.ejcped.2024.100166.
8. Bailey S, et al. Medulloblastoma therapy: Consensus treatment recommendations from SIOP-Europe and the European Reference Network. *EJC Paediatric Oncology*. 2025;5:100205. doi:10.1016/j.ejcped.2024.100205.
9. Wesseling P, et al. cIMPACT-NOW update 11: Proposal on adaptation of diagnostic criteria for IDH- and H3-wildtype diffuse high-grade gliomas and for posterior fossa ependymal tumors. *Brain Pathology*. 2026;36:e70035. doi:10.1111/bpa.70035.
10. ANOCEF. *Référentiel Glioblastome 2025*.
11. Fontaine A, et al. Le méthylome ou l'avenir de la neuro-oncologie ? *Médecine/Sciences*. 2025;41:570-577. doi:10.1051/medsci/2025095.
12. Djirackor L, et al. Intraoperative DNA methylation classification of brain tumors impacts neurosurgical strategy. *Neuro-Oncology Advances*. 2021;3:vdab149. doi:10.1093/noajnl/vdab149.
13. Vermeulen C, et al. Ultra-fast deep-learned CNS tumour classification during surgery. *Nature*. 2023;622:842-849. doi:10.1038/s41586-023-06615-2.
14. Brändl B, et al. Rapid brain tumor classification from sparse epigenomic data. *Nature Medicine*. 2025;31:840-848. doi:10.1038/s41591-024-03435-3.
15. Patel A, et al. Prospective, multicenter validation of a platform for rapid molecular profiling of central nervous system tumors. *Nature Medicine*. 2025;31:1567-1577. doi:10.1038/s41591-025-03562-5.
16. Deacon S, et al. ROBIN: A unified nanopore-based assay integrating intraoperative methylome classification and next-day comprehensive profiling for ultra-rapid tumor diagnosis. *Neuro-Oncology*. 2025;27:2035-2046. doi:10.1093/neuonc/noaf103.
17. Filser M, et al. Nanopore sequencing as a cutting-edge technology for medulloblastoma classification. *Neuro-Oncology*. 2025;27:1313-1324. doi:10.1093/neuonc/noae279.

Voir également `methylome_guidelines_and_clinical_implementation_rationale_2026-09-09.md` pour l'argumentaire détaillé et les formulations à utiliser ou éviter.

---

## 24. Éléments à verrouiller avant version v1.0

### Priorité immédiate

- [ ] échange opérationnel avec Toulouse ;
- [ ] workflow réel transférable ;
- [ ] prix réels et coût complet ;
- [ ] qualification réglementaire et qualité ;
- [ ] distinction précise entre phase B, phase C et éventuelle phase D ;
- [ ] critères de passage entre phases.

### Données locales

- [ ] nombre annuel de tumeurs du SNC ;
- [ ] nombre de prélèvements congelés exploitables ;
- [ ] composition tumorale de la cohorte ;
- [ ] faisabilité d'un circuit prélèvement → PMMG → résultat rapide.

### Protocole

- [ ] plateforme et flow cell ;
- [ ] kit ;
- [ ] extraction ;
- [ ] QC ADN ;
- [ ] multiplexage par phase ;
- [ ] classifieur(s) ;
- [ ] seuils ;
- [ ] sorties CNV/`MGMT`/autres ;
- [ ] format du compte rendu ;
- [ ] critères de non-rendu ;
- [ ] effectifs par phase après avis URCE ;
- [ ] calendrier.

---

## 25. Statut de cette version

La v0.2 constitue le nouveau cadrage scientifique du projet. Elle conserve les acquis de la v0.1 — faisabilité locale, littérature nanopore, intérêt périopératoire, analyse des classifieurs et réflexion budgétaire — mais modifie la logique générale : **la technologie est suffisamment mature pour justifier un transfert clinique structuré ; la question n'est plus de réaliser une longue démonstration locale du principe avant d'envisager le soin.**

La prochaine révision doit être faite après le retour de Toulouse et l'avis URCE/DRI/qualité, car ces éléments détermineront le workflow, le budget, le nombre de cas de qualification et la possibilité d'inclure une véritable phase périopératoire dans l'AAP.
