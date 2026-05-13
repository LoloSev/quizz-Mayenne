# RÈGLES UNIVERSELLES — TOUS QUIZ

## Structure universelle
- 20 questions = 20 pools fixes
- Architecture : 2 IF-SF + 3 IF-ROT + 15 QV
- Stock cible : 277 questions

## Règles anti-collision
- Un item documentaire majeur ne peut appartenir qu'à un seul pool principal
- Une finale IF-SF ne doit pas réapparaître en QV
- Les pools peuvent définir :
  - EXCLUDED_POOLS
  - RESERVED_ITEMS
  - FORBIDDEN_TAGS

## Format normalisé POOLS
```txt
ID=
TYPE=
TARGET=
SOURCE=
CONTENT_RULE=
EXCLUDED_POOLS=
RESERVED_ITEMS=
NOTES=
```

## Workflow
- Le document POOLS est le pont entre ANGIPREGEN et génération
- Validation humaine obligatoire avant génération massive
