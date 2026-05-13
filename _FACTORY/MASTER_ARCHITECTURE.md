⚠️ RÈGLE IA — COMPORTEMENT OBLIGATOIRE
• Fais strictement ce qui est demandé
• Pas de suggestions non sollicitées
• Pas de récapitulatifs après chaque action
• Pas de questions si la tâche est claire
• Réponses courtes, action immédiate
• Signaler toute erreur détectée
• Signaler les incohérences entre fichiers du projet
• Signaler quand une tâche risque de dépasser les capacités techniques de l'IA
• Proposer des pistes pour économiser des tokens et optimiser les processus

---

# QUIZZZ FACTORY — MASTER ARCHITECTURE

**Version :** 3.3
**Mis à jour :** 13/05/2026 — dépoussiérage + stratégie cobayes
**Statut :** Document central de référence — tous les autres pointent vers celui-ci

---

# CONTEXTE DU PROJET

**Les Quizzzz de Lolo** est un site de quiz de culture générale thématique, court, mobile-friendly et rejouable. Chaque partie dure 90 secondes pour 20 questions, avec un mélange aléatoire à chaque session.

**Auteur :** Laurent (Lolo)
**URL live :** `quizzzz-de-lolo.netlify.app`
**Hashtag :** `#QuizzzdeLolo`
**Public cible :** 12–20 ans, anciens élèves, passionnés de culture pop. Usage mobile, partage Instagram, défis entre amis.

| Paramètre | Valeur |
|---|---|
| Durée d'une partie | 90 secondes |
| Questions par partie | 20 |
| Incontournables fixes | 5 |
| Questions aléatoires | 15 |
| Stock cible par quiz | 277 questions |
| Format | QCM 4 choix (A/B/C/D), 1 bonne réponse |

---

# CATALOGUE DES QUIZ

| Quiz | Thème |
|---|---|
| 🎸 Rock | Légendes, albums, riffs, mouvements |
| 🎤 Rap | Rap français + game international |
| ⚽ CDM | Histoire de la Coupe du Monde |
| 🏞️ Mayenne | Histoire, géo, traditions du 53 |
| 💻 Internet | Memes, plateformes, culture web |
| 📺 Séries | Séries TV françaises et internationales |
| 🎬 Cinéma | Films, acteurs, réalisateurs |

Pistes futures : voir `_DOCS/BAI.md`

---

# PHILOSOPHIE GÉNÉRALE

L'objectif n'est pas de tout connaître, mais de **créer un système capable de produire des quiz cohérents sur n'importe quel thème**.

Le rôle humain : architecte éditorial, valideur final, superviseur qualité. Pas opérateur de saisie.

Tous les documents de la FACTORY sont conçus pour être **IA-compatibles** : formulations précises, concepts définis dans le glossaire, règles non ambiguës. L'objectif à terme est que chaque MDE puisse servir de base à un skill autonome.

---

# STRATÉGIE COBAYES

Chaque workflow est construit et validé sur un thème cobaye avant d'être généralisé. Les règles extraites alimentent à terme le glossaire documentaire.

| Cobaye | Workflow | Statut |
|---|---|---|
| 🏞️ Mayenne | Audit questions + construction xlsx (MDE B5) | 🔄 En cours |
| ⚽ CDM | Traitement BIB → BIPREGEN + ANGIPREGEN (MDE A3) | ✅ Référence |
| 🎬 Cinéma | Approvisionnement BIB (MDE A2) | 🔄 En cours |

---

# RÈGLES D'ÉQUILIBRAGE DOCUMENTAIRE

- Les quotas servent de guides d'équilibrage et non de contraintes rigides.
- La cohérence culturelle et documentaire prime sur les objectifs chiffrés.
- Des déséquilibres volontaires peuvent être conservés s'ils sont pertinents.
- Les répartitions N1 / N2 / N3 dépendent du profil documentaire choisi.
- Profil documentaire par défaut : CLASSIQUE.
- D'autres profils peuvent être utilisés : JEUNE PUBLIC, EXPERT, PERSONNALISÉ.
- Les fourchettes de niveaux restent indicatives et adaptables selon le thème et le public ciblé.

---

# NOMENCLATURE DES DOCUMENTS

## Documents de la chaîne de production

