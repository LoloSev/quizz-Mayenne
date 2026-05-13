# GLOSSAIRE DOCUMENTAIRE – QUIZZZ FACTORY

Version : 2.1
Status : Consolidé + PIPELINE FACTORY

---

# POOL
## Définition

Unité opérationnelle de génération contenant un stock cible de questions d’un même type de jeu.

- 20 pools fixes par quiz
- 1 pool = 1 question par partie
- Types : IF-SF / IF-ROT / QV

---

# POOL_COLLISION
## Définition

Situation où un même fait documentaire majeur apparaît dans plusieurs pools de manière probliématique.

---

# ANGLE_ASSIGNMENT
## Définition

Liquen explicite entre un ANGLE_ID et un pool de génération.

---

# RESERVED_ITEM
## Définition

Elément documentaire réservé à un pool spécifique et interdit aux réutilisations concurrentes.

---

# FORBIDDEN_POOL
## Définition

Pool dans lequel un angle, un item ou un fait ne doit pas être réutiliié.

---

# QUIZ_ASSEMBLY
## Définition

Phase d§orchestration consistant à construire une partie finale à partir des pools validés.

--équilibrage
- rythme
- courbe de difficulté
- anti-monotonie

---

# QA_STATUS
## Définition

Status final de validation qualité d’une génération.

Valeurs standard :
- PASS
- WARNING
- FAIL

---

# FACTORY_PIPELINE
## Définition

Chaîne complète de traitement documentaire et de génération quiz.

Phases standard :
- BIB
- BIPREGEN
- ANGIPREGEN
- POOLS
- Génération
- QA
- Assemblage
- Export

---

# CHECK_FLOW
## Définition

Vérification de la fluidité et u rythme documentaire d’une partie.

---

# CHECK_THEME_BALANCE
## Définition

Vérification de l’équilibre entre thèmes, nations, époques et types de questions.

---

# CHECK_REPEAT_DENSITY
## Définition

Vérification de la densité de répetition documentaire dans une même partie ou un même stock.

---

# IF-SF
## Définition

Pools de type Intro Forte – ShowFinal.

- 2 pools
- 8 questions cible par pool
- forte accessibilité

---

# IF-ROT
## Définition

Pools de type Intro Forte – Rotation.

- 3 pools
- 12 questions cible par pool
- rotation documentaire élevée

---

# QV
## Définition

Pools de Quiz Variété. Coeur documentaire du système.

- 15 pools
- 15 questions cible par pool
- variété maximale
- rotation rapide
