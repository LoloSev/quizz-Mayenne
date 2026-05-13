---
name: quizz-factory
description: Skill pour la production de quiz selon la méthode QUIZZZ FACTORY. Déclencher pour : générer des questions brutes (B2), ajouter des distracteurs (B3), auditer un pool (B5), ou toute étape du workflow A/B. S'applique à tous les quiz (Mayenne, Rock, Rap, CDM, Internet, Séries...).
---

# QUIZZZ FACTORY — Skill de production

## Règles comportementales (toujours actives)
- Fais strictement ce qui est demandé
- Pas de suggestions non sollicitées
- Pas de récapitulatifs après chaque action
- Réponses courtes, action immédiate
- Signaler toute erreur ou incohérence détectée

---

## Règles universelles (tous quiz)

- Questions courtes : 10 mots max, lisibles sur mobile
- Format QCM : 4 choix (A/B/C/D), 1 seule bonne réponse incontestable
- Jamais de formulation négative complexe
- Jamais de réponse dans l'énoncé
- Jamais de connaissance ultra-spécialisée
- Équilibre bonnes réponses : ≈25% par lettre sur le stock
- Travailler pool par pool, jamais globalement

---

## Étape B2 — Générer des questions brutes

**Prompt-type :**
```
Génère [N] questions brutes pour le pool [CODE_POOL] — [THÈME].
Format strict :
Q : [question]
R : [bonne réponse]
Thème : [thème]

Contraintes :
- 10 mots max par question
- Pas de distracteurs
- Une seule bonne réponse incontestable
- [Contraintes spécifiques au type de quiz — voir ci-dessous]
```

---

## Étape B3 — Ajouter les distracteurs

**Prompt-type :**
```
Ajoute 3 distracteurs à chaque question du pool [CODE_POOL].
Format strict :
Q : [question]
R : [bonne réponse]
A : / B : / C : / D : (mélanger la bonne réponse parmi les 4)

Règles distracteurs :
- Crédibles, même univers mental que la bonne réponse
- Même niveau de notoriété perçue
- Jamais de distracteur fictif sans signalement explicite
- [Contraintes spécifiques au type de quiz — voir ci-dessous]
```

---

## Étape B5 — Audit question par question

**Prompt-type :**
```
Présente les questions du pool [CODE_POOL] une par une pour audit.
Format obligatoire par question :

Question : [intitulé]
A. / B. / C. / D.
Bonne réponse : [lettre]. [réponse]
Difficulté : [1-5]
[Statut : incontournable] (uniquement si applicable)
Proposition : CONSERVER / MODIFIER / REJETER
Raison conservation : [si CONSERVER]
Raison modification : [si MODIFIER ou REJETER]
```

Attendre validation humaine avant de passer à la question suivante.

---

## Variantes par type de quiz

### Type : Entité géographique (ex: Mayenne)
- Questions strictement dans le territoire concerné
- Diversité géographique : max 5% par ville
- Pools distracteurs : DIST_COMMUNES, DIST_MONUMENTS, DIST_PERSONNALITES, DIST_GASTRONOMIE, DIST_RIVIERES
- Référence : `_LIGNES/_MAYENNE/` + `_STANDARDS/_ENTITE_GEO/`

### Type : Culture populaire (Rock, Rap, CDM, Internet, Séries)
- Max 2 questions par artiste/sujet/personnage
- Ne jamais répéter le mot-clé du thème dans les questions (implicite)
- Vérifier les liens croisés : une question ne doit jamais donner la réponse d'une autre
- Validation par blocs, attendre validation humaine avant de continuer

---

## Traçabilité (étape B5)

Toute décision doit être tracée dans le .xlsx :
- CONSERVER → remplir "Raison conservation"
- MODIFIER → remplir "Version originale", "Version modifiée", "Raison modification"
- REJETER → remplir "Raison modification"

Distracteurs fictifs : signalement obligatoire, validation humaine toujours.
