# Profilage pangénomique de méthylation dans les tumeurs du SNC : recommandations, justification clinique et implications pour le projet nanopore

**Date :** 9 septembre 2026  
**Statut :** document scientifique de cadrage destiné à enrichir le projet AAP Jeunes Chercheurs Tremplin 2026 et les versions ultérieures du protocole/manuscrit.  
**Projet concerné :** mise en place d'un workflow Oxford Nanopore pour la classification moléculaire rapide des tumeurs du système nerveux central (SNC), à partir de tissu tumoral, avec perspective d'utilisation clinique et périopératoire.

---

## 1. Message principal

Le profilage pangénomique de méthylation de l'ADN n'est plus un examen de recherche marginal en neuropathologie. Il est intégré à la classification OMS 2021 des tumeurs du SNC, fait partie des critères essentiels ou désirables de plusieurs entités, est explicitement recommandé par l'EANO comme une capacité diagnostique à laquelle tout centre prenant en charge des tumeurs du SNC devrait avoir accès, et a été intégré en 2024 par l'International Collaboration on Cancer Reporting (ICCR) parmi les éléments moléculaires du compte rendu diagnostique standardisé. Les recommandations cIMPACT-NOW de 2025-2026 ont encore renforcé ce rôle et fournissent des situations dans lesquelles l'absence de profilage de méthylation empêche d'atteindre une classification moléculaire complète.

Il serait cependant incorrect d'écrire qu'un méthylome pangénomique est actuellement obligatoire pour toute tumeur cérébrale. Le niveau de nécessité dépend du type tumoral, du diagnostic différentiel et des autres données morphologiques et moléculaires. Le point défendable est plus précis : **l'accès au profilage pangénomique de méthylation est désormais une composante du diagnostic moderne des tumeurs du SNC, et pour certaines entités il est nécessaire à l'établissement du diagnostic intégré complet.**

Cette évolution rend pertinente l'évaluation de technologies capables de produire rapidement cette information. Le séquençage Oxford Nanopore présente un intérêt particulier car il mesure directement la méthylation sur ADN natif, produit les données en continu et peut fournir, à partir d'un même run, une classification épigénétique ainsi que des informations complémentaires de nombre de copies et, selon le workflow, de séquence ou de structure. Plusieurs études prospectives et multicentriques ont maintenant démontré que cette information peut être obtenue dans un délai compatible avec la période périopératoire.

Pour le projet montpelliérain, le positionnement scientifique ne devrait donc pas être limité à une large « validation locale » académique préalable à toute utilisation clinique. Un schéma plus pertinent est : **transfert et qualification rapide du workflow, vérification locale sur un nombre limité de cas représentatifs, puis évaluation prospective de son intégration au diagnostic clinique et, si le cadre réglementaire et qualité le permet, de son utilisation périopératoire avec la neuropathologie et la neurochirurgie.**

---

## 2. Pourquoi le méthylome est devenu important dans la classification des tumeurs du SNC

La classification des tumeurs du SNC a évolué d'une classification principalement morphologique vers un diagnostic intégré combinant histologie, immunohistochimie et données moléculaires. Cette évolution s'est accélérée avec la cinquième édition de la classification OMS des tumeurs du SNC (WHO CNS5, 2021).

Le profil de méthylation de l'ADN fournit une information différente d'un panel de mutations. Il reflète en partie l'identité cellulaire et les programmes épigénétiques de la tumeur. Des tumeurs morphologiquement proches peuvent présenter des signatures de méthylation très différentes, tandis que des tumeurs présentant des variations histologiques importantes peuvent appartenir à une même classe moléculaire. Le classifieur développé initialement par Capper et al. a démontré à grande échelle que ces signatures permettent une classification reproductible de nombreuses tumeurs du SNC et peuvent conduire à la révision de diagnostics morphologiques ou moléculaires antérieurs.

Dans une logique diagnostique, le profilage pangénomique de méthylation peut répondre à plusieurs questions :

- résoudre un diagnostic différentiel non tranché par la morphologie et les marqueurs ciblés ;
- identifier une classe ou sous-classe tumorale qui n'est pas accessible par une anomalie génétique unique ;
- confirmer ou contredire une hypothèse diagnostique lorsque les données morphologiques, immunohistochimiques et génétiques sont discordantes ;
- fournir simultanément un profil de nombre de copies à l'échelle du génome ;
- contribuer à l'interprétation du statut du promoteur de `MGMT` dans certains workflows ;
- identifier des situations dans lesquelles une analyse moléculaire orthogonale supplémentaire est nécessaire.

