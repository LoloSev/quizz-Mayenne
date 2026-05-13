# MDE A3 — TRAITEMENT BASE ITEMS
# BIB → BIPREGEN + ANGIPREGEN
## Applicable à tout thème : CDM, Rock, Rap, Séries, Internet, Géographie...

Version : 2.0
Date de mise à jour : 13/05/2026
Basée sur : Traitement réel de BIB_CDM.txt (111 items, 300 questions)

---

# PRINCIPE GÉNÉRAL

Avant de générer des questions de quiz, la BIB doit être traitée et structurée.

Ce traitement est :
- systématique
- reproductible
- adaptable selon les thèmes
- piloté par équilibrage documentaire souple

Le traitement produit :

1. BIPREGEN_[THEME].txt — version traitée et codée
2. ANGIPREGEN_[THEME].txt — carte des angles interrogeables par item
3. PROCESS_BIB_[THEME].md — documentation du traitement (traçabilité)

L’objectif final est de disposer d’un volume cohérent de questions réparties selon un profil documentaire choisi.

---

# PROFILS DOCUMENTAIRES

Avant tout calibrage des niveaux, l’IA doit demander quel profil documentaire est souhaité.

## CLASSIQUE (profil par défaut)
- N1 : 35–45%
- N2 : 35–45%
- N3 : 15–25%

## JEUNE PUBLIC
- N1 : 55–70%
- N2 : 20–35%
- N3 : 5–15%

## EXPERT
- N1 : 15–30%
- N2 : 35–45%
- N3 : 30–50%

## PERSONNALISÉ
Les proportions peuvent être adaptées selon :
- le thème
- le public ciblé
- la densité documentaire
- le niveau de difficulté recherché

Les proportions servent de guides d’équilibrage et non de contraintes rigides.

---

# ÉTAPE 0 — ARCHIVAGE DE L'ORIGINAL

Action :
Dupliquer le fichier brut sous le nom BIB_[THEME].txt.

Règle :
Ce fichier n'est jamais modifié.
Il sert de référence AVANT pour toute vérification ultérieure.

---

# ÉTAPE 1 — AUDIT DU FICHIER BRUT

Avant toute modification, analyser et documenter l'état initial.

## 1.1 Inventaire des sections
- lister les sections thématiques
- compter le nombre d'items par section

## 1.2 Identification des problèmes

| Problème fréquent | Action à prévoir |
|---|---|
| Indicateurs de difficulté non standard | Harmonisation |
| Items sur plusieurs lignes | Fusion sur une ligne |
| Absence d'identifiant unique | Ajout d'un code |
| Déséquilibres N1/N2/N3 | Rééquilibrage documentaire |
| Risques de doublons entre sections | Cartographie des angles |

## 1.3 Comptage initial
- nombre total d'items
- répartition N1/N2/N3
- écarts éventuels avec le profil documentaire choisi

---

# ÉTAPE 2 — HARMONISATION DES NIVEAUX

Quel que soit le système initial, convertir vers :
- Niveau 1
- Niveau 2
- Niveau 3

Points d'attention :
- certains symboles peuvent avoir d'autres significations
- vérifier section par section avant automatisation

---

# ÉTAPE 3 — MISE EN LIGNE UNIQUE

Chaque item doit tenir sur une seule ligne.

Détection :
une ligne est une continuation si elle ne commence ni par :
- un numéro de section
- un titre de section

Types possibles :
- Type A : titre + description
- Type B : titre + sous-données multiples

---

# ÉTAPE 4 — SYSTÈME DE CODAGE

Format :
[THEME]-[CAT]-[N°]-[NIV]

Règles :
- chaque code doit être unique
- le niveau du code doit correspondre au niveau réel de l'item
- le code remplace la numérotation d'origine

---

# ÉTAPE 5 — TABLEAU DE STATISTIQUES

Le tableau statistiques sert :
- d’outil de pilotage documentaire
- d’aide au rééquilibrage
- de contrôle de cohérence global

Il doit utiliser :
- des zones d’équilibre
- des fourchettes indicatives
- et non des quotas rigides

Le tableau peut contenir :
- total items
- nombre de sections
- répartition N1/N2/N3
- typologie des sections
- volumes par section
- observations de cohérence

---

# ÉTAPE 6 — RÉÉQUILIBRAGE DOCUMENTAIRE

Si les proportions s'écartent fortement du profil choisi :
- proposer des reclassements
- proposer des réductions
- proposer des enrichissements

Validation humaine obligatoire avant application.

Les propositions doivent rester :
- cohérentes culturellement
- compatibles avec le thème
- adaptées au public ciblé

---

# ÉTAPE 7 — INDEX PAR NIVEAU

Créer un index regroupant les items par niveau :
- N1
- N2
- N3

À ce stade :
pas encore de quotas d’angles.

---

# ÉTAPE 8 — LÉGENDE

Ajouter :
- format du code
- catégories
- niveaux
- profil documentaire utilisé

---

# ÉTAPE 9 — HISTORIQUE DES INTERVENTIONS

Documenter :
- l’état initial
- les transformations
- les arbitrages
- les rééquilibrages effectués

---

# ÉTAPE 10 — CRÉATION DU FICHIER ANGIPREGEN

Un angle = un aspect précis et non ambigu d’un item = une seule question possible.

Le fichier ANGIPREGEN sert à :
- cartographier les angles interrogeables
- éviter les redondances
- calibrer les futurs quotas de questions

---

# ANGLES — PRINCIPES GÉNÉRAUX

Les quotas d’angles doivent rester souples.

L’objectif :
- obtenir une génération cohérente
- éviter les doublons
- préserver les angles les plus pertinents

Les suppressions d’angles peuvent être motivées par :
- redondance
- faible intérêt documentaire
- angle trop évident
- angle trop faible pour le niveau ciblé

---

# RÈGLE — DISTRACTEURS FICTIFS

Les distracteurs inventés sont autorisés uniquement après validation humaine manuelle.

- L’IA ne peut jamais valider seule un distracteur fictif
- Tout nom inventé doit être vérifié avant intégration
- Les distracteurs fictifs doivent rester crédibles sans pouvoir être confondus avec une véritable entité locale existante
- Tout distracteur fictif doit rester traçable dans le workflow (MODIFICATIONS_LOG)

---

# ÉTAPE 11 — MISE À JOUR DE L'INDEX

Une fois les angles définis :
- mettre à jour les quotas indicatifs
- vérifier l’équilibrage global
- ajuster si nécessaire

---

# ORDRE D'EXÉCUTION OPTIMAL

0. Archiver l’original
1. Auditer le fichier brut
2. Harmoniser les niveaux
3. Mettre en ligne unique
4. Coder les items
5. Construire les statistiques
6. Rééquilibrer si nécessaire
7. Créer l’index
8. Ajouter légende et historique
9. Créer ANGIPREGEN
10. Ajuster les quotas d’angles
11. Vérifier l’équilibre documentaire global

---

# MÉTRIQUES DE QUALITÉ

Un traitement est considéré comme cohérent si :
- les niveaux restent globalement équilibrés
- le profil documentaire choisi est respecté de manière souple
- les codes sont uniques
- les angles restent distincts
- le BIB original reste intact
- les rééquilibrages restent culturellement cohérents

Les objectifs chiffrés servent de guides documentaires et non d’obligations absolues.
