# GLOSSAIRE DOCUMENTAIRE — QUIZZZ FACTORY

Version : 2.0
Statut : Consolidé
Rôle : Couche d’interprétation documentaire destinée à harmoniser le comportement des IA dans les workflows FACTORY.
Documents de référence : BIB_[THEME].txt (base d’items brute) — MDE A3 (méthode de traitement BIB → BIPREGEN + ANGIPREGEN)

---

# ACCESSIBILITÉ GRAND PUBLIC

## Définition

Niveau de facilité avec lequel une référence peut être reconnue, comprise ou identifiée par un public large non spécialiste.

## Une forte accessibilité grand public implique généralement

- reconnaissance rapide,
- compréhension immédiate,
- faible besoin de connaissances spécialisées,
- forte présence culturelle ou médiatique,
- bonne compatibilité avec un quiz généraliste.

## Une faible accessibilité grand public implique généralement

- besoin de connaissances spécialisées,
- identification difficile,
- forte dépendance au contexte,
- exploitabilité plus limitée dans un quiz grand public.

## Important

- accessibilité grand public et qualité culturelle sont indépendantes,
- une œuvre prestigieuse peut rester peu accessible,
- une référence très populaire peut être extrêmement accessible malgré une faible profondeur documentaire.

## Comportement IA attendu

- préserver une base documentaire largement accessible,
- éviter une accumulation excessive de références peu accessibles,
- privilégier la reconnaissance et l’identification rapides dans les sections structurantes.

---

# ANGLE DOCUMENTAIRE

## Définition

Aspect précis, identifiable et non ambigu d’un item pouvant servir de base à une question distincte.

## Caractéristiques d’un angle valide

- information clairement identifiable,
- une seule réponse correcte possible,
- formulation exploitable en quiz,
- distinction claire avec les autres angles,
- absence d’ambiguïté majeure.

## Exemples d’angles possibles

- acteur principal,
- réalisateur,
- année de sortie,
- citation,
- récompense,
- univers,
- personnage,
- scène célèbre,
- record,
- musique associée.

## Important

- plusieurs angles peuvent exister pour un même item,
- deux angles très proches peuvent être considérés comme redondants,
- un angle trop évident ou trop faible peut être écarté.

## Comportement IA attendu

- privilégier les angles distincts,
- limiter les recouvrements entre sections,
- préserver la variété documentaire globale,
- éviter les formulations quasi identiques.

---

# ANGLE INTERROGEABLE

## Définition

Aspect précis, exploitable et non ambigu d’un item documentaire pouvant générer une seule question distincte de quiz.

Un angle interrogeable correspond à une information stable, identifiable et suffisamment spécifique pour éviter les doublons de génération.

Un même item peut posséder plusieurs angles interrogeables.

## Caractéristiques typiques

- porte sur une seule information principale,
- produit une question identifiable sans ambiguïté,
- reste distinct des autres angles du même item,
- possède un potentiel réel de jouabilité quiz,
- peut être plus ou moins pertinent selon le niveau documentaire ciblé,
- peut être conservé, réduit ou supprimé lors du rééquilibrage documentaire.

## Effets possibles

- augmentation ou réduction du potentiel de génération d’un item,
- création de risques de doublons si les angles sont trop proches,
- déséquilibre documentaire si certains items possèdent beaucoup plus d’angles exploitables que d’autres,
- nécessité de prioriser certains angles plus culturels ou plus jouables.

## Important

- un angle n’est pas une formulation de question,
- un angle est une unité documentaire exploitable,
- deux angles trop proches doivent être considérés comme redondants,
- tous les angles théoriquement possibles ne doivent pas forcément être conservés,
- les quotas d’angles restent indicatifs et documentaires,
- la cohérence culturelle et la qualité quiz priment sur la quantité d’angles.

## Comportement IA attendu

