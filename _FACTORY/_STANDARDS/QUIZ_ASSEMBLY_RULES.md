# QUIZ ASSEMBLY RULES

## Objectif

Garantir qu'une partie finale de 20 questions soit :
- variée
- fluide
- équilibrée
- rejouable
- sans collisions documentaires

---

## Structure fixe

Chaque quiz final contient :

- 2 IF-SF
- 3 IF-ROT
- 15 QV

Ordre recommandé :

```txt
IF-SF
QV
QV
IF-ROT
QV
QV
QV
IF-SF
QV
QV
IF-ROT
QV
QV
QV
QV
IF-ROT
QV
QV
QV
QV
```

---

## Règles d'équilibrage

### Joueurs

- Maximum 2 occurrences du même joueur majeur par partie
- Aucun joueur dans 2 questions consécutives
- Une question IF-SF sur un joueur interdit un QV immédiat sur le même joueur

---

### Finales / matchs

- Pas de deux finales consécutives
- Maximum 3 questions liées à une même édition CDM
- Une finale IF-SF interdit sa réutilisation dans les QV

---

### Nations

- Éviter plus de 3 questions d'affilée sur une même nation
- Répartir les grandes nations sur toute la partie

---

### Difficulté

Distribution cible :

| Niveau | Volume |
|---|---|
| N1 | 40% |
| N2 | 40% |
| N3 | 20% |

Règles :
- jamais plus de 2 N3 consécutifs
- début de partie accessible
- montée progressive difficulté

---

## Règles anti-monotonie

Interdits :
- 3 questions biographies d'àffilée
- 3 scores/matchs d'àffilée
- 3 records d'àffilée
- répétition immédiate de formulation

Alterner :
- joueurs
- matchs
- records
- anecdotes
- nations
- époques

---

## Validation finale pipeline

Avant export final :

```txt
CHECK_DUPLICATES
CHECK_PLAYER_DENSITY
CHECK_DIFFICULTY_CURVE
CHECK_THEME_BALANCE
CHECK_POOL_COLLISIONS
CHECK_REPEAT_EDITIONS
```

---

## Philosophie

Une bonne partie ne dépend pas seulement :
- de bonnes questions

Mais surtout :
- d'un bon rythme
- d'une bonne alternance
- d'une variété documentaire maîtrisée