Le méthylome ne doit donc pas être présenté comme un remplacement de l'anatomopathologie. Les recommandations actuelles le considèrent comme une donnée à intégrer avec la morphologie, l'immunohistochimie, les altérations génomiques, l'âge, la localisation et le contexte clinique.

---

## 3. Classification OMS 2021 : une base diagnostique internationale

La **WHO Classification of Tumours, Central Nervous System Tumours, 5th edition, volume 6 (2021)** constitue le référentiel international de classification des tumeurs du SNC. L'IARC/OMS la décrit comme un standard international pour le diagnostic tumoral, intégrant histopathologie et pathologie moléculaire.

WHO CNS5 introduit ou consolide un grand nombre d'entités définies par des caractéristiques moléculaires. Pour certaines tumeurs, la classe de méthylation fait partie des critères diagnostiques essentiels ou désirables. Cette situation est explicitement reprise par les recommandations cIMPACT-NOW et EANO ultérieures.

La conséquence pratique est importante : le besoin de disposer d'une analyse de méthylation ne dépend plus uniquement d'un intérêt de recherche ou de sous-typage exploratoire. **Dans certaines situations, la classification OMS elle-même ne peut pas être appliquée de manière complète sans accès à cette information.**

Il faut néanmoins conserver une formulation rigoureuse : WHO CNS5 ne demande pas un profilage pangénomique de méthylation pour chaque tumeur du SNC. L'indication dépend de l'entité et du contexte diagnostique.

---

## 4. Recommandation EANO 2023 : l'accès au méthylome doit être disponible pour les centres diagnostiquant les tumeurs du SNC

La recommandation EANO publiée par Sahm et al. en 2023 est probablement l'un des textes les plus utiles pour justifier institutionnellement le projet.

Elle porte sur les outils moléculaires nécessaires à l'application de WHO CNS5 aux gliomes, tumeurs glioneuronales et neuronales. Elle émet notamment la recommandation de consensus suivante :

> **« Access to DNA methylation analysis, on-site or via referral, should be made available at any institution involved in the diagnostics of CNS tumors. »**

Cette recommandation est classée **C II ; niveau A**.

L'EANO précise également que :

- le résultat d'un classifieur de méthylation est une donnée diagnostique et non un diagnostic autonome ;
- il doit être interprété par un neuropathologiste expérimenté dans le cadre du diagnostic intégré ;
- les informations de CNV obtenues à partir du méthylome peuvent être utiles, mais certaines altérations, en particulier les fusions ou altérations thérapeutiques, nécessitent une confirmation orthogonale ;
- l'accès équitable au diagnostic histomoléculaire conforme à la classification OMS doit être recherché ;
- les grands centres sont encouragés à aider les autres centres à implémenter les nouvelles technologies et à fournir des échantillons pour leur validation ;
- le tissu congelé présente une qualité analytique particulièrement intéressante pour certaines technologies moléculaires, notamment les technologies long-read telles que Nanopore.

Le texte aborde aussi directement la question de l'implémentation clinique en Europe. Il rappelle que les classifieurs de méthylation disponibles ne sont pas en eux-mêmes des dispositifs CE-IVD et que les laboratoires utilisant ces méthodes à des fins diagnostiques doivent mettre en place la validation, la documentation et, lorsque nécessaire, l'accréditation correspondant au cadre réglementaire applicable aux tests développés en laboratoire.

Pour le projet, ce point doit être utilisé de manière constructive : **il justifie une phase locale de qualification/validation analytique, mais pas nécessairement une longue cohorte de recherche avant toute utilisation clinique.** Le nombre et la nature des cas nécessaires doivent être définis avec la neuropathologie, le laboratoire, la qualité, la DRI/URCE et, idéalement, à partir du retour d'expérience d'un centre français qui utilise déjà la technique.

---

## 5. cIMPACT-NOW update 9 (2025) : recommandations spécifiques sur le profilage pangénomique de méthylation

Le **cIMPACT-NOW update 9**, publié en 2025, est le premier texte de consensus entièrement consacré à l'utilisation du profilage pangénomique de méthylation dans le diagnostic des tumeurs du SNC.