- identifier les angles réellement distincts,
- éviter les micro-variantes artificielles d’un même angle,
- privilégier les angles culturellement pertinents,
- signaler les redondances potentielles,
- éviter les angles trop faibles, triviaux ou non jouables,
- conserver une logique documentaire cohérente avec le profil choisi,
- ne pas multiplier artificiellement les angles pour atteindre un quota.

---

# ARBITRAGE DOCUMENTAIRE

## Définition

Décision consistant à privilégier une logique documentaire plutôt qu’une autre lorsqu’un conflit apparaît entre quotas, cohérence culturelle, variété ou exploitabilité quiz.

## Exemples fréquents

- conserver une section forte malgré un dépassement,
- réduire une section pourtant prestigieuse mais peu rentable,
- limiter certains angles trop redondants,
- privilégier la jouabilité plutôt que l’exhaustivité.

## Important

- les arbitrages sont contextuels,
- il n’existe pas de solution universelle,
- la cohérence globale reste prioritaire.

## Comportement IA attendu

- expliciter les arbitrages proposés,
- éviter les décisions mécaniques,
- privilégier la logique documentaire globale.

---

# BIB (BASE D'ITEMS DE BASE)

## Définition

Fichier source structuré contenant l'ensemble des items documentaires d'un thème, organisés en sections thématiques et classés par niveau de difficulté (N1 / N2 / N3).

Le BIB est le point de départ obligatoire de tout workflow FACTORY. Il est traité selon la méthode MDE A3 pour produire :
- BIPREGEN_[THEME].txt — version traitée, codée et équilibrée,
- ANGIPREGEN_[THEME].txt — carte des angles interrogeables par item.

## Structure typique

- sections thématiques nommées,
- items codés au format [THEME]-[CAT]-[N°]-[NIV],
- niveaux N1 (accessible), N2 (intermédiaire), N3 (expert).

## Règle fondamentale

Le BIB original (BIB_[THEME].txt) n'est jamais modifié après archivage. Il sert de référence AVANT pour toute vérification ultérieure.

## Comportement IA attendu

- ne jamais modifier le fichier BIB original,
- travailler exclusivement sur la version traitée (BIPREGEN),
- respecter la logique documentaire définie dans le BIB lors de la génération des angles et des questions.

---

# CARTOGRAPHIE DES ANGLES

## Définition

Travail documentaire consistant à identifier, répartir et organiser les angles interrogeables afin de limiter les redondances et préserver la variété globale des futures questions.

La cartographie des angles s’effectue :
- entre les items,
- entre les sections,
- et à l’échelle globale du BIB.

## Caractéristiques typiques

- repérage des angles trop proches,
- répartition des angles entre sections voisines,
- limitation des doublons documentaires,
- priorisation des angles les plus pertinents,
- conservation des angles les plus jouables,
- arbitrage entre variété et importance culturelle.

## Effets possibles

- réduction des répétitions futures,
- amélioration de la diversité quiz,
- meilleure rentabilité documentaire,
- limitation de la saturation documentaire,
- meilleure exploitation des sections fortes,
- diminution des conflits entre items proches.

## Important

- la cartographie des angles ne vise pas à supprimer toute redondance,
- certaines répétitions cohérentes peuvent être conservées,
- les univers structurants peuvent rester présents dans plusieurs sections,
- l’objectif principal est la variété réelle des questions générées,
- la cohérence culturelle prime sur l’optimisation mathématique parfaite.

## Comportement IA attendu

- détecter les angles susceptibles de produire les mêmes mécanismes de questions,
- répartir les angles entre sections proches lorsque cela améliore la variété,
- éviter la multiplication artificielle d’angles quasi identiques,
- préserver les angles les plus pertinents culturellement,
- signaler les risques élevés de redondance documentaire,
- ne pas supprimer automatiquement un angle uniquement parce qu’il existe ailleurs,
- privilégier la cohérence globale du futur système de génération.

---

