# MASTER_PIPELINE

## OBJECTIF

Definir l orchestration complete de la FACTORY quiz.

Pipeline industriel :
1. Documentation
2. Structuration
3. Pools
4. Generation
5. QA
6. Assemblage
7. Export

---

## PHASE 1 - COLLECTE DOCUMENTAIRE

Entrees :
- BIB_CDM
- Sources documentaires
- Validations humaines

Sorties :
- BIPREGEN
- ANGIPREGEN
- STATS

### CHECKS

```txt
CHECK_SOURCE_QUALITY
CHECK_DUPLICATES_RAW
CHECK_COVERAGE
```

---

## PHASE 2 - STRUCTURATION POOLS

Entrees :
- ANGIPREGEN
- POOLS_CDM

Sorties :
- 20 POOLS valides
- RESERVED_ITEM
- FORBIDDEN_POOL
- ANGLE_ASSIGNMENT

### CHECKS

```txt
CHECK_POOL_COLLISIONS
CHECK_ANGLE_ASSIGNMENT
CHECK_RESERVATIONS
```

---

## PHASE 3 - GENERATION IA

Entrees :
- POOLS
- IF-SF
- IF-ROT
- QV
- BIPREGEN
- QA_RULES

Sorties :
- Questions
- Reponses
- Tags
- Metadonnees

### CHECKS

```txt
CHECK_FORMAT
CHECK_DISTRACTORS
CHECK_DIFFICULTY
```

---

## PHASE 4 - QA

Entrees :
- Questions generees
- QA_RULES

Sorties :
- QA_STATUS
- FLAGS
- REJECTS

### CHECKS

```txt
CHECK_WEAK_QUESTIONS
CHECK_REPEAT_DENSITY
CHECK_IA_STYLE
```

---

## PHASE 5 - ASSEMBLAGE QUIZ

Entrees :
- Questions validees
- QUIZ_ASSEMBLY_RULES

Sorties :
- Quiz final
- Ordre de jeu
- Courbe difficulte

### CHECKS

```txt
CHECK_THEME_BALANCE
CHECK_DIFFICULTY_CURVE
CHECK_FLOW
```

---

## PHASE 6 - EXPORT

Entrees :
- Quiz final
- Metadonnees

Sorties :
- JSON
- CSV
- API
- App

### CHECKS

```txt
CHECK_EXPORT_FORMAT
CHECK_MISSING_FIELDS
CHECK_CORRUPTION
```

---

## BLOCAGES OBLIGATOIRES

L export final doit etre bloque si :
- QA_STATUS=FAIL
- CHECK_POOL_COLLISIONS fail
- CHECK_FACTORY_FORMAT fail
- CHECK_DUPLICATES fail

---

## PHILOSOPHIE

La FACTORY devient un :
- systeme industriel
- auditable
- resilient
- modulaire
- automatisable