Ses recommandations principales sont directement pertinentes :

1. le profilage de méthylation doit être envisagé lorsqu'il peut résoudre un diagnostic différentiel ;
2. il doit être priorisé lorsque le diagnostic est difficile, lorsque les résultats morphologiques et moléculaires sont discordants, lorsqu'un sous-typage moléculaire est nécessaire ou lorsque la classification par méthylation est la seule méthode permettant de définir le type tumoral ;
3. le profilage de méthylation est inclus parmi les critères essentiels ou désirables de nombreuses entités WHO CNS ;
4. le résultat doit toujours être interprété avec les autres données disponibles et faire l'objet d'une revue experte lorsque la classe obtenue est inattendue ou discordante.

Ce texte est important pour l'argumentaire car il transforme une pratique déjà répandue dans les centres experts en recommandations explicites de bonne utilisation diagnostique.

---

## 6. ICCR 2024 : le méthylome intégré au reporting moléculaire standardisé

L'**International Collaboration on Cancer Reporting (ICCR)** a publié en septembre 2024 la deuxième édition de son dataset international pour les tumeurs du SNC, mis à jour selon WHO CNS5.

Le dataset est structuré en trois parties : évaluation histologique, informations moléculaires, puis diagnostic final intégré. L'ICCR précise qu'un diagnostic complet doit idéalement être conforme aux diagnostics intégrés WHO CNS5 et que, pour la plupart des types tumoraux, cela nécessite désormais l'intégration d'analyses histologiques et complémentaires.

La mise à jour 2024 est particulièrement significative : **« Methylome profiling » a été ajouté parmi les éléments moléculaires core**, avec d'autres altérations devenues nécessaires pour refléter les critères diagnostiques essentiels de WHO CNS5.

Ce document est utile pour un projet hospitalier car il ne s'agit pas uniquement d'une revue scientifique : il s'agit d'un standard international de reporting anatomopathologique destiné à harmoniser le diagnostic des cancers.

---

## 7. Recommandations européennes pédiatriques SIOP-Europe / ERN PaedCan

Les recommandations européennes de pratique clinique pour les tumeurs du SNC de l'enfant et de l'adolescent vont également dans le sens d'un accès organisé au profilage de méthylation.

Le document SIOP-Europe Brain Tumour Group indique parmi les paramètres de qualité en neuropathologie la nécessité d'un **accès local ou par filière de recours à une plateforme de méthylation de l'ADN et au séquençage par panel de gènes**.

Pour le médulloblastome, les recommandations de consensus SIOP-Europe / ERN PaedCan publiées en 2024-2025 sont encore plus explicites. Elles recommandent que l'assignation au type moléculaire repose sur au moins deux méthodes validées indépendantes et indiquent que les méthodes de classification moléculaire doivent être fondées sur le **profilage de méthylation de l'ADN ou le profilage transcriptomique**, complétés par les analyses de séquence appropriées. Parmi les technologies ayant été utilisées en diagnostic clinique, le texte cite notamment :

- Illumina 850K/EPIC methylation array ;
- MS-MIMIC MassArray ;
- **Nanopore sequencing** ;
- Nanostring.

Cette référence est particulièrement importante pour le projet car elle montre que Nanopore n'est plus seulement cité dans des travaux méthodologiques : il apparaît dans un texte européen de recommandations comme l'une des technologies effectivement utilisées pour la classification moléculaire du médulloblastome.

---

## 8. cIMPACT-NOW update 11 (2025/2026) : exemple d'une entité pour laquelle l'absence de méthylome limite le diagnostic

Le **cIMPACT-NOW update 11**, publié en ligne en août 2025 et dans *Brain Pathology* en 2026, fournit un exemple particulièrement démonstratif avec les épendymomes de la fosse postérieure.

Pour un épendymome de fosse postérieure avec conservation de H3 K27me3 et absence de surexpression nucléaire d'EZHIP, le groupe indique que **la classification définitive en épendymome PFB nécessite un profilage de méthylation de l'ADN**. Si celui-ci n'est pas réalisé ou n'est pas concluant, le diagnostic doit rester **posterior fossa ependymoma, NOS**.

Autrement dit, dans cette situation, l'absence de méthylome n'est pas simplement une perte d'information supplémentaire : **elle empêche l'assignation complète à l'entité moléculaire.**