# COHÉRENCE GLOBALE

## Définition

État d’un BIB dont les sections, volumes, niveaux et thèmes produisent un ensemble documentaire cohérent, exploitable et équilibré sans rigidité artificielle.

## Priorités d’évaluation (ordre décroissant)

1. cohérence culturelle,
2. jouabilité / exploitabilité quiz,
3. absence de redondance excessive,
4. équilibre documentaire général,
5. respect des quotas et fourchettes indicatives.

## Principes

- les objectifs chiffrés ne doivent pas dégrader la qualité documentaire,
- les déséquilibres cohérents sont autorisés,
- les ajustements doivent privilégier la pertinence globale plutôt que l’égalité mathématique.

---

# DENSITÉ DOCUMENTAIRE

## Définition

Quantité d’informations exploitables, connues et distinctes disponibles autour d’un thème, d’une section ou d’un item.

## Une forte densité documentaire implique généralement

- nombreux faits exploitables,
- nombreux angles de questions possibles,
- bonne variété de formulations,
- faible risque d’épuisement rapide,
- bonne profondeur documentaire.

## Une faible densité documentaire implique généralement

- peu d’angles exploitables,
- répétition rapide,
- faible variété de questions,
- risque élevé de redondance.

## Critères d’évaluation possibles

- quantité de faits connus du public cible,
- diversité des informations exploitables,
- richesse culturelle du sujet,
- variété des angles distincts,
- stabilité documentaire dans le temps.

## Important

- la densité documentaire est indépendante du prestige culturel,
- un sujet prestigieux peut avoir une faible densité quiz,
- un sujet populaire peut avoir une très forte densité documentaire.

---

# DÉSÉQUILIBRE COHÉRENT

## Définition

Déséquilibre documentaire volontaire considéré comme pertinent en raison du poids culturel, du potentiel quiz, de la densité documentaire ou de l’importance stratégique d’un thème ou d’une section.

## Principes

- les volumes des sections n’ont pas vocation à être uniformes,
- certaines sections peuvent être volontairement surreprésentées,
- certaines sections peuvent rester volontairement limitées malgré leur intérêt culturel.

## Causes possibles de déséquilibre cohérent

- forte notoriété,
- potentiel de génération très élevé,
- richesse documentaire exceptionnelle,
- importance structurante dans le thème,
- meilleure jouabilité quiz,
- stabilité culturelle forte.

## Comportement IA attendu

- ne pas corriger automatiquement un déséquilibre,
- vérifier d’abord si ce déséquilibre possède une justification documentaire,
- privilégier la cohérence globale plutôt que l’homogénéité mathématique.

---

# ÉQUILIBRAGE DOCUMENTAIRE

## Définition

Processus d’ajustement du volume, des niveaux, des sections et des angles d’un BIB afin d’obtenir un ensemble cohérent, jouable et durablement exploitable sans homogénéisation artificielle.

L’équilibrage documentaire vise à maintenir une cohérence globale compatible avec :
- le profil documentaire choisi,
- le public cible,
- la logique culturelle du thème,
- et les besoins futurs de génération.

## Caractéristiques typiques

- ajustement des volumes de sections,
- arbitrage entre profondeur et accessibilité,
- surveillance des déséquilibres excessifs,
- adaptation des niveaux N1 / N2 / N3,
- limitation des saturations documentaires,
- maintien de la variété quiz,
- conservation des sections structurantes fortes.

## Effets possibles

- amélioration de la jouabilité globale,
- meilleure stabilité des futures générations,
- réduction des répétitions,
- meilleure répartition des niveaux,
- limitation des enrichissements artificiels,
- augmentation de la durée de vie documentaire du quiz.

## Important

- l’équilibrage documentaire n’a pas pour objectif l’égalité mathématique,
- les quotas servent de guides et non de contraintes absolues,
- des déséquilibres cohérents peuvent être volontairement conservés,
- un équilibrage excessif peut produire une rigidification documentaire,
- la cohérence culturelle prime toujours sur la symétrie statistique.

