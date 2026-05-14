# B5 — MODE OPÉRATOIRE AUDIT

**Rôle :** 👤 Laurent + 🤖 IA
**Référence :** MASTER_ARCHITECTURE.md — Étape B5

---

## Principe

- Une question à la fois
- Validation humaine obligatoire avant passage à la suivante
- Mise à jour CSV/xlsx immédiate à chaque décision

---

## Format de présentation (obligatoire)

```
Question :
[intitulé]

A. / B. / C. / D.

Bonne réponse : [lettre]. [réponse]
Difficulté : N1 / N2 / N3
[Statut : incontournable] (si applicable)

Proposition : CONSERVER / MODIFIER / REJETER / DÉPLACER
Raison conservation : [si CONSERVER]
Raison modification : [si MODIFIER ou REJETER]
Pool cible : [si DÉPLACER]
```

---

## Les 4 décisions

### 1. CONSERVER
- Remplir "Raison conservation" dans le CSV
- Passer à la question suivante

### 2. MODIFIER
- Indiquer ce qui change (formulation / distracteur / difficulté)
- Remplir "Version originale" + "Version modifiée" + "Type modification" + "Raison modification"
- Valider la nouvelle version avant de passer à la suivante

### 3. REJETER
- Remplir "Raison modification" (raison du rejet)
- La ligne reste dans le CSV avec statut REJETÉ

### 4. DÉPLACER
- Préciser le pool cible
- Inscrire immédiatement la question dans le CSV du pool cible
  → Statut audit : `DÉPLACÉ (origine [pool source])`
  → Pools secondaires compatibles : pool d'origine
- Remplir "Raison modification" dans le pool source

---

## Critères d'évaluation

- Clarté de la formulation
- Lisibilité mobile (10 mots max)
- Absence d'ambiguïté
- Qualité et cohérence des distracteurs
- Difficulté adaptée au pool
- Cohérence gameplay (position dans le quiz)
- Diversité géographique/thématique
- Pas de collision avec d'autres questions du pool

---

## Règles distracteurs

- Crédibles, même univers mental que la bonne réponse
- Même périmètre cohérent (géographique, temporel, thématique)
- Distracteur fictif → signalement obligatoire + validation humaine
- Distracteur trop éloigné → remplacer

---

## Fichier lisible

Créer un fichier `[POOL]_LISIBLE.md` en parallèle du CSV pour relecture humaine rapide.

---

## Workflow résumé

```
Question présentée
    ↓
Décision humaine (1/2/3/4)
    ↓
Mise à jour CSV immédiate
    ↓
Question suivante
```