Le texte précise en outre que ces recommandations sont destinées à guider la pratique en amont de WHO CNS6. Elles ne constituent pas encore une modification formelle de la classification OMS, mais elles indiquent la direction prise par la taxonomie diagnostique actuelle.

---

## 9. WHO CNS6 : une nouvelle classification est en cours d'élaboration

En septembre 2026, la sixième édition de la classification OMS des tumeurs du SNC n'est pas encore publiée. L'IARC indique officiellement que le volume **Central Nervous System Tumours — 6th edition** est **« in progress »**.

La deuxième réunion de l'Editorial Board consacrée au volume CNS de la sixième édition s'est tenue les **29 et 30 avril 2026 à Lyon**.

Il serait donc excessif de prédire que WHO CNS6 imposera un méthylome pour toutes les tumeurs du SNC. En revanche, il est légitime d'écrire que :

- WHO CNS5 a déjà intégré la classe de méthylation dans plusieurs critères diagnostiques ;
- cIMPACT-NOW 9 a formalisé son utilisation diagnostique ;
- cIMPACT-NOW 11 propose des adaptations destinées à guider la pratique avant WHO CNS6 ;
- WHO CNS6 est actuellement en cours d'élaboration.

Le projet se situe donc dans une période de transition où la dépendance du diagnostic neuropathologique aux données moléculaires et épigénétiques augmente.

---

## 10. Situation française

### 10.1. Référentiel ANOCEF Glioblastome 2025

Le référentiel français **ANOCEF Glioblastome 2025** ne recommande pas un méthylome systématique pour tous les glioblastomes adultes.

Il indique cependant que, dans les cas de diagnostic difficile, le méthylome peut aider à classer la tumeur. Il souligne également que cette analyse fournit un profil pangénomique permettant d'identifier des anomalies chromosomiques clés telles que le gain du chromosome 7, la perte du chromosome 10 ou certaines amplifications, et qu'elle peut fournir une estimation du statut de méthylation du promoteur de `MGMT`.

Le même référentiel recommande de **congeler du matériel tumoral pour les analyses complémentaires de biologie moléculaire**, en rappelant que l'ADN extrait de matériel congelé est de meilleure qualité.

Pour le projet, cette recommandation est directement cohérente avec le choix d'un prélèvement tumoral congelé destiné au workflow nanopore.

### 10.2. Synthèse française 2025 sur le méthylome

Fontaine, Basset, Argentin et Rousseau, du CHU d'Angers, ont publié en 2025 dans *Médecine/Sciences* une synthèse consacrée à la place du méthylome en neuro-oncologie. Les auteurs rappellent que WHO CNS5 intègre les données de méthylation pour certains types tumoraux, parfois comme critère désirable et parfois comme critère essentiel, et que certaines entités nécessitent l'étude du méthylome pour une classification complète.

Cette publication n'est pas une recommandation nationale HAS ou INCa, mais elle constitue une synthèse française récente issue d'une équipe de neuropathologie ayant une expérience clinique de la méthode.

### 10.3. Ce qui n'a pas été identifié

À ce jour, aucun texte HAS ou INCa n'a été identifié imposant un profilage pangénomique de méthylation pour **toutes** les tumeurs cérébrales de l'adulte. Il ne faut donc pas formuler l'argumentaire de cette manière.

Le niveau de preuve institutionnel le plus solide repose actuellement sur la combinaison suivante : **WHO CNS5 + EANO + ICCR + cIMPACT-NOW + recommandations européennes pédiatriques + référentiels français par entité.**

---

## 11. Pourquoi Nanopore répond à un besoin qui n'est pas seulement analytique

La méthode actuellement la plus largement utilisée pour la classification de méthylation repose sur les arrays Illumina. Cette approche est robuste mais impose généralement un traitement par lots, une infrastructure dédiée et un délai de plusieurs jours à plusieurs semaines selon l'organisation locale.

Le séquençage Oxford Nanopore présente plusieurs caractéristiques susceptibles de réduire ce délai :