## Comportement IA attendu

- analyser les déséquilibres avant de proposer des corrections,
- distinguer déséquilibre incohérent et déséquilibre justifié,
- éviter les rééquilibrages mécaniques,
- privilégier la qualité documentaire globale,
- signaler les sections sous-exploitées ou saturées,
- préserver les sections à forte rentabilité quiz,
- ne pas enrichir artificiellement une section faible uniquement pour atteindre une fourchette cible.

---

# EXPLOITABILITÉ QUIZ

## Définition

Capacité d’un thème, d’une section, d’un item ou d’un angle à produire des questions claires, intéressantes, variées et adaptées au format quiz.

## Une forte exploitabilité quiz implique généralement

- formulations naturelles,
- réponses identifiables,
- bonne jouabilité,
- variété de questions possible,
- compatibilité avec plusieurs niveaux de difficulté,
- faible ambiguïté.

## Une faible exploitabilité quiz implique généralement

- questions répétitives,
- formulations complexes,
- ambiguïtés fréquentes,
- faible variété documentaire,
- intérêt limité pour le joueur.

## Important

- un sujet culturellement prestigieux peut avoir une faible exploitabilité quiz,
- un sujet très populaire peut posséder une excellente exploitabilité même avec une profondeur limitée,
- l’exploitabilité quiz doit être évaluée selon le public cible et le format du projet.

## Comportement IA attendu

- privilégier les angles naturellement jouables,
- éviter les formulations artificielles ou trop techniques,
- préserver l’intérêt ludique du quiz.

---

# JOUABILITÉ QUIZ

## Définition

Capacité réelle d’une question, d’un angle ou d’un item à produire une expérience de jeu fluide, compréhensible et satisfaisante pour le joueur.

## Critères typiques

- compréhension rapide,
- absence d’ambiguïté,
- intérêt ludique,
- identification raisonnable,
- rythme compatible avec le format du quiz.

## Comportement IA attendu

- privilégier les formulations fluides,
- éviter les questions inutilement complexes,
- préserver le plaisir de jeu.

---

# ITEM

## Définition

Unité documentaire de base d'une BIB. Représente une référence culturelle, un fait, une œuvre, un personnage ou un événement exploitable pour la génération de questions.

## Caractéristiques

- appartient à une section thématique
- classé selon un niveau de difficulté (N1 / N2 / N3)
- codé au format `[THEME]-[CAT]-[N°]-[NIV]`
- peut produire un ou plusieurs angles interrogeables
- constitue l'unité de base de tout équilibrage documentaire

## Important

- un item n'est pas une question — c'est le matériau source dont sont extraites les questions
- un item peut avoir un fort intérêt culturel mais un faible potentiel de génération
- la valeur documentaire d'un item dépend du nombre d'angles interrogeables qu'il offre

## Comportement IA attendu

- traiter chaque item comme une unité indépendante lors de la cartographie des angles
- ne pas confondre item et question générée
- évaluer le potentiel de génération de chaque item avant d'assigner des angles

---

# LOGIQUE DE NOTORIÉTÉ

## Définition

Priorisation documentaire basée principalement sur la reconnaissance grand public, l’identification immédiate et la probabilité qu’une référence soit connue du public cible.

## Critères principaux

- notoriété grand public,
- visibilité culturelle durable,
- reconnaissance immédiate,
- présence dans la culture populaire,
- fréquence de réutilisation médiatique,
- accessibilité générationnelle.

## Référentiel prioritaire

La notoriété doit être évaluée principalement selon :

1. le public cible Quizzzz de Lolo,
2. la culture populaire généraliste,
3. la reconnaissance grand public française,
4. la portée internationale si pertinente pour le thème.

## Important

