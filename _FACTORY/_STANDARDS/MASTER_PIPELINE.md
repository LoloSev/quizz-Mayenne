# MASTER_PIPELINE

## Objectif

Define the complete FACTORY pipeline.

Pipeline :
1. Documentation
2. Structuration
3. Generation
4. QA
5. Assembly
6. Export

---

## Phase 1 – Documentation

- BIB_CDM
- ANGIPREGEN
- BIPREGEN

## Checks

```txt
CHECK_SOURCE_QUALITY
CHECK_DUPLICATES_RAW
```

---

## Phase 2 – Pools

- POOLS_CDM
- Reservations
- Exclusions

## Checks

```txt
CHECK_POOL_COLLISIONS
CHECK_ANGLE_ASSIGNMENT
```

---

## Phase 3 – Generation I

- Questions
- Reponses
- Tags

## Checks

```txt
CHECK_FORMAT
CHECK_DIFFICULTY
```

---

## Phase 4 – QA

- QA_STATUS
- FLAGS

---

## Phase 5 – Assembly

- Quiz final
- Difficulty curve

---

## Phase 6 – Export

- JSON
- CSV
- API

---

## Philosophy

- Industrial
- Auditable
- Automatable