- lecture directe de l'ADN natif ;
- détection directe de la méthylation sans conversion au bisulfite ;
- acquisition des données en continu ;
- classification possible à faible couverture et à partir d'un nombre relativement limité de CpG informatifs ;
- possibilité de produire simultanément un profil de nombre de copies ;
- possibilité d'étendre l'analyse à certaines SNV/indels, SV, fusions ou au statut `MGMT` selon le workflow ;
- compatibilité avec des stratégies de séquençage rapide et potentiellement peropératoire.

Les études publiées avec nanoDx/crossNN, Sturgeon, MethyLYZR, Rapid-CNS2, iSCORED, ROBIN et d'autres approches convergent vers la faisabilité d'une classification fiable à partir de données nanopore peu profondes. Les validations prospectives récentes montrent que le problème scientifique n'est plus seulement de savoir si la classification est possible, mais **comment l'intégrer de manière robuste, rapide, réglementairement conforme et cliniquement utile dans un parcours hospitalier.**

---

## 12. Conséquence pour le positionnement du projet de Montpellier

Le projet actuel a été initialement rédigé comme une étude prospective de validation locale à large effectif, dans laquelle le résultat nanopore resterait expérimental pendant toute la première phase.

Ce positionnement peut être utile méthodologiquement, mais il risque d'être trop conservateur compte tenu :

1. de la maturité de la littérature ;
2. des recommandations actuelles sur l'accès au profilage de méthylation ;
3. des validations multicentriques déjà publiées ;
4. de l'existence de centres français ayant déjà une expérience opérationnelle de la méthode ;
5. de l'objectif réel du projet, qui est d'améliorer le diagnostic des patients et, à terme, de fournir une information moléculaire pendant que la décision chirurgicale reste modifiable.

### Positionnement recommandé

Le projet devrait être reformulé autour de l'**implémentation clinique accélérée d'un workflow nanopore de classification moléculaire des tumeurs du SNC**, avec des étapes de sécurité et de qualification clairement définies.

Une architecture possible serait :

### Phase A — transfert de méthode et benchmark inter-centres

Avant de figer le protocole local, recueillir auprès d'un centre français utilisant déjà la méthode, notamment le CHU/IUCT de Toulouse, les paramètres réels de fonctionnement : plateforme, flow cell, kit, extraction, quantité d'ADN, multiplexage, pipeline bioinformatique, classifieur, seuils, contrôle qualité, délai, taux d'échec, coût complet et organisation du rendu clinique.

Cette phase doit éviter de reconstruire localement un workflow dont les principaux choix ont déjà été éprouvés ailleurs.

### Phase B — qualification/vérification locale courte

Réaliser un nombre limité de cas représentatifs permettant de vérifier :

- qualité de l'extraction et de l'ADN ;
- reproductibilité technique ;
- concordance avec les diagnostics intégrés connus ;
- fonctionnement des classifieurs et seuils ;
- profil CNV et informations complémentaires attendues ;
- délai réel du workflow ;
- traçabilité et intégration au système qualité du laboratoire.

L'effectif de cette phase ne doit pas être arbitrairement fixé à une large cohorte de 100-200 patients. Il doit être déterminé en fonction de la finalité réglementaire et qualité : vérification locale d'une méthode transférée, validation d'un LDT, ou étude de performance clinique, selon le cadre finalement retenu.

### Phase C — évaluation prospective en conditions cliniques

Une fois les critères analytiques et qualité atteints, évaluer le workflow sur des cas prospectifs consécutifs dans le circuit de diagnostic réel, en association étroite avec la neuropathologie.

Les critères pertinents deviennent alors :

- proportion de cas avec résultat concluant ;
- concordance avec le diagnostic intégré final ;
- délai prélèvement-résultat ;
- proportion de cas dans lesquels le méthylome résout ou modifie le diagnostic ;
- proportion de cas NOS/NEC résolus ;
- informations de CNV ou autres données moléculaires cliniquement utiles obtenues en parallèle ;
- délai évité par rapport à l'adressage externe ou au workflow conventionnel ;
- impact sur les examens complémentaires nécessaires ;
- coût complet par diagnostic utile.

### Phase D — utilisation périopératoire avec la neurochirurgie

Si la phase précédente valide le workflow et si le cadre réglementaire permet le rendu du résultat en soin, une sous-cohorte périopératoire peut tester le résultat pendant l'intervention.

Les critères ne doivent alors plus se limiter à l'exactitude diagnostique. Il faut mesurer :