| Code | Nom complet | Rôle |
|---|---|---|
| **BIB** | Base Items Brute | Document source constitué manuellement. Ensemble des items organisés en sections thématiques, avec indicateurs de difficulté bruts. **Non modifié après archivage.** |
| **BIPREGEN** | Base Items Prégénération | Version traitée et structurée de la BIB. Items codés `[THEME]-[CAT]-[N°]-[NIV]`, ligne unique, niveaux harmonisés, statistiques et index inclus. **Source de données propre pour la génération.** |
| **ANGIPREGEN** | Angles Items Prégénération | Définit pour chaque item : les angles interrogeables, les exclusions inter-items (⚠️) et le quota de questions à générer. **Guide opérationnel de la génération.** |
| **PROCESS_BIB** | Process Traitement BIB | Trace précise de toutes les transformations BIB → BIPREGEN + ANGIPREGEN. État initial, interventions, reclassements, décisions. **Traçabilité AVANT/APRÈS.** |
| **POOLS** | Pools Prégénération | Définit les 20 pools du quiz : identifiant, type (IF-SF / IF-ROT / QV), thème éditorial, stock cible, items ANGIPREGEN associés. **Chaînon entre ANGIPREGEN et génération.** |

## Convention de nommage fichier

```
[CODE]_[THEME].[ext]
```

Exemples : `BIB_CDM.txt` · `BIPREGEN_CDM.txt` · `ANGIPREGEN_CDM.txt` · `PROCESS_BIB_CDM.md` · `POOLS_CDM.txt`

---

# ARBORESCENCE — QUIZZZ FACTORY

```
_FACTORY/
│
├── MASTER_ARCHITECTURE.md          ← ce document
├── START.txt                       ← contexte projet + briefing IA
│
├── _DOCS/                          ← docs contextuels projet
│   ├── DDT.md                      ← état du site, technique, déploiement
│   ├── DDT_WORKFLOW.md             ← règles de travail avec l'IA
│   ├── BAI.md                      ← boîte à idées
│   └── WF.md                       ← workflow quiz + avatars
│
├── _BUREAU_METHODES/               ← modes opératoires
│   ├── MDE_A2_approvisionnement.md ← construire la BIB              (⏳ à créer)
│   ├── MDE_A3_traitement.md        ← BIB → BIPREGEN + ANGIPREGEN    ✅
│   ├── MDE_A4_tableur_pools.md     ← créer le tableur xlsx           (⏳ à créer)
│   ├── MDE_B2_generation.md        ← générer les questions brutes    (⏳ à créer)
│   ├── MDE_B3_distracteurs.md      ← ajouter les distracteurs        (⏳ à créer)
│   ├── MDE_B4_implantation.md      ← implanter dans le xlsx          (⏳ à créer)
│   ├── MDE_B5_audit.md             ← audit humain + traçabilité      ✅
│   └── MDE_B6_regles.md            ← extraire les règles généralisables (⏳ à créer)
│
├── _STANDARDS/                     ← règles et références transversales
│   ├── REGLES_UNIVERSELLES.md      ← règles applicables à tous les quiz ✅
│   ├── glossaire_documentaire_factory.md ← couche d'interprétation IA ✅
│   └── REGLES_TYPE_[X].md          ← règles par type de quiz         (⏳ à créer)
│
└── _LIGNES/                        ← une ligne de production par quiz
    │
    ├── _TEMPLATE/                  ← gabarit à copier pour tout nouveau quiz
    │   ├── 01_APPRO/               ← BIB_[THEME].txt
    │   ├── 02_TRAITEMENT/          ← BIPREGEN + ANGIPREGEN + PROCESS_BIB + POOLS
    │   ├── 03_GENERATION/          ← questions brutes pool par pool
    │   ├── 04_AUDIT/               ← audit + modifications tracées
    │   ├── 05_REGLES/              ← règles extraites (spécifiques au thème)
    │   └── 06_PRODUIT_FINI/        ← xlsx + JSON final
    │
    ├── _MAYENNE/                   ← cobaye B5 (audit + xlsx)
    │   ├── 01_APPRO/               ✅ BIB Mayenne
    │   ├── 03_GENERATION/          ✅ 300 questions brutes
    │   ├── 05_REGLES/              (vide)
    │   └── 06_PRODUITS_FINIS/      ✅ quiz_mayenne_integral.xlsx
    │
    ├── _CDM/                       ← cobaye A3 (traitement BIB)
    │   ├── 01_APPRO/               ✅ BIB_CDM.txt
    │   └── 02_TRAITEMENT/          ✅ BIPREGEN + ANGIPREGEN + PROCESS_BIB
    │
    ├── _CINEMA/                    ← cobaye A2 (approvisionnement BIB)
    │   ├── 01_APPRO/               ✅ BIB_CINEMA x3 + LOG + STATS
    │   ├── 02_TRAITEMENT/          (vide)
    │   ├── 03_GENERATION/          (vide)
    │   ├── 04_AUDIT/               (vide)
    │   ├── 05_REGLES/              (vide)
    │   └── 06_PRODUIT_FINI/        (vide)
    │
    ├── _ROCK/                      (⏳ à créer)
    ├── _RAP/                       (⏳ à créer)
    ├── _INTERNET/                  (⏳ à créer)
    └── _SERIES/                    (⏳ à créer)
```