- la qualité artistique seule ne suffit pas à augmenter la priorité documentaire,
- une référence très prestigieuse mais peu identifiable peut rester secondaire,
- la notoriété actuelle et la stabilité culturelle priment généralement sur le prestige critique pur.

---

# PERTINENCE GÉNÉRALISTE

## Définition

Capacité d’un item, d’une section ou d’un angle à rester compréhensible, identifiable et exploitable par un large public non spécialiste.

## Critères principaux

- reconnaissance relativement large,
- accessibilité culturelle,
- compréhension sans expertise forte,
- compatibilité avec un quiz grand public,
- identification rapide par le public cible.

## Important

- la pertinence généraliste ne signifie pas uniquement “très connu”,
- un item peut être légèrement niche mais rester généraliste s’il est culturellement identifiable,
- la pertinence généraliste dépend du thème et du profil documentaire choisi.

## Comportement IA attendu

- éviter de surcharger le BIB en références trop spécialisées,
- conserver une base accessible au public cible,
- préserver un équilibre entre accessibilité et profondeur documentaire.

---

# POTENTIEL DE GÉNÉRATION

## Définition

Capacité d’une section ou d’un item à produire des questions variées, pertinentes et non redondantes.

## Échelle opérationnelle

| Niveau | Définition |
|---|---|
| Faible | Peu d’angles exploitables, répétition rapide, faible profondeur documentaire |
| Moyen | Nombre correct d’angles mais variété limitée à moyen terme |
| Fort | Bonne diversité d’angles, bonne exploitabilité quiz, faible répétition |
| Très fort | Très forte densité documentaire, nombreux angles distincts, excellente rentabilité quiz |

## Critères d’évaluation possibles

- diversité des angles,
- quantité de faits connus,
- variété des formulations,
- stabilité culturelle,
- risque de doublons,
- profondeur documentaire,
- accessibilité grand public.

---

# PROFIL DOCUMENTAIRE

## Définition

Configuration documentaire définissant l’équilibre cible entre accessibilité, difficulté, profondeur documentaire et exploitabilité quiz.

## Profils principaux

- CLASSIQUE,
- JEUNE PUBLIC,
- EXPERT,
- PERSONNALISÉ.

## Effets possibles

- modification des répartitions N1 / N2 / N3,
- adaptation du niveau moyen des références,
- variation de la profondeur documentaire,
- ajustement des angles retenus.

## Important

- les profils servent d’orientation documentaire,
- les proportions restent indicatives,
- le profil peut évoluer selon le thème traité.

## Comportement IA attendu

- adapter les propositions au profil choisi,
- éviter les contradictions entre profil et sélection documentaire,
- préserver la cohérence globale du quiz.

---

# PROFONDEUR DOCUMENTAIRE

## Définition

Capacité d’un thème, d’une section ou d’un item à rester exploitable sur de nombreux niveaux de questions et de nombreux angles distincts.

## Une forte profondeur documentaire implique généralement

- exploitation possible sur plusieurs niveaux de difficulté,
- nombreux faits distincts,
- angles variés,
- bonne résistance à l’épuisement,
- richesse documentaire durable.

## Une faible profondeur documentaire implique généralement

- peu d’informations réellement distinctes,
- répétition rapide des mêmes mécanismes de questions,
- faible renouvellement des angles.

## Important

- profondeur documentaire et notoriété sont indépendantes,
- un sujet très connu peut avoir une faible profondeur,
- un sujet moins populaire peut posséder une profondeur documentaire importante.

## Comportement IA attendu

- privilégier les sections profondes pour les volumes élevés,
- éviter de surestimer des thèmes uniquement populaires,
- tenir compte de la variété réelle des informations exploitables.

---

# QUOTAS SOUPLES

## Définition

Objectifs indicatifs servant de guide d’équilibrage documentaire. Les quotas peuvent être dépassés ou réduits si la cohérence culturelle, documentaire ou quiz le justifie.