- délai jusqu'à une classification exploitable ;
- proportion d'interventions avec résultat disponible avant la fin du temps décisionnel ;
- concordance avec l'extemporané et le diagnostic intégré final ;
- cas dans lesquels le résultat confirme la stratégie prévue ;
- cas dans lesquels il modifie réellement la stratégie chirurgicale ;
- sens de la modification : poursuite de la résection ou limitation de la résection ;
- deuxième chirurgie évitée ou indiquée ;
- déficit neurologique postopératoire ;
- étendue de résection ;
- résultats fonctionnels et qualité de vie lorsque l'effectif le permet.

Cette architecture est plus directement alignée sur la valeur clinique attendue de la technologie.

---

## 13. Toulouse : benchmark opérationnel à documenter avant de figer le protocole

Des éléments publics confirment une expertise toulousaine pertinente :

- Emmanuelle Uro-Coste, anatomopathologiste à l'IUCT-Oncopole/CHU de Toulouse, est co-auteure de l'étude française de Filser et al. sur la classification des médulloblastomes par Nanopore ;
- Anne-Isabelle Bertozzi, oncologue pédiatre au CHU de Toulouse, est également co-auteure de cette étude ;
- une présentation d'Emmanuelle Uro-Coste au GFCO intitulée **« La classification diagnostique par Méthylome en 2024 »** mentionne explicitement une classification devenue plus rapide avec **« nanopore en extemporané »**.

Ces éléments justifient le contact prévu avec Toulouse, mais ils ne suffisent pas à déduire publiquement le workflow de routine exact. Il faut donc obtenir directement les informations opérationnelles.

### Questions à adresser au centre de Toulouse

1. **Matériel et séquençage** : séquenceur exact ; flow cell ; Rapid Barcoding vs Native Barcoding/Ligation ; version du kit ; quantité minimale et optimale d'ADN ; critères de qualité ; extraction utilisée ; singleplex ou multiplexage.
2. **Bioinformatique** : basecaller ; modèle de methylation calling ; classifieur utilisé ; version du classifieur ; référence de classes ; score minimal ; conduite à tenir pour les scores intermédiaires ; CNV ; `MGMT` ; autres altérations rapportées.
3. **Cinétique** : délai extraction-librairie ; temps de séquençage ; délai jusqu'au premier résultat ; délai jusqu'au rendu final ; taux de résultats non conclusifs.
4. **Organisation clinique** : qui prescrit ; qui interprète ; rôle du neuropathologiste ; format du compte rendu ; intégration avec l'extemporané ; interaction avec les neurochirurgiens ; fréquence d'utilisation réelle.
5. **Qualité et réglementation** : méthode utilisée comme LDT ou dans un autre cadre ; validation analytique réalisée ; nombre et type de cas de validation ; contrôles ; répétabilité/reproductibilité ; accréditation ISO 15189 ; documentation IVDR/Article 5(5) si applicable.
6. **Budget** : coût flow cell ; coût kit ; nombre de patients par run ; coût extraction/QC ; coût bioinformatique ; temps technicien/biologiste ; coût réel par patient concluant ; pertes liées aux runs incomplets.
7. **Retour d'expérience** : principaux échecs ; types tumoraux difficiles ; cellularité minimale ; impact de la nécrose ; qualité du tissu congelé ; gestion des cas NOS/NEC ; situations dans lesquelles Nanopore apporte une information réellement différente des examens de routine.

Les réponses à ces questions doivent être utilisées avant de figer le budget et le choix `FLO-MIN114` / `SQK-RBK114.24` actuellement utilisés comme hypothèses de travail dans le projet.

---

## 14. Texte proposé pour l'introduction scientifique du projet

Le passage suivant peut être adapté dans le manuscrit AAP :