---

# ARCHITECTURE DES QUIZ

Chaque quiz contient 20 questions issues de 20 pools.

## Bloc 1 — Incontournables semi-fixes (IF-SF)
2 pools × 8 questions — identité forte, rotation très lente

## Bloc 2 — Incontournables rotatifs (IF-ROT)
3 pools × 12 questions — rotation lente, onboarding fluide

## Bloc 3 — Questions variables (QV)
15 pools × 15 questions — forte variété, rotation rapide

**Total : 20 pools = 20 questions par partie. Le moteur pioche UNE question par pool.**

---

# DEUX WORKFLOWS

## Workflow A — Élaboration (architecture du quiz)

| Étape | Qui | Action | MDE |
|---|---|---|---|
| A1 | 👤 Laurent | Choix du thème | — |
| A2 | 🤖 → ✅ | Construire la BIB | `MDE_A2_approvisionnement.md` |
| A3 | 🤖 → ✅ | Traiter BIB → BIPREGEN + ANGIPREGEN | `MDE_A3_traitement.md` |
| A4 | 🤖 → ✅ | Définir les 20 pools → créer POOLS_[THEME].txt | `MDE_A4_tableur_pools.md` |
| A5 | 🤖 → ✅ | Créer le tableur xlsx depuis POOLS | `MDE_A4_tableur_pools.md` |

## Workflow B — Production (génération des questions)

| Étape | Qui | Action | MDE |
|---|---|---|---|
| B2 | 🤖 → ✅ | Générer les questions brutes (pool par pool) | `MDE_B2_generation.md` |
| B3 | 🤖 → ✅ | Ajouter les distracteurs | `MDE_B3_distracteurs.md` |
| B4 | 🤖 | Implanter dans le xlsx | `MDE_B4_implantation.md` |
| B5 | 👤 + 🤖 | Audit humain + traçabilité | `MDE_B5_audit.md` |
| B6 | 🤖 → ✅ | Extraire les règles généralisables | `MDE_B6_regles.md` |

---

# RÈGLES CRITIQUES

- Pool par pool, étape par étape — **jamais globalement**
- Validation humaine obligatoire avant chaque étape suivante
- Distracteurs fictifs → validation humaine **toujours**
- Traçabilité AVANT/APRÈS/RAISON dans le xlsx
- BIB original jamais modifié après archivage
- Les règles extraites des cobayes alimentent le glossaire documentaire

---

# STRATÉGIE TECHNIQUE

Rester le plus longtemps possible sur : **Excel / JSON / GitHub / Netlify**

Architecture cible : `Excel → Export JSON → Site`

---

# DOCUMENTS LIÉS

## Contexte projet

| Document | Rôle |
|---|---|
| `START.txt` | Contexte projet, briefing IA, qui fait quoi |
| `_DOCS/DDT.md` | État du site, technique, déploiement |
| `_DOCS/DDT_WORKFLOW.md` | Règles de travail avec l'IA |
| `_DOCS/BAI.md` | Boîte à idées — pistes futures |
| `_DOCS/WF.md` | Workflow quiz + avatars (Claude + ChatGPT) |



## Méthodes de production (Bureau des Méthodes)

| Document | Rôle | Workflow |
|---|---|---|
| `_BUREAU_METHODES/MDE_A3_traitement.md` | Traitement BIB → BIPREGEN + ANGIPREGEN | A3 |
| `_BUREAU_METHODES/MDE_B5_audit.md` | Audit humain des questions générées + traçabilité | B5 |

## Standards et règles

| Document | Rôle |
|---|---|
| `_STANDARDS/REGLES_UNIVERSELLES.md` | Règles de génération applicables à tous les quiz |
| `_STANDARDS/glossaire_documentaire_factory.md` | Définitions des concepts documentaires (BIB, angles, niveaux, profils…) — couche d'interprétation IA |