## Principes opérationnels

- les quotas ne sont jamais des contraintes rigides,
- l’IA ne doit pas chercher une égalité mathématique artificielle,
- les écarts cohérents sont autorisés,
- la qualité documentaire prime sur les objectifs chiffrés.

## Comportement IA attendu

- signaler les écarts importants,
- ne proposer des corrections que si :
  - l’équilibre global devient incohérent,
  - une section devient disproportionnée,
  - ou le potentiel documentaire réel ne justifie plus le volume.

## Tolérance recommandée

- pas d’alerte pour les écarts faibles,
- alerte uniquement si :
  - dépassement important,
  - déséquilibre documentaire évident,
  - ou incohérence structurelle.

---

# REDONDANCE DOCUMENTAIRE

## Définition

Répétition excessive d’informations, d’univers, de formulations ou de mécanismes de questions dans un même BIB ou dans les futures générations.

## Formes fréquentes de redondance

- mêmes franchises dans plusieurs sections,
- mêmes informations exploitées sous plusieurs formulations,
- mêmes mécanismes de questions répétés,
- forte concentration autour des mêmes univers culturels.

## Effets négatifs possibles

- impression de répétition,
- baisse de variété quiz,
- épuisement rapide du contenu,
- réduction de l’intérêt ludique,
- déséquilibre documentaire.

## Important

- la redondance n’est pas automatiquement négative,
- certaines références structurantes peuvent volontairement apparaître dans plusieurs sections,
- la priorité reste la variété globale des angles réellement utilisés.

## Comportement IA attendu

- surveiller les recouvrements excessifs,
- répartir les angles entre sections proches,
- éviter les répétitions inutiles,
- préserver la diversité documentaire du quiz.

---

# RENTABILITÉ QUIZ

## Définition

Rapport entre le volume documentaire d’un thème et sa capacité réelle à produire un grand nombre de questions intéressantes, variées et exploitables.

## Une forte rentabilité quiz implique généralement

- nombreux angles exploitables,
- faible répétition,
- bonne jouabilité,
- forte variété de formulations,
- génération durable de contenu.

## Une faible rentabilité quiz implique généralement

- épuisement rapide des angles,
- répétition fréquente,
- faible variété documentaire,
- difficulté à produire des questions renouvelées.

## Important

- un thème très connu peut avoir une faible rentabilité quiz,
- un thème de taille modeste peut posséder une excellente rentabilité documentaire,
- la rentabilité quiz doit être évaluée sur le long terme et non sur quelques questions isolées.

## Comportement IA attendu

- privilégier les sections à forte rentabilité pour les volumes importants,
- éviter de surdimensionner des sections rapidement épuisables,
- prendre en compte la variété réelle des futurs angles.

---

# RÉÉQUILIBRAGE DOCUMENTAIRE

## Définition

Intervention visant à corriger un déséquilibre documentaire devenu problématique pour la cohérence globale, la variété quiz ou le profil documentaire ciblé.

## Interventions possibles

- reclassement de niveaux,
- réduction de sections,
- enrichissement ciblé,
- suppression d’angles redondants,
- ajustement des volumes.

## Important

- le rééquilibrage n’est pas automatique,
- les déséquilibres culturellement cohérents peuvent être conservés,
- toute modification importante nécessite validation humaine.

## Comportement IA attendu

- justifier les propositions de rééquilibrage,
- privilégier les corrections minimales,
- éviter les restructurations massives inutiles.

---

# RIGIDIFICATION DOCUMENTAIRE

## Définition

Transformation excessive de règles indicatives en contraintes strictes produisant un BIB artificiellement équilibré ou mécaniquement homogène.

## Signes fréquents de rigidification

- égalisation artificielle des volumes,
- suppression de déséquilibres culturellement pertinents,
- application mécanique des quotas,
- réduction forcée des sections fortes,
- enrichissement artificiel des sections faibles.