> La classification des tumeurs du système nerveux central repose désormais sur un diagnostic intégré associant données histologiques et moléculaires. La cinquième édition de la classification OMS des tumeurs du SNC intègre le profil de méthylation de l'ADN parmi les critères essentiels ou désirables de plusieurs entités. Cette évolution a été renforcée par les recommandations EANO, qui indiquent qu'un accès au profilage de méthylation, localement ou par adressage, devrait être disponible dans tout établissement impliqué dans le diagnostic des tumeurs du SNC. Le cIMPACT-NOW update 9 a précisé en 2025 les situations dans lesquelles le profilage pangénomique de méthylation doit être priorisé, notamment lorsque le diagnostic est difficile, discordant ou lorsque la classe de méthylation est nécessaire à la définition de l'entité. L'ICCR a parallèlement intégré le profilage du méthylome parmi les éléments moléculaires core de son dataset 2024 pour le reporting des tumeurs du SNC. Pour certaines entités, cette dépendance est déjà explicite : cIMPACT-NOW update 11 indique par exemple qu'un épendymome de fosse postérieure ne peut être classé définitivement comme PFB sans profil de méthylation concordant et doit rester NOS lorsque cette analyse n'est pas disponible.
>
> Ces exigences croissantes créent un besoin de méthodes de profilage moléculaire à la fois larges, rapides et compatibles avec le fonctionnement hospitalier. Le séquençage Oxford Nanopore permet d'analyser directement l'ADN natif et sa méthylation, avec acquisition continue des données. Des workflows récents ont démontré qu'une classification de méthylation, accompagnée d'informations de nombre de copies et, selon les méthodes, d'autres altérations génomiques, peut être obtenue dans un délai compatible avec la période périopératoire. Le projet vise donc non seulement à vérifier la performance locale de cette approche, mais à préparer son intégration rapide dans le parcours diagnostique des tumeurs du SNC et son évaluation en situation clinique, notamment lorsque le résultat peut contribuer à la décision neurochirurgicale.

---

## 15. Formulations à utiliser et formulations à éviter

### Formulations scientifiquement défendables

- « Le profilage pangénomique de méthylation est intégré à la classification WHO CNS5 et constitue un critère essentiel ou désirable pour plusieurs entités. »
- « L'EANO recommande qu'un accès à l'analyse de méthylation, localement ou par adressage, soit disponible dans tout établissement impliqué dans le diagnostic des tumeurs du SNC. »
- « Pour certaines entités, l'absence de profilage de méthylation empêche une classification moléculaire complète. »
- « Les recommandations européennes pédiatriques intègrent l'accès à une plateforme de méthylation dans l'organisation diagnostique et citent Nanopore parmi les méthodes utilisées pour la classification moléculaire du médulloblastome. »
- « WHO CNS6 est en cours d'élaboration ; les mises à jour cIMPACT-NOW récentes fournissent des recommandations destinées à guider la pratique dans l'intervalle. »

### Formulations à éviter

- « Le méthylome est obligatoire pour toutes les tumeurs cérébrales. »
- « L'OMS exige un séquençage nanopore. »
- « Nanopore est déjà le standard de soin pour toutes les tumeurs du SNC. »
- « WHO CNS6 imposera le méthylome. »
- « Un résultat de classifieur de méthylation constitue à lui seul un diagnostic. »

---

## 16. Références principales

1. **WHO Classification of Tumours Editorial Board.** *Central Nervous System Tumours*. WHO Classification of Tumours, 5th Edition, Volume 6. Lyon: International Agency for Research on Cancer; 2021. ISBN 978-92-832-4508-7. https://publications.iarc.fr/601

2. **Louis DN, Perry A, Wesseling P, et al.** The 2021 WHO Classification of Tumors of the Central Nervous System: a summary. *Neuro-Oncology*. 2021;23(8):1231-1251. doi:10.1093/neuonc/noab106.

3. **Capper D, Jones DTW, Sill M, et al.** DNA methylation-based classification of central nervous system tumours. *Nature*. 2018;555:469-474. doi:10.1038/nature26000.

4. **Sahm F, Brandner S, Bertero L, et al.** Molecular diagnostic tools for the World Health Organization (WHO) 2021 classification of gliomas, glioneuronal and neuronal tumors; an EANO guideline. *Neuro-Oncology*. 2023;25(10):1731-1749. doi:10.1093/neuonc/noad100.

5. **Aldape K, Capper D, von Deimling A, et al.** cIMPACT-NOW update 9: Recommendations on utilization of genome-wide DNA methylation profiling for central nervous system tumor diagnostics. *Neuro-Oncology Advances*. 2025;7(1):vdae228. doi:10.1093/noajnl/vdae228.

6. **Wesseling P, Brat DJ, Hawkins C, et al.** *Tumours of the Central Nervous System (CNS) Reporting Guide*. 2nd ed., version 2.1. International Collaboration on Cancer Reporting; 2024. ISBN 978-1-922324-44-3. https://www.iccr-cancer.org/datasets/published-datasets/central-nervous-system/cns/

