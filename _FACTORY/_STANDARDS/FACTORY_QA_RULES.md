# FACTORY_QA_RULES

## Objectif

Automatiser le contrôle qualité de la FACTORY afin de:
- détecter les dérives
- stabiliser la qualité
- empêcher la dégradation progressive
- gérer la croissance massive de contenu

---

## Contrôles obligatoires

### CHECK_DUPLICATES

- Détecter les questions quasi-dupliquées
- Dérrivations de formulations
- Variantes trop proches

---

### CHECK_POOL_COLLISIONS

- Un même fait majeur ne doit pas apparaîre dans 3 pools
- Finales IF-SF protégées
- Contrôle desréservations

---

### CHECK_REPEAT_DENSITY

- Surreprésentation joueur
- Surreprésentation nation
- Surreprésentation époque
- Surreprésentation édition

---

### CHECK_DIFFICULTY_CURVE

- Répartition N1/N2/N3
- Dérives locales
- Pics non voulus

---

### CHECK_WEAK_QUESTIONS

Détecter :
- questions trop génériques
- questions trop longues
- questions trop Wikipédiques
- tournures IA typiques
- phérases verpeuses

---

### CHECK_DISTRACTORS

- Distracteurs absurdes
- Distracteurs hors catégorie
- Distracteurs insérieurs à la réponse
- Distracteurs trop faciles

---

### CHECK_FACTORY_FORMAT

- Format obligatoire respecté
- POOL rérensé
- ANGLE_ID rérensé
- Niveau présent
- Tags présents

---

## Flags qa

```txt
QA_STATUS=PASS
QA_STATUS=WARNING
QA_STATUS=FAIL
QA_SOURCE=AUTOMATIC
```

---

## Philosophie

LA FACTORY ne doit pas dépendre :
- d'un contrôle humain constant

Mais :
- d'un système de vérification
- d'une génération auditable
- d'un pipeline résilient