## Effets négatifs possibles

- perte de cohérence culturelle,
- baisse de qualité documentaire,
- diminution de l’exploitabilité quiz,
- homogénéisation artificielle,
- affaiblissement des sections structurantes.

## Important

- les quotas servent de guides et non de contraintes absolues,
- la cohérence documentaire prime sur l’équilibre mathématique,
- certains déséquilibres sont volontairement conservés.

## Comportement IA attendu

- éviter les corrections automatiques systématiques,
- privilégier l’analyse contextuelle,
- conserver les écarts documentaires justifiés,
- signaler les incohérences plutôt que normaliser systématiquement.

---

# RISQUE DE DOUBLON

## Définition

Probabilité qu’un angle, une information ou une logique de question soit déjà exploité ailleurs dans le BIB ou dans les futures générations de questions.

## Risque de doublon élevé

Caractéristiques typiques :

- univers très transversaux,
- franchises présentes dans plusieurs sections,
- informations extrêmement connues,
- angles évidents réutilisables partout.

## Risque de doublon faible

Caractéristiques typiques :

- angles spécialisés,
- informations très spécifiques,
- univers peu connectés aux autres sections.

## Comportement IA attendu

- éviter la répétition des mêmes informations sous plusieurs formulations,
- répartir les angles entre sections proches,
- réserver certains angles à une seule section si nécessaire,
- privilégier la variété documentaire globale.

## Important

- un item très connu possède souvent un risque de doublon élevé,
- un fort risque de doublon ne justifie pas automatiquement une suppression,
- la priorité reste la cohérence documentaire globale.

---

# SATURATION DOCUMENTAIRE

## Définition

État d’un thème, d’une section ou d’un univers dont les angles réellement exploitables commencent à s’épuiser malgré l’augmentation du volume documentaire.

## Signes fréquents

- répétition croissante des mécanismes de questions,
- angles très proches les uns des autres,
- ajout d’items à faible valeur documentaire,
- augmentation artificielle du volume,
- baisse de variété réelle.

## Effets négatifs possibles

- fatigue documentaire,
- redondance excessive,
- baisse de qualité quiz,
- enrichissement artificiel des sections,
- rigidification du BIB.

## Important

- une section volumineuse n’est pas forcément saturée,
- une petite section peut saturer très rapidement,
- la saturation dépend surtout de la variété réelle des angles disponibles.

## Comportement IA attendu

- détecter les enrichissements artificiels,
- éviter d’ajouter des items uniquement pour atteindre un quota,
- privilégier la qualité documentaire à l’augmentation mécanique du volume,
- signaler les sections proches de l’épuisement documentaire.

---

# SECTION IMPORTANTE

## Définition

Section disposant d’un bon potentiel documentaire et d’une bonne exploitabilité quiz, sans être forcément centrale dans l’identité globale du thème.

## Caractéristiques typiques

- bonne notoriété,
- potentiel de génération correct à élevé,
- bonne accessibilité généraliste,
- diversité documentaire suffisante,
- rôle significatif dans l’équilibre du BIB.

## Important

- une section importante peut parfois rivaliser avec une section majeure selon le thème,
- son classement dépend du contexte documentaire global,
- le volume reste indicatif et non absolu.

---

# SECTION MAJEURE

## Définition

Section considérée comme centrale dans le thème traité. Elle possède généralement une forte notoriété, une forte densité documentaire et un potentiel élevé de génération de questions.

## Caractéristiques typiques

- forte exploitabilité quiz,
- nombreux angles possibles,
- bonne accessibilité grand public,
- forte stabilité culturelle,
- volume généralement élevé,
- faible risque d’épuisement rapide.

## Important

- une section majeure n’est pas définie uniquement par son volume,
- le volume reste un indicateur et non une obligation,
- une section peut être majeure même avec un volume réduit si son importance documentaire le justifie.

---

# SECTION MOYENNE