7. **Wesseling P, Capper D, Reifenberger G, et al.** cIMPACT-NOW update 11: Proposal on adaptation of diagnostic criteria for IDH- and H3-wildtype diffuse high-grade gliomas and for posterior fossa ependymal tumors. *Brain Pathology*. 2026;36(1):e70035. doi:10.1111/bpa.70035.

8. **Otth M, Scheinemann K, Ajithkumar T, et al.** Overview of European standard clinical practice recommendations for multidisciplinary teams involved in the treatment of central nervous system tumours in children and adolescents – SIOPE Brain Tumour Group. *EJC Paediatric Oncology*. 2024;3:100166. doi:10.1016/j.ejcped.2024.100166.

9. **Bailey S, Jacobs S, Kourti M, et al.** Medulloblastoma therapy: Consensus treatment recommendations from SIOP-Europe and the European Reference Network. *EJC Paediatric Oncology*. 2025;5:100205. doi:10.1016/j.ejcped.2024.100205.

10. **ANOCEF.** *Référentiel Glioblastome 2025*. Association des Neuro-Oncologues d'Expression Française; 2025. Section diagnostic moléculaire : utilisation du méthylome dans les cas diagnostiques difficiles et recommandation de congélation du matériel tumoral pour les analyses moléculaires.

11. **Fontaine A, Basset L, Argentin J, Rousseau A.** Le méthylome ou l'avenir de la neuro-oncologie ? *Médecine/Sciences*. 2025;41(6-7):570-577. doi:10.1051/medsci/2025095.

12. **Filser M, Torrejon J, Merchadou K, et al.** Nanopore sequencing as a cutting-edge technology for medulloblastoma classification. *Neuro-Oncology*. 2025;27(5):1313-1324. doi:10.1093/neuonc/noae279.

13. **Patel A, Göbel K, Ille S, et al.** Prospective, multicenter validation of a platform for rapid molecular profiling of central nervous system tumors. *Nature Medicine*. 2025;31(5):1567-1577. doi:10.1038/s41591-025-03562-5.

14. **Vermeulen C, Pagès-Gallego M, Kester L, et al.** Ultra-fast deep-learned CNS tumour classification during surgery. *Nature*. 2023;622:842-849. doi:10.1038/s41586-023-06615-2.

15. **Brändl B, Steiger M, Kubelt C, et al.** Rapid brain tumor classification from sparse epigenomic data. *Nature Medicine*. 2025;31(3):840-848. doi:10.1038/s41591-024-03435-3.

16. **IARC/WHO Classification of Tumours.** 6th edition future titles: Central Nervous System Tumours — in progress. Consulted 9 September 2026. https://whobluebooks.iarc.who.int/future-titles/

17. **International Agency for Research on Cancer.** Editorial Board meetings for the 6th edition of the WHO Classification of Tumours series, 27-30 April 2026; CNS Editorial Board meeting #2, 29-30 April 2026, Lyon. https://events.iarc.who.int/event/124/

---

## 17. Consignes pour les prochaines versions du projet

- Ne plus présenter par défaut le projet comme une cohorte de 100-200 patients exclusivement destinée à une validation locale avant toute utilisation clinique.
- Conserver une phase de vérification/qualification locale, mais définir son effectif à partir du cadre qualité/réglementaire et du retour d'expérience de Toulouse.
- Mettre l'objectif clinique au premier plan : disponibilité rapide d'une information diagnostique moléculaire conforme à l'évolution des standards de neuropathologie.
- Conserver le diagnostic intégré neuropathologique comme référence ; ne jamais présenter le classifieur comme autonome.
- Décrire explicitement les critères de passage d'une phase expérimentale à une phase de rendu clinique.
- Faire participer la neurochirurgie dès la conception des critères périopératoires, même si le premier run clinique n'est pas immédiatement utilisé pour modifier le geste.
- Intégrer les recommandations WHO/EANO/cIMPACT-NOW/ICCR/SIOPE/ANOCEF dans l'introduction et la justification.
- Utiliser le contact toulousain pour figer le matériel, les kits, le coût, le niveau de multiplexage, le pipeline, les seuils et les exigences qualité avant de finaliser le budget et la méthodologie.
