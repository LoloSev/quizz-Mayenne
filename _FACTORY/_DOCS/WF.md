# WF — WORKFLOW CRÉATION QUIZ ET AVATARS

**Mis à jour :** 12/05/2026

---

## 🎮 Workflow : Créer un nouveau quiz

### Étape 1 — Préparation

- [ ] Définir le thème et le public cible
- [ ] Vérifier que le thème n'est pas trop proche d'un quiz existant
- [ ] Créer le dossier `quiz-[thème]/`
- [ ] Copier `_BASE/QUIZ_TEMPLATE.html` → renommer `QUIZ_[THÈME].html`
- [ ] Copier `_BASE/QUESTIONS_TEMPLATE.txt` → renommer `QUESTIONS_[THÈME].txt`

### Étape 2 — Production des questions (QUIZZZ FACTORY)

Suivre le workflow en 8 étapes (voir `DDT_WORKFLOW.md`) :

```
1. Base connaissances → demander à Claude de construire la matière
2. Génération brute → 300 questions sans distracteurs
3. Audit individuel → filtrer, corriger, reformuler
4. Classement difficulté → 40% facile / 40% intermédiaire / 20% difficile
5. Audit diversité → vérifier équilibre thématique
6. Distracteurs → générer pool par pool
7. Audit final → lisibilité mobile, ambiguïtés, collisions
8. Construction finale → assembler les 20 questions du quiz
```

### Étape 3 — Intégration technique

- [ ] Remplir `QUESTIONS_[THÈME].txt` avec les questions validées
- [ ] Créer `theme.css` (couleurs, identité visuelle du thème)
- [ ] Intégrer les questions dans `QUIZ_[THÈME].html`
- [ ] Ajouter Google Analytics dans le `<head>` (ID : `G-GZHLYBP79J`)
- [ ] Ajouter l'ambiance sonore `sounds/ambiance-[thème].mp3`

### Étape 4 — Avatar

Voir section **Workflow Avatars** ci-dessous.

### Étape 5 — Intégration au site

- [ ] Ajouter la carte du quiz dans `index.html`
- [ ] Vérifier tous les liens
- [ ] Tester sur mobile

### Étape 6 — Déploiement

```bash
netlify deploy --prod
# Compte : laurent-baudouin
```

### Étape 7 — Communication Instagram

- [ ] Post de lancement (carrousel)
- [ ] Story dédiée
- [ ] Appel aux retours utilisateurs

---

## 🎨 Workflow : Créer un avatar

### Matériau source

- Photo de base : `photo de laurent pour avatar.jpg` (à la racine du projet)
- Outil : **ChatGPT** (image generation)

### Prompt type pour ChatGPT

```
Crée un avatar stylisé de cet homme dans un style [ambiance du thème].
Il doit être reconnaissable (même visage), avec des accessoires évoquant [thème].
Ambiance : [couleurs dominantes, style graphique].
Format : carré, fond transparent ou simple, adapté à une utilisation web.
```

### Exemples de styles par thème

| Quiz | Style | Accessoires |
|---|---|---|
| Rock | Sombre, grunge, rock | Guitare, perfecto, bandana |
| Rap | Urban, streetwear | Casquette, microphone, chaîne |
| CDM | Sportif, dynamique | Maillot, ballon, trophée |
| Mayenne | Champêtre, chaud | Paysage mayennais en fond |
| Internet | Geek, néon, digital | Écran, mèmes, pixels |
| Séries | Cinématographique | Clap de cinéma, écran TV |

### Après génération

- [ ] Sauvegarder dans `quiz-[thème]/avatar-lolo-[thème].png`
- [ ] Copier dans `Campagne Insta [date]/` si campagne en cours
- [ ] Intégrer dans `QUIZ_[THÈME].html`

---

## 📣 Workflow : Campagne Instagram

### Pour un nouveau quiz

1. Générer l'avatar (voir ci-dessus)
2. Créer le dossier `Campagne Insta [date]/`
3. Préparer les visuels (avatar + texte accroche)
4. Rédiger la légende Instagram avec `#QuizzzdeLolo`
5. Publier et épingler en story

### Format des stories

- Image : avatar du quiz
- Texte : "Nouveau quiz [Thème] disponible ! 🎮"
- Lien : `quizzzz-de-lolo.netlify.app`
- Hashtag : `#QuizzzdeLolo`