## Définition

Section disposant d’un intérêt documentaire réel mais d’un potentiel plus limité en notoriété, densité documentaire ou exploitabilité quiz.

## Caractéristiques typiques

- volume modéré,
- potentiel de génération correct mais limité,
- angles exploitables moins nombreux,
- utilité surtout complémentaire dans l’équilibre global.

## Important

- une section moyenne reste pleinement légitime dans un BIB cohérent,
- son rôle principal est d’enrichir la diversité documentaire sans surcharger le système,
- une section moyenne peut exceptionnellement être renforcée si le thème le justifie.

---

# SECTION SECONDAIRE

## Définition

Section principalement destinée à enrichir la variété documentaire du BIB. Son potentiel de génération, sa densité documentaire ou sa notoriété sont généralement plus limités.

## Caractéristiques typiques

- volume généralement faible,
- angles souvent moins nombreux,
- risque d’épuisement plus rapide,
- intérêt documentaire complémentaire,
- utilité principalement liée à la diversité du quiz.

## Important

- une section secondaire peut exceptionnellement dépasser sa fourchette recommandée si :
  - la cohérence culturelle le justifie,
  - le potentiel quiz est supérieur à l’estimation initiale,
  - ou le thème possède une richesse documentaire inattendue.

---

# STABILITÉ CULTURELLE

## Définition

Capacité d’un thème, d’un item ou d’une référence à conserver sa reconnaissance et sa pertinence dans le temps.

## Une forte stabilité culturelle implique généralement

- reconnaissance durable,
- présence transgénérationnelle,
- réutilisation fréquente dans la culture populaire,
- faible dépendance à l’actualité immédiate,
- forte mémorisation collective.

## Une faible stabilité culturelle implique généralement

- dépendance aux tendances récentes,
- visibilité temporaire,
- risque d’oubli rapide,
- notoriété fragile ou contextuelle.

## Important

- une référence récente peut malgré tout posséder une forte stabilité potentielle,
- la stabilité culturelle ne dépend pas uniquement de l’ancienneté,
- certaines références très populaires peuvent rester instables à long terme.

## Comportement IA attendu

- privilégier les références durablement identifiables pour les sections structurantes,
- éviter de surcharger les sections majeures avec des références à stabilité faible,
- accepter davantage d’instabilité dans les sections secondaires ou expérimentales.

---

# SUR-REPRÉSENTATION DOCUMENTAIRE

## Définition

Présence excessive d’un thème, d’un univers, d’une franchise ou d’un type de contenu au point de réduire la variété documentaire globale du BIB.

## Signes fréquents

- trop forte concentration autour des mêmes licences,
- domination d’un univers culturel,
- répétition importante des mêmes références,
- déséquilibre durable entre sections.

## Effets négatifs possibles

- baisse de diversité,
- augmentation du risque de doublon,
- impression de répétition pour le joueur,
- affaiblissement des sections complémentaires.

## Important

- une forte présence n’est pas automatiquement problématique,
- certaines références structurantes peuvent rester volontairement très présentes,
- la priorité reste l’équilibre documentaire global et la variété réelle des angles.

## Comportement IA attendu

- surveiller les concentrations excessives,
- préserver la diversité documentaire globale,
- éviter l’expansion artificielle des univers déjà dominants,
- distinguer présence forte légitime et saturation documentaire.

---

# ZONE D’ÉQUILIBRE DOCUMENTAIRE

## Définition

Fourchette indicative servant de repère pour évaluer si un volume documentaire reste cohérent avec le type de section, le thème et le profil choisi.

## Important

- une zone d’équilibre n’est pas un quota fixe,
- les dépassements cohérents sont autorisés,
- les écarts doivent être analysés contextuellement.

## Comportement IA attendu

- utiliser les zones comme outil d’analyse,
- éviter les ajustements automatiques,
- signaler uniquement les écarts réellement problématiques.

