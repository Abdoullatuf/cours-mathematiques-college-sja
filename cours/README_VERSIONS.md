# Guide des Versions Élève et Professeur

## Vue d'ensemble

Pour chaque niveau (6e, 5e, 4e), il existe désormais **deux versions** du cours :

### Version Élève
- Fichier source : `main_XXe_eleve.tex`
- Contient des **espaces à trous** (lignes pointillées) pour que les élèves complètent
- Format idéal pour distribuer aux élèves en classe

### Version Professeur
- Fichier source : `main_XXe_prof.tex`
- Contient **toutes les réponses** affichées en **bleu**
- Mention "VERSION PROFESSEUR" sur la page de titre
- Format idéal pour préparer les cours et avoir le corrigé sous les yeux

## Fichiers disponibles

### 6e (Sixième)
| Type | Fichier source | PDF généré | Pages | Taille |
|------|---------------|------------|-------|--------|
| Élève | `6e/main_6e_eleve.tex` | `6e/main_6e_eleve.pdf` | 29 | 358 Ko |
| Professeur | `6e/main_6e_prof.tex` | `6e/main_6e_prof.pdf` | 29 | 367 Ko |

**Chapitres inclus :**
- Séquence 01 : Les nombres entiers
- Séquence 02 : Points et droites
- Séquence 03 : Fractions décimales et nombres décimaux

### 5e (Cinquième)
| Type | Fichier source | PDF généré | Pages | Taille |
|------|---------------|------------|-------|--------|
| Élève | `5e/main_5e_eleve.tex` | `5e/main_5e_eleve.pdf` | 45 | 646 Ko |
| Professeur | `5e/main_5e_prof.tex` | `5e/main_5e_prof.pdf` | 45 | 668 Ko |

**Chapitres inclus :**
- Séquence 01 : Calculs numériques
- Séquence 02 : Symétrie centrale
- Séquence 03 : Nombres en écriture fractionnaire

### 4e (Quatrième)
| Type | Fichier source | PDF généré | Pages | Taille |
|------|---------------|------------|-------|--------|
| Élève | `4e/main_4e_eleve.tex` | `4e/main_4e_eleve.pdf` | 43 | 393 Ko |
| Professeur | `4e/main_4e_prof.tex` | `4e/main_4e_prof.pdf` | 43 | 393 Ko |

**Chapitres inclus :**
- Séquence 01 : Les nombres relatifs
- Séquence 02 : Théorème de Pythagore
- Séquence 03 : Calcul littéral 1

## Comment compiler les documents

### Compilation manuelle

Pour compiler la version élève :
```bash
cd 6e  # ou 5e, ou 4e
pdflatex main_6e_eleve.tex
```

Pour compiler la version professeur :
```bash
cd 6e  # ou 5e, ou 4e
pdflatex main_6e_prof.tex
```

### Compilation automatique des deux versions

Pour compiler les deux versions d'un niveau en une seule commande :

**Pour 6e :**
```bash
cd 6e
pdflatex main_6e_eleve.tex && pdflatex main_6e_prof.tex
```

**Pour 5e :**
```bash
cd 5e
pdflatex main_5e_eleve.tex && pdflatex main_5e_prof.tex
```

**Pour 4e :**
```bash
cd 4e
pdflatex main_4e_eleve.tex && pdflatex main_4e_prof.tex
```

## Fonctionnement technique

Le système utilise la commande `\VersionCorrige` définie dans le préambule commun :

- **Version élève** : Par défaut, les commandes `\solution[largeur]{réponse}` créent des espaces pointillés
- **Version professeur** : Avec `\VersionCorrige`, les réponses s'affichent en bleu

### Exemple dans le code source

```latex
% Dans un chapitre .tex
La racine carrée de 16 est \solution[2cm]{4}.
```

**Résultat version élève :** `La racine carrée de 16 est ........`
**Résultat version professeur :** `La racine carrée de 16 est 4` (en bleu)

## Structure des fichiers

```
cours/
├── 6e/
│   ├── main_6e_eleve.tex    ← Version élève (espaces à trous)
│   ├── main_6e_prof.tex     ← Version professeur (avec corrections)
│   ├── main_6e_eleve.pdf    ← PDF élève généré
│   ├── main_6e_prof.pdf     ← PDF professeur généré
│   └── chapitres/
│       ├── seq_01.tex
│       ├── seq_02.tex
│       └── seq_03_fractions_decimales_et_nombres_decimaux.tex
├── 5e/
│   ├── main_5e_eleve.tex
│   ├── main_5e_prof.tex
│   ├── main_5e_eleve.pdf
│   ├── main_5e_prof.pdf
│   └── chapitres/
│       ├── seq_01.tex
│       ├── seq_02.tex
│       └── seq_03_nombres_en_ecriture_fractionnaire.tex
├── 4e/
│   ├── main_4e_eleve.tex
│   ├── main_4e_prof.tex
│   ├── main_4e_eleve.pdf
│   ├── main_4e_prof.pdf
│   └── chapitres/
│       ├── seq_01_nombres_relatifs.tex
│       ├── seq_02_pythagore_version_2.tex
│       └── seq_03_calcul_litteral_1.tex
└── commun/
    └── preambule_commun.tex  ← Définit le système \solution et \VersionCorrige
```

## Notes importantes

1. **Un seul fichier source par chapitre** : Les fichiers dans `chapitres/` sont partagés entre les deux versions. Le changement élève/professeur se fait uniquement au niveau du fichier `main_XXe_xxx.tex`.

2. **Modifications futures** : Pour ajouter du contenu avec correction :
   - Utilisez `\solution[largeur]{réponse}` pour les réponses courtes
   - Utilisez la structure `\ifcorrige ... \else ... \fi` pour les réponses longues

3. **Backup** : Pensez à sauvegarder régulièrement vos fichiers .tex dans un système de contrôle de version (git).

## Date de création

Système créé le : 13 octobre 2025

Niveaux configurés : 6e, 5e, 4e
