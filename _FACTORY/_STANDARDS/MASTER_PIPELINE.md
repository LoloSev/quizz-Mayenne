# MASTER_PIPELINE

## Objectif

Définir l'orchestration complète de la FACTORY quiz.

Pipeline industriel :
1. Documentation
2. Structuration
3. Génération
4. QA
5. Assemblage
6. Export

---

## Phase 1 — Collecte documentaire

Entrées :
- BIB_CDM
- Sources documentaires
- Validations humaines

Sorties :
- BIPREGEN
- ANGIPREGEN
- STATS

## Checks

```txt
CHECK_SOURCE_QUALITY
CHECK_DUPLICATES_RAW
CHECK_COVERAGE
```

---

## Phase 2 — Structuration POOLS

Entrées :
- ANGIPREGEN
- POOLS_CDM

Sorties :
- Pools validés
- Réservations
- Exclusions

## Checks

```txt
CHECK_POOL_COLLISIONS
CHECK_ANGLE_ASSIGNMENT
CHECK_RESERVATIONS
```

---

## Phase 3 — G�nération IA

Entrées :
- POOLS
- BIPREGEN
- QA_RULES

Sorties :
- Questions
- Réponses
- Tags
- Métadonnées

## Checks

```txt
CHECK_FORMAT
CHECK_DISTRACTORS
CHECK_DIFFICULTY
```

---

## Phase 4 — QA

Entrées :
- Questions générées
- QA_RULES

Sorties :
- QA_STATUS
- FLAGS
- REJECTS

## Checks

```txt
CHECK_WEAK_QUESTIONS
CHECK_REPEAT_DENSITY
CHECK_IA_STYLE
```

---

## Phase 5 — Assemblage Quiz

Entrées :
- Questions validées
- QUIZ_ASSEMBLY_RULES

Sorties :
- Quiz final
- Ordre de jeu
- Courbe difficulté

## Checks

```txt
CHECK_THEME_BALANCE
CHECK_DIFFICULTY_CURVE
CHECK_FLOW
```

---

## Phase 6 — Export

Entrées :
- Quiz final
- Métadonnées

Sorties :
- JSON
- CSV
- API
- App

## Checks

```txt
CHECK_EXPORT_FORMAT
CHECK_MISSING_FIELDS
CHECK_CORRUPTION
```

---

## Blockages obligatoires

L'export final doit être bloqué si :
- QA_STATUS=FAIL
- CHECK_POOL_COLLISIONS fail
- CHECK_FACTORY_FORMAT fail
- CHECK_DUPLICATES fail

---

## Philosophie

La FACTORY devient un :
- système industriel
- auditable
- résilient
- modulaire
- automatisable
