# MDE_A4 — CRÉER LE TABLEUR XLSX DEPUIS POOLS_[THEME].txt

**Version :** 1.0
**Workflow :** A4 (définition pools) + A5 (création tableur)
**Prérequis :** POOLS_[THEME].txt validé (étape A4 complète)
**Livrable :** `[THEME]_A5_TABLEUR_POOLS.xlsx`

---

## RÔLE DE CE DOCUMENT

Transformer le fichier POOLS_[THEME].txt en tableur xlsx opérationnel, prêt à recevoir les questions générées à l'étape B2.

Le tableur est le **chaînon entre l'architecture (A4) et la production (B2)**. Il ne contient pas encore de questions — seulement la structure et les lignes vides pré-créées.

---

## PRÉREQUIS

| Document | Statut requis |
|---|---|
| `POOLS_[THEME].txt` | ✅ Validé humainement |
| `ANGIPREGEN_[THEME].txt` | ✅ Disponible (pour vérification des sources) |
| Outil Python + openpyxl | Disponible en session |

---

## STRUCTURE DU TABLEUR

### Onglets

| Onglet | Contenu |
|---|---|
| `SOMMAIRE` | Vue globale des 20 pools + compteurs QA automatiques |
| `IF-SF-01` à `IF-SF-02` | 1 onglet par pool IF-SF |
| `IF-ROT-01` à `IF-ROT-03` | 1 onglet par pool IF-ROT |
| `QV-01` à `QV-15` | 1 onglet par pool QV |

**Total : 21 onglets** (1 SOMMAIRE + 20 pools)

### Colonnes (identiques sur tous les onglets pool)

| Col | Nom | Contenu |
|---|---|---|
| A | ID_Q | Identifiant unique auto-généré — ex : `CDM-IFSF01-Q001` |
| B | Pool | Identifiant du pool — ex : `CDM-POOL-IF-SF-01` |
| C | Angle_ID | Code ANGIPREGEN source — ex : `CDM-JOU-01` |
| D | Niveau | N1 / N2 / N3 |
| E | Question | Texte de la question |
| F–I | A / B / C / D | Texte des 4 propositions |
| J | Bonne_Rep | Lettre de la bonne réponse (A / B / C / D) |
| K | Tags | Mots-clés thématiques libres |
| L | QA_STATUS | DRAFT → PASS / WARNING / FAIL (liste déroulante) |

### Lignes pré-créées par type de pool

| Type | Lignes vides | Cible |
|---|---|---|
| IF-SF | 8 | 8 questions |
| IF-ROT | 12 | 12 questions |
| QV | 15 | 15 questions |

---

## STRUCTURE D'UN ONGLET POOL

```
Ligne 1 : Bandeau titre — ID pool / Thème / Type / Target
Ligne 2 : SOURCE ANGIPREGEN
Ligne 3 : EXCLUSIONS + NOTES anti-collision
Ligne 4 : Séparateur vide
Ligne 5 : En-têtes colonnes
Lignes 6 à 6+target-1 : Lignes de questions pré-créées (ID auto, Pool pré-rempli, QA_STATUS=DRAFT)
Dernière ligne : Compteurs PASS / WARNING / FAIL / DRAFT
```

---

## CODE COULEUR

| Type | En-tête | Fond lignes pairs | Usage |
|---|---|---|---|
| IF-SF | Rouge foncé `#8B0000` | `#FFF5F5` | Incontournables semi-fixes |
| IF-ROT | Bleu foncé `#1F497D` | `#F0F5FF` | Incontournables rotatifs |
| QV | Vert foncé `#375623` | `#F4FAF2` | Questions variables |

---

## SOMMAIRE — COLONNES

Le SOMMAIRE contient pour chaque pool :

`#` / `Pool ID` / `Type` / `Thème` / `Target` / `Source ANGIPREGEN` / `Exclu` / `Notes` / `Q PASS` / `Q WARNING` / `Q FAIL` / `Q DRAFT` / `% Complet`

Les colonnes `Q PASS`, `Q WARNING`, `Q FAIL`, `Q DRAFT` et `% Complet` sont des **formules COUNTIF** qui lisent automatiquement la colonne `QA_STATUS` de chaque onglet. Elles se mettent à jour à l'ouverture du fichier.

---

## FORMAT DES IDs QUESTION

```
CDM-[TYPE_COURT]-[NN]-Q[NNN]
```

Exemples :
- `CDM-IFSF01-Q001` (Pool IF-SF-01, question 1)
- `CDM-IFROT02-Q008` (Pool IF-ROT-02, question 8)
- `CDM-QV03-Q015` (Pool QV-03, question 15)

**Règle :** Les tirets sont supprimés du type pour raccourcir l'ID.

---

## PROCÉDURE DE CRÉATION (IA)

1. Lire `POOLS_[THEME].txt` — extraire les 20 définitions
2. Exécuter le script Python `build_[theme]_xlsx.py` via bash
3. Recalculer avec `scripts/recalc.py` — vérifier 0 erreurs
4. Copier le fichier dans `_LIGNES/_[THEME]/02_TRAITEMENT/`
5. Signaler les pools éditoriaux (SOURCE = Éditorial) qui nécessitent validation humaine

---

## RÈGLES CRITIQUES

- **Ne jamais modifier les IDs auto-générés** — ils servent de clé de traçabilité
- **Ne jamais supprimer les lignes pré-créées** — ajouter des lignes si besoin de dépasser le target
- **QA_STATUS = DRAFT par défaut** — seule la validation humaine peut le passer à PASS
- **Les colonnes Pool et ID_Q sont pré-remplies** — ne pas écraser
- **Les formules du SOMMAIRE sont dynamiques** — ne pas les remplacer par des valeurs

---

## UTILISATION EN B2 (GÉNÉRATION)

À l'étape B2, l'IA remplit le tableur pool par pool :

1. Ouvrir l'onglet du pool en cours
2. Lire les NOTES et EXCLUDED_POOLS de la ligne 3
3. Générer les questions dans les lignes pré-créées
4. Remplir : Angle_ID / Niveau / Question / A / B / C / D / Bonne_Rep / Tags
5. Laisser QA_STATUS = DRAFT
6. Ne pas passer au pool suivant sans validation humaine du pool en cours

---

## DOCUMENTS LIÉS

| Document | Rôle |
|---|---|
| `POOLS_[THEME].txt` | Source de définition des 20 pools |
| `ANGIPREGEN_[THEME].txt` | Angles interrogeables — source des Angle_ID |
| `MDE_B2_generation.md` | Mode opératoire de génération des questions dans le tableur |
| `MDE_B5_audit.md` | Audit humain + passage QA_STATUS DRAFT → PASS/WARNING/FAIL |
